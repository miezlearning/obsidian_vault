# 📂 Struktur File Coffee Shop Bot

## 🌳 File Tree

```
coffee-shop-bot/
│
├── 📖 README.md              # Dokumentasi lengkap + setup guide
├── 📖 QRIS_GUIDE.md          # Panduan implementasi QRIS dinamis
├── 📖 QUICK_START.md         # Quick start dalam 5 menit
│
├── 📦 package.json           # Dependencies & scripts
├── 📄 .env.example           # Template environment variables
├── 🚫 .gitignore             # Git ignore file
│
├── ⚙️  index.js              # 🚀 ENTRY POINT - Start bot disini
│
├── 📁 src/                   # Source code utama
│   │
│   ├── ⚙️  bot.js            # 🤖 CORE BOT
│   │                         # - Inisialisasi WhatsApp connection
│   │                         # - Handle connection updates
│   │                         # - QR code generation
│   │                         # - Session management
│   │                         # - Cleanup jobs
│   │
│   ├── 📁 config/
│   │   └── ⚙️  config.js     # ⚙️ KONFIGURASI UTAMA
│   │                         # - Info coffee shop
│   │                         # - QRIS static
│   │                         # - Menu items & harga
│   │                         # - Nomor barista & admin
│   │                         # - Service fee settings
│   │                         # - Timeout settings
│   │                         # - Message templates
│   │
│   ├── 📁 commands/          # 📝 SEMUA COMMAND BOT
│   │   │
│   │   ├── ⚙️  index.js      # Command loader (auto-load semua commands)
│   │   │
│   │   ├── ⚙️  menu.js       # 📋 Command: !menu
│   │   │                     # - Tampilkan daftar menu
│   │   │                     # - Filter by category
│   │   │                     # - Show prices & availability
│   │   │
│   │   ├── ⚙️  order.js      # 🛒 Command: !order [ID] [QTY]
│   │   │                     # - Tambah item ke cart
│   │   │                     # - Validasi item & quantity
│   │   │                     # - Update cart session
│   │   │
│   │   ├── ⚙️  cart.js       # 🛒 Command: !cart
│   │   │                     # - Lihat isi keranjang
│   │   │                     # - Show subtotal & total
│   │   │                     # - Show service fee (if enabled)
│   │   │
│   │   ├── ⚙️  checkout.js   # 💳 Command: !checkout
│   │   │                     # - Create order dari cart
│   │   │                     # - Generate order ID
│   │   │                     # - Set payment expiry
│   │   │                     # - Clear cart
│   │   │
│   │   ├── ⚙️  pay.js        # 💰 Command: !pay [ORDER_ID]
│   │   │                     # - Generate QRIS dinamis
│   │   │                     # - Create QR code image
│   │   │                     # - Send payment info
│   │   │                     # - Handle payment timeout
│   │   │
│   │   ├── ⚙️  confirm.js    # ✅ Command: !confirm [ORDER_ID]
│   │   │                     # - Konfirmasi pembayaran
│   │   │                     # - Update order status to PAID
│   │   │                     # - Notify barista (auto)
│   │   │                     # - Send confirmation to customer
│   │   │
│   │   ├── ⚙️  status.js     # 📊 Command: !status [ORDER_ID]
│   │   │                     # - Cek status pesanan
│   │   │                     # - Show order details
│   │   │                     # - Show order history
│   │   │
│   │   ├── ⚙️  ready.js      # 👨‍🍳 Command: !ready [ORDER_ID]
│   │   │                     # - [BARISTA ONLY]
│   │   │                     # - Mark order as ready
│   │   │                     # - Notify customer (auto)
│   │   │
│   │   ├── ⚙️  help.js       # ❓ Command: !help
│   │   │                     # - Show command list
│   │   │                     # - Usage instructions
│   │   │                     # - Shop info
│   │   │
│   │   └── ⚙️  utils.js      # 🔧 Utility Commands
│   │                         # - !cancel: Clear cart
│   │                         # - !remove [ID]: Hapus item dari cart
│   │                         # - !info: Coffee shop info
│   │
│   ├── 📁 handlers/
│   │   └── ⚙️  messageHandler.js  # 🎯 MESSAGE ROUTER
│   │                              # - Parse incoming messages
│   │                              # - Extract command & args
│   │                              # - Route ke command handler
│   │                              # - Error handling
│   │
│   ├── 📁 services/
│   │   └── ⚙️  orderManager.js    # 📦 ORDER MANAGEMENT SERVICE
│   │                              # - Create/update/get orders
│   │                              # - Session management (cart)
│   │                              # - Calculate pricing & fees
│   │                              # - Order status lifecycle
│   │                              # - Expiry handling
│   │                              # - Order formatting
│   │
│   └── 📁 utils/
│       └── ⚙️  qris.js            # 💳 QRIS GENERATOR
│                                  # - convertQRIS(): QRIS static → dynamic
│                                  # - convertCRC16(): Calculate checksum
│                                  # - validateQRIS(): Validasi format
│                                  # - calculateTotal(): Hitung total + fee
│                                  # - generateOrderQRIS(): All-in-one
│
└── 📁 sessions/                   # 🔐 WhatsApp Auth Sessions
    └── (auto-generated)           # ⚠️ JANGAN di-commit ke Git!

```

