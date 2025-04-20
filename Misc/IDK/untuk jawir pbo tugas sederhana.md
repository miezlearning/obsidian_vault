## 🧾 **Penjelasan Perubahan dan Perbaikan dari struktur lama ke baru.**

---

### 🔁 **Perbandingan Fitur**

| Fitur            | `old.py`                              | `new.py`                                                        |
| ---------------- | ------------------------------------- | --------------------------------------------------------------- |
| Struktur Data    | Menggunakan banyak `if-else`          | Menggunakan `dictionary` untuk data wahana dan harga            |
| Validasi Input   | Sederhana, tidak konsisten            | Menggunakan `set` untuk validasi input menu utama & submenu     |
| UI & Tampilan    | Teks polos                            | Menggunakan **ASCII Art** dan **warna terminal ANSI**           |
| Penanganan Error | Ada sebagian `try-except`             | Konsisten menggunakan `try-except` untuk validasi input angka   |
| Pengulangan      | `while True` dengan banyak `continue` | Tetap `while True` tetapi lebih **rapih dan modular**           |
| Output & Harga   | Hardcoded per pilihan                 | Data dinamis melalui dictionary dan `f-string` untuk formatting |

---

### 📦 **Struktur Data yang Digunakan**

```python
wahana_kecil = {
    '1': {'name': 'Trampolin Mini', 'price': 20000},
    '2': {'name': 'Kolam Bola', 'price': 25000},
    '3': {'name': 'Ayunan dan Perosotan Kecil', 'price': 25000}
}
```

- ✅ Lebih **terstruktur dan mudah di-maintain** (lebih mudah untuk di edit di masa dpean)
    
- ✅ Bisa digunakan untuk melakukan looping jika ingin menampilkan semua item
    

---

### 🎨 **Tampilan & Warna Terminal**

Menggunakan `ANSI Escape Code` untuk memberikan warna pada teks:

```python
warna = {
    'hijau': "\033[92m",
    'merah': "\033[91m",
    'reset': "\033[0m"
}
```

---

### 💡 **Kelebihan `new.py`**

- ✅ Lebih rapi dan **mudah dikembangkan**
    
- ✅ Menambahkan visual ASCII art dan warna
    
- ✅ Penggunaan `dictionary` membuat program **lebih scalable**
    
- ✅ Validasi input lebih aman dan terstruktur
    
- ✅ Lebih profesional dan nyaman digunakan
    

---

### ❗ Catatan Tambahan

- `old.py` cocok untuk pemula karena sederhana
- `new.py` cocok untuk digunakan sebagai **tugas akhir mini-project** karena sudah memakai **konsep modular dan clean code**
    