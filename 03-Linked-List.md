# 📚 PERTEMUAN 3 SINGLE LINKED LIST (SLL)

# 1️⃣ Identitas Pertemuan  

**Mata Kuliah**: Struktur Data  
**Topik**: Single Linked List  
**Pertemuan ke**: 3  
**Bobot Waktu**: 1 × 150 menit  

# 2️⃣ Capaian Pembelajaran (Sub-CPMK)

Mahasiswa mampu:
1. Menjelaskan konsep Linked List sebagai struktur data dinamis.
2. Mendeskripsikan perbedaan array dan linked list.
3. Mengimplementasikan Single Linked List dalam Python.
4. Mengimplementasikan operasi dasar:
   * Insert di awal
   * Insert di akhir
   * Read (Traversal)
5. Menganalisis kompleksitas waktu operasi.

# 3️⃣ Tujuan Pembelajaran

Setelah mengikuti pertemuan ini mahasiswa mampu:

* Memahami konsep pointer/referensi dalam struktur data dinamis.
* Mengimplementasikan node dan linked list.
* Menjelaskan alur perubahan referensi saat insert dilakukan.
* Menentukan kompleksitas waktu operasi dasar.

# 4️⃣ Manfaat Mempelajari Linked List

1. Digunakan pada implementasi Stack & Queue.
2. Digunakan pada Graph (Adjacency List).
3. Digunakan pada manajemen memori dinamis.
4. Lebih fleksibel dibanding array dalam alokasi memori.

Menurut Introduction to Algorithms, linked list merupakan struktur linear dinamis dengan akses sekuensial dan efisien dalam operasi penyisipan pada awal struktur.

# 5️⃣ Konsep Dasar Single Linked List

## 🔹 Definisi

Single Linked List adalah struktur data linear yang terdiri dari sekumpulan node, di mana setiap node memiliki:

* Data
* Pointer (referensi) ke node berikutnya

## 🔹 Representasi Konseptual

```
Head → [10 | * ] → [20 | * ] → [30 | None]
```

## 🔹 Karakteristik

* Tidak menggunakan indeks
* Tidak memiliki alokasi memori berurutan
* Traversal harus dari head

# 6️⃣ Perbandingan Array vs Linked List

| Aspek                | Array        | Linked List   |
| -------------------- | ------------ | ------------- |
| Memori               | Kontigu      | Tidak kontigu |
| Insert awal          | Mahal (O(n)) | Murah (O(1))  |
| Akses indeks         | O(1)         | O(n)          |
| Fleksibilitas ukuran | Tetap        | Dinamis       |


# 7️⃣ Implementasi dalam Python

## 7.1 Struktur Node

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
```

## 7.2 Struktur Linked List

```python
class LinkedList:
    def __init__(self):
        self.head = None
```

# 8️⃣ Operasi Dasar Single Linked List

# 🔹 1. Insert di Awal (O(1))

## Konsep:

1. Node baru dibuat
2. Next node baru menunjuk ke head lama
3. Head dipindahkan ke node baru

```python
def insert_awal(self, data):
    node_baru = Node(data)
    node_baru.next = self.head
    self.head = node_baru
```

# 🔹 2. Insert di Akhir (O(n))

## Konsep:

1. Jika list kosong → head = node baru
2. Jika tidak → traversal sampai node terakhir
3. Node terakhir.next = node baru

```python
def insert_akhir(self, data):
    node_baru = Node(data)

    if self.head is None:
        self.head = node_baru
        return

    current = self.head
    while current.next:
        current = current.next

    current.next = node_baru
```

# 🔹 3. Read / Traversal (O(n))

## Konsep:

Menelusuri node dari head hingga None.

```python
def tampilkan(self):
    current = self.head
    while current:
        print(current.data, end=" -> ")
        current = current.next
    print("None")
```

# 9️⃣ Program Lengkap Single Linked List

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None


class LinkedList:
    def __init__(self):
        self.head = None

    def insert_awal(self, data):
        node_baru = Node(data)
        node_baru.next = self.head
        self.head = node_baru

    def insert_akhir(self, data):
        node_baru = Node(data)

        if self.head is None:
            self.head = node_baru
            return

        current = self.head
        while current.next:
            current = current.next

        current.next = node_baru

    def tampilkan(self):
        current = self.head
        while current:
            print(current.data, end=" -> ")
            current = current.next
        print("None")


# Pengujian
ll = LinkedList()
ll.insert_awal(10)
ll.insert_awal(20)
ll.insert_akhir(30)
ll.insert_akhir(40)

ll.tampilkan()
```

Output:

```
20 -> 10 -> 30 -> 40 -> None
```

# 🔎 Analisis Kompleksitas

| Operasi      | Kompleksitas |
| ------------ | ------------ |
| Insert Awal  | O(1)         |
| Insert Akhir | O(n)         |
| Traversal    | O(n)         |

Penjelasan lebih lanjut mengenai kompleksitas struktur list linear dapat ditemukan pada
Data Structures and Algorithm Analysis in C

# 🔬 Studi Kasus Sederhana

## Kasus: Manajemen Antrian Sederhana

Sistem menyimpan nomor antrian:

* Pasien datang → insert di akhir
* Admin melihat daftar → traversal

Diskusi kelas:

* Mengapa tidak menggunakan array?
* Bagaimana jika antrian bertambah sangat besar?

# 🧪 Praktikum Pertemuan 3

## Tugas Praktikum

1. Tambahkan fungsi:

   * search(data)
   * delete(data)
2. Hitung jumlah node dalam list.
3. Tampilkan panjang list.

# 🎯 Project Mini – “Sistem Manajemen Buku”

Buat program:

* Tambah buku di awal
* Tambah buku di akhir
* Tampilkan daftar buku
* Hitung jumlah buku

Output berbentuk menu interaktif.

# 📊 Rubrik Penilaian Project

| Aspek               | Bobot |
| ------------------- | ----- |
| Struktur Node benar | 20%   |
| Insert Awal         | 20%   |
| Insert Akhir        | 20%   |
| Traversal           | 20%   |
| Kerapian & Logika   | 20%   |

# 📖 Referensi
1. Introduction to Algorithms
2. Data Structures and Algorithm Analysis in C