---

## 📝 Penjelasan Detail per File

### 🚀 Root Level

#### `index.js` - Entry Point
```javascript
// Fungsi: Start bot & handle process
- Import WhatsAppBot class
- Initialize & start bot
- Handle SIGINT/SIGTERM (graceful shutdown)
- Keep process alive
```

#### `package.json` - Dependencies
```json
{
  "dependencies": {
    "@whiskeysockets/baileys": "^6.7.8",  // WhatsApp Web API
    "@hapi/boom": "^10.0.1",              // Error handling
    "pino": "^8.19.0",                    // Logger
    "qrcode-terminal": "^0.12.0",         // QR in terminal
    "moment-timezone": "^0.5.45",         // Date/time handling
    "node-cache": "^5.1.2"                // In-memory caching
  }
}
```

---

### 🤖 Core (`src/bot.js`)

**Responsibilities:**
- ✅ Initialize Baileys socket
- ✅ Generate QR code untuk login
- ✅ Handle connection events
- ✅ Route messages ke handler
- ✅ Session persistence
- ✅ Auto-reconnect
- ✅ Periodic cleanup jobs

**Key Functions:**
```javascript
start()                    // Start bot
handleConnection(update)   // Connection lifecycle
handleMessages(m)          // Process incoming messages
startCleanupJob()          // Cleanup expired orders (every 5 min)
sendMessage(to, content)   // Send message helper
```

---

### ⚙️ Config (`src/config/config.js`)

**Isi File:**
```javascript
module.exports = {
    bot: {
        name: 'Coffee Shop Bot',
        prefix: '!',
        timezone: 'Asia/Jakarta'
    },
    
    shop: {
        name: 'My Coffee Shop',
        address: '...',
        openHours: '08:00 - 22:00',
        contact: '08123456789',
        qrisStatic: 'YOUR_QRIS_HERE',  // ← GANTI INI!
        baristaNumbers: [...],          // ← GANTI INI!
        adminNumbers: [...]
    },
    
    menu: {
        categories: { ... },
        items: [
            { id: 'C001', name: 'Espresso', price: 15000, ... },
            // ... menu lainnya
        ]
    },
    
    order: {
        maxItemsPerOrder: 10,
        orderTimeout: 15,      // minutes
        paymentTimeout: 10,    // minutes
        serviceFee: { ... }
    },
    
    messages: { ... }  // Template pesan
}
```

**Yang Perlu Diganti:**
1. ✏️ `shop.qrisStatic` - QRIS dari merchant
2. ✏️ `shop.baristaNumbers` - Nomor WA barista
3. ✏️ `shop.name`, `address`, dll - Info shop kamu
4. ✏️ `menu.items` - Menu coffee shop kamu

---

### 📝 Commands (`src/commands/`)

Setiap command file export object dengan struktur:
```javascript
module.exports = {
    name: 'nama_command',
    description: 'Deskripsi command',
    aliases: ['alias1', 'alias2'],
    
    async execute(sock, msg, args) {
        // Logic command disini
    }
}
```

#### Flow Command:
```
User kirim: "!menu coffee"
      ↓
messageHandler parse: command = "menu", args = ["coffee"]
      ↓
Route ke: commands/menu.js
      ↓
Execute: menu.execute(sock, msg, ["coffee"])
      ↓
Response dikirim ke user
```

---

### 🎯 Message Handler (`src/handlers/messageHandler.js`)

**Flow:**
```javascript
1. Extract message text
2. Check if starts with prefix (!)
3. Parse command & arguments
4. Find command in commands object
5. Execute command
6. Handle errors
```

**Example:**
```
Input: "!order C001 2"
Parse: {
    command: "order",
    args: ["C001", "2"]
}
Execute: commands.order.execute(sock, msg, ["C001", "2"])
```

---

### 📦 Order Manager (`src/services/orderManager.js`)

**Key Features:**
- ✅ In-memory storage (node-cache)
- ✅ Session management (cart per user)
- ✅ Order lifecycle management
- ✅ Price calculation with fees
- ✅ Auto-expiry handling
- ✅ Order formatting

**Order Status Flow:**
```
DRAFT
  ↓
PENDING_PAYMENT  (after checkout)
  ↓
PAID  (after confirm)
  ↓
PROCESSING  (barista notified)
  ↓
READY  (barista marks ready)
  ↓
COMPLETED  (customer picks up)
```

**Key Functions:**
```javascript
createSession(userId)                    // Create cart session
addItemToCart(userId, item, qty)         // Add to cart
removeItemFromCart(userId, itemId)       // Remove from cart
calculateTotal(items, includeFee)        // Calculate pricing
createOrder(userId)                      // Create order from cart
updateOrderStatus(orderId, status)       // Update status
isPaymentExpired(orderId)                // Check expiry
formatOrderDetails(order)                // Format for display
```

---

### 💳 QRIS Generator (`src/utils/qris.js`)

