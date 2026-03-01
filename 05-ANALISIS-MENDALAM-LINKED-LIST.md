# 📚 PERTEMUAN 5 IMPLEMENTASI LANJUTAN & ANALISIS MENDALAM LINKED LIST

# 1️⃣ Identitas Pertemuan

**Mata Kuliah**: Struktur Data
**Topik**: Operasi Lanjutan Linked List & Analisis Kompleksitas
**Pertemuan ke**: 5
**Waktu**: 1 × 150 menit

# 2️⃣ Capaian Pembelajaran
Mahasiswa mampu:
1. Mengimplementasikan operasi lanjutan pada Linked List.
2. Menganalisis kompleksitas waktu dan ruang.
3. Mengidentifikasi kasus edge case.
4. Membandingkan efisiensi dengan array.
5. Menerapkan Linked List dalam studi kasus nyata.
6. Melakukan evaluasi performa secara konseptual.

# 3️⃣ Tujuan Pembelajaran

Setelah pertemuan ini mahasiswa mampu:
* Mengimplementasikan operasi delete, search, reverse.
* Menangani kondisi list kosong dan satu node.
* Menganalisis Big-O setiap operasi.
* Menentukan struktur yang optimal untuk suatu masalah.

# 4️⃣ Operasi Lanjutan Single Linked List

# 🔹 4.1 Operasi Search (O(n))

### Konsep:

Traversal hingga data ditemukan atau None.

```python
def search(self, key):
    current = self.head
    posisi = 0

    while current:
        if current.data == key:
            return posisi
        current = current.next
        posisi += 1

    return -1
```

# 🔹 4.2 Operasi Delete Berdasarkan Nilai

## Kasus:

1. Hapus di awal
2. Hapus di tengah
3. Hapus di akhir

```python
def delete(self, key):
    current = self.head

    if current and current.data == key:
        self.head = current.next
        return

    prev = None
    while current and current.data != key:
        prev = current
        current = current.next

    if current is None:
        return

    prev.next = current.next
```

Kompleksitas: **O(n)**

# 🔹 4.3 Reverse Linked List (Iteratif)

### Konsep:

Balik arah pointer next.

```python
def reverse(self):
    prev = None
    current = self.head

    while current:
        next_node = current.next
        current.next = prev
        prev = current
        current = next_node

    self.head = prev
```

Kompleksitas:

* Waktu: O(n)
* Ruang: O(1)

Reverse Linked List sering dijadikan studi klasik dalam analisis algoritma (lihat Introduction to Algorithms).

# 5️⃣ Analisis Kompleksitas Mendalam

## 5.1 Kompleksitas Waktu

| Operasi      | Kompleksitas |
| ------------ | ------------ |
| Insert Awal  | O(1)         |
| Insert Akhir | O(n)         |
| Search       | O(n)         |
| Delete       | O(n)         |
| Reverse      | O(n)         |

## 5.2 Kompleksitas Ruang

Linked List membutuhkan:
* 1 pointer tambahan per node (Single)
* 2 pointer tambahan (Double)

Ruang total:

```
O(n)
```

# 6️⃣ Perbandingan Mendalam: Array vs Linked List

| Aspek          | Array   | Linked List |
| -------------- | ------- | ----------- |
| Akses          | O(1)    | O(n)        |
| Insert Awal    | O(n)    | O(1)        |
| Insert Tengah  | O(n)    | O(n)        |
| Memori         | Kontigu | Terpisah    |
| Cache Friendly | Ya      | Tidak       |

Linked List kurang cache-friendly karena lokasi memori tersebar, sebagaimana dibahas dalam Data Structures and Algorithm Analysis in C.

# 7️⃣ Edge Case & Kesalahan Umum

1. Infinite loop pada Circular Linked List
2. Null pointer (NoneType error)
3. Kehilangan referensi head
4. Tidak menangani list kosong
5. Tidak menangani satu node

Diskusi kelas:
* Mengapa kehilangan referensi head fatal?
* Bagaimana mencegah infinite loop?

# 8️⃣ Studi Kasus Akademik

## 🔹 8.1 Implementasi Stack Menggunakan Linked List

Push → insert awal
Pop → delete awal

Kompleksitas:
O(1)

## 🔹 8.2 Implementasi Queue Menggunakan Linked List
Enqueue → insert akhir
Dequeue → delete awal

Kompleksitas:
O(1) jika menggunakan tail pointer.

## 🔹 8.3 Deteksi Siklus (Cycle Detection)

Konsep Floyd’s Cycle Detection (Tortoise and Hare).

Ide:
* Dua pointer dengan kecepatan berbeda
* Jika bertemu → ada siklus

Digunakan dalam analisis graph dan struktur memori.

# 9️⃣ Evaluasi Performa (Konseptual)

Pertanyaan analitis:

1. Mengapa Insert Akhir menjadi mahal?
2. Bagaimana mengoptimalkan Insert Akhir?
   * Tambahkan tail pointer
3. Apa trade-off penggunaan Double Linked List?

# 🧪 Praktikum Pertemuan 5

## Latihan 1

Implementasikan:

* search
* delete
* reverse

## Latihan 2

Tambahkan:
* Fungsi menghitung panjang list
* Fungsi mengecek list kosong

## Latihan 3 (Analitis)

Bandingkan:
* Waktu eksekusi insert 10.000 data pada array vs linked list
  (analisis konseptual, tidak perlu benchmarking real)

# 🎯 Project Akhir Mini Modul Linked List

## Project: “Sistem Manajemen Playlist Musik”

Gunakan Circular Linked List.

Fitur:
1. Tambah lagu
2. Hapus lagu
3. Tampilkan playlist
4. Next lagu (rotasi)
5. Reverse playlist

Tambahan analisis:
* Jelaskan kompleksitas setiap fitur.
* Jelaskan mengapa Circular lebih cocok dibanding Single.

# 📊 Rubrik Penilaian Project

| Aspek                         | Bobot |
| ----------------------------- | ----- |
| Implementasi Operasi Lanjutan | 30%   |
| Logika Circular / Reverse     | 20%   |
| Penanganan Edge Case          | 15%   |
| Analisis Kompleksitas         | 20%   |
| Kerapian & Struktur Program   | 15%   |

# 📖 Referensi Akademik
1. Introduction to Algorithms
2. Data Structures and Algorithm Analysis in C

# 🔎 Penutup Akademik

Pada pertemuan 3–5 mahasiswa telah memahami:

* Struktur dasar Linked List
* Variasi struktur (Single, Double, Circular)
* Operasi dasar & lanjutan
* Analisis kompleksitas
* Studi kasus implementatif
* Hash Table
* Tree Structure