**Implementasi dari code TypeScript kamu!**

**Key Functions:**

1. **`convertQRIS(qris, nominal, feeOption, feeAmount)`**
   ```javascript
   // Convert QRIS static → dynamic dengan nominal
   const dynamicQRIS = QRISGenerator.convertQRIS(
       'YOUR_STATIC_QRIS',
       25000,      // Rp 25,000
       'percent',  // Optional: fee type
       2           // Optional: 2%
   );
   ```

2. **`convertCRC16(str)`**
   ```javascript
   // Calculate CRC16 checksum untuk QRIS
   const crc = QRISGenerator.convertCRC16(qrisString);
   // Returns: "4F1A" (4 character hex)
   ```

3. **`validateQRIS(qris)`**
   ```javascript
   // Validate QRIS format
   const isValid = QRISGenerator.validateQRIS(qrisString);
   // Returns: true/false
   ```

4. **`calculateTotal(subtotal, feeConfig)`**
   ```javascript
   // Calculate total dengan fee
   const { subtotal, fee, total } = QRISGenerator.calculateTotal(
       25000,
       { enabled: true, type: 'percent', amount: 2 }
   );
   // Returns: { subtotal: 25000, fee: 500, total: 25500 }
   ```

5. **`generateOrderQRIS(staticQRIS, amount, feeConfig)`**
   ```javascript
   // All-in-one: generate QRIS dengan fee
   const dynamicQRIS = QRISGenerator.generateOrderQRIS(
       staticQRIS,
       25000,
       { enabled: true, type: 'percent', amount: 2 }
   );
   ```

**QRIS Format:**
```
Static QRIS:  00020101021226670016ID...5802ID...6304XXXX
                    ↓ (change)
Dynamic QRIS: 00020102021226670016ID...54052500055802ID...6304YYYY
                    ↑                    ↑                    ↑
                 dynamic              amount               new CRC
```

---

## 🔄 Flow Lengkap Sistem

### 1️⃣ Customer Order Flow
```
1. !menu                    → Show menu
2. !order C001 2           → Add to cart
3. !cart                   → View cart
4. !checkout               → Create order (Order ID: CF123456)
5. !pay CF123456           → Generate QRIS
6. [Scan & Pay QRIS]       → Payment via e-wallet
7. !confirm CF123456       → Confirm payment
   ↓
   Order status: PAID → PROCESSING
   ↓
   Barista auto-notified
```

### 2️⃣ Barista Processing Flow
```
1. Receive notification: 🔔 New Order CF123456
2. Check order details
3. Process order (make coffee)
4. !ready CF123456         → Mark as ready
   ↓
   Customer auto-notified
```

### 3️⃣ Customer Pickup Flow
```
1. Receive notification: 🎉 Order Ready!
2. Go to counter
3. Show Order ID
4. Pick up order
   ↓
   Order status: COMPLETED
```

---

## 🔧 Cara Modifikasi

### Tambah Menu Baru
Edit `src/config/config.js`:
```javascript
menu: {
    items: [
        // ... existing items
        { 
            id: 'C009', 
            name: 'Flat White', 
            category: 'coffee', 
            price: 26000, 
            available: true 
        }
    ]
}
```

### Tambah Command Baru
1. Create file `src/commands/mycommand.js`:
```javascript
module.exports = {
    name: 'mycommand',
    description: 'My new command',
    
    async execute(sock, msg, args) {
        const from = msg.key.remoteJid;
        await sock.sendMessage(from, { 
            text: 'Hello from my command!' 
        });
    }
};
```
2. Command otomatis ke-load oleh `src/commands/index.js`
3. Usage: `!mycommand`

### Ubah Prefix Command
Edit `src/config/config.js`:
```javascript
bot: {
    prefix: '/'  // Change from ! to /
}
```
Usage: `/menu`, `/order`, dll

### Enable Service Fee
Edit `src/config/config.js`:
```javascript
order: {
    serviceFee: {
        enabled: true,
        type: 'percent',  // or 'rupiah'
        amount: 2         // 2% or Rp 2000
    }
}
```

---

## 🎯 File Penting yang Perlu Diperhatikan

### ⚠️ HARUS DIGANTI:
1. ✏️ `src/config/config.js` → `shop.qrisStatic`
2. ✏️ `src/config/config.js` → `shop.baristaNumbers`
3. ✏️ `src/config/config.js` → `shop.name`, `address`, dll
4. ✏️ `src/config/config.js` → `menu.items`

### 🚫 JANGAN DI-COMMIT:
1. ❌ `sessions/` folder (contains auth data)
2. ❌ `.env` file (if you create it)

### 📦 AUTO-GENERATED:
1. 🔄 `sessions/` folder (after first QR scan)
2. 🔄 `node_modules/` folder (after npm install)

---

## 📚 Dokumentasi File

- **README.md** → Setup guide lengkap
- **QRIS_GUIDE.md** → Detail implementasi QRIS
- **QUICK_START.md** → Quick start 5 menit
- **SUMMARY.md** → Overview project

---

Semua file sudah siap pakai! 🎉
