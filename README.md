# 📚 MATA KULIAH: STRUKTUR DATA

Semester 2 | 3 SKS (T=2, P=1)

---

# 🔹 PERTEMUAN 1

## ARRAY (1D & 2D)

### 🎯 Tujuan

Mahasiswa mampu memahami konsep array dan mengimplementasikan array 1D dan 2D.

### ✅ Manfaat

* Dasar semua struktur data
* Memahami penyimpanan data terstruktur
* Bekal ke sorting & searching

### 📘 Materi Inti (Sederhana)

* Struktur data = cara menyimpan & mengatur data
* Array = kumpulan data bertipe sama
* Index dimulai dari 0
* 1D → seperti daftar
* 2D → seperti tabel

Contoh:

```python
# Array 1D
data = [10, 20, 30]

# Array 2D
matrix = [
    [1,2],
    [3,4]
]
```

### 🧪 Praktikum

1. Input 10 angka → tampilkan nilai terbesar
2. Buat program matriks 3x3 → hitung jumlah tiap baris

### 📝 Tugas GitHub

Buat repository:

```
struktur-data-pertemuan-1
```

Isi:

* program_array_1d.py
* program_array_2d.py
* README.md (penjelasan konsep)

---

# 🔹 PERTEMUAN 2

## ARRAY N-DIMENSI & ARRAY DINAMIS

### 🎯 Tujuan

Mahasiswa memahami array multidimensi dan konsep array dinamis.

### ✅ Manfaat

Digunakan dalam:

* Pengolahan citra
* Machine learning
* Data tabel kompleks

### 📘 Materi

* 3D array → seperti kubus data
* Array dinamis → ukuran bisa berubah

Contoh:

```python
data = []
data.append(10)
data.append(20)
```

### 🧪 Praktikum

* Buat sistem input nilai mahasiswa (dinamis)
* Hitung rata-rata otomatis

### 📝 Tugas GitHub

Update repo sebelumnya:

* tambah folder pertemuan-2
* jelaskan perbedaan array statis & dinamis

---

# 🔹 PERTEMUAN 3

## REKURSIF

### 🎯 Tujuan

Mahasiswa memahami fungsi rekursif.

### ✅ Manfaat

Digunakan pada:

* Tree
* DFS Graph
* Sorting tertentu

### 📘 Materi

Rekursif = fungsi memanggil dirinya sendiri.

Contoh:

```python
def faktorial(n):
    if n == 1:
        return 1
    return n * faktorial(n-1)
```

### 🧪 Praktikum

* Faktorial
* Deret Fibonacci

### 📝 Tugas GitHub

Repo:

```
struktur-data-pertemuan-3
```

Buat:

* faktorial_rekursif.py
* fibonacci_rekursif.py
* analisis waktu eksekusi

---

# 🔹 PERTEMUAN 4-5

## LINKED LIST

### 🎯 Tujuan

Mahasiswa mampu membuat:

* Single Linked List
* Double Linked List
* Circular Linked List

### ✅ Manfaat

Digunakan dalam:

* Browser history
* Undo/Redo
* Sistem playlist

### 📘 Konsep Sederhana

Linked List = node yang saling terhubung

Node:

```
[data | next]
```

Contoh dasar:

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
```

### 🧪 Praktikum

* Insert awal
* Insert akhir
* Hapus node
* Traversal

### 📝 Tugas 1 (Sesuai RPS)

Implementasi:
Circular Linked List menggunakan rekursif

Repo:

```
struktur-data-tugas-1
```

Isi:

* source code
* paper analisis PDF
* README

---

# 🔹 PERTEMUAN 6

## STACK

### 🎯 Tujuan

Mahasiswa mampu membuat stack dengan:

* Array
* Linked List

### ✅ Manfaat

Digunakan pada:

* Undo
* Call Stack
* Validasi tanda kurung

### 📘 Konsep

Stack = LIFO (Last In First Out)

Operasi:

* push
* pop
* peek

### 🧪 Praktikum

* Validasi kurung "()[]{}"
* Simulasi undo

### 📝 Tugas

Upload:

```
stack-array.py
stack-linkedlist.py
```

---

# 🔹 PERTEMUAN 7

## QUEUE & CIRCULAR QUEUE

### 🎯 Tujuan

Mahasiswa mampu mengimplementasikan Queue.

### ✅ Manfaat

Digunakan pada:

* Antrian bank
* Printer queue
* BFS graph

### 📘 Konsep

Queue = FIFO (First In First Out)

Operasi:

* enqueue
* dequeue

### 🧪 Praktikum

* Sistem antrian rumah sakit
* Circular queue dengan array

### 📝 Tugas 2 (Sesuai RPS)

Linked List untuk Stack & Queue

Repo:

```
struktur-data-tugas-2
```

---

# 🔹 PERTEMUAN 8

## UTS

Bentuk:

* Tes coding
* Analisis kompleksitas
* Implementasi struktur data

---

# 🔹 PERTEMUAN 9-10

## TREE

### 🎯 Tujuan

Mahasiswa mampu membuat:

* Binary Tree
* Traversal
* Balanced Tree

### ✅ Manfaat

Digunakan pada:

* Database indexing
* File system
* AI decision tree

### 📘 Konsep

Traversal:

* Preorder
* Inorder
* Postorder

### 🧪 Praktikum

* Bangun binary tree
* Implement traversal
* Hitung tinggi tree

### 📝 Tugas

Implementasi BST + balancing sederhana

---

# 🔹 PERTEMUAN 11

## GRAPH

### 🎯 Tujuan

Mahasiswa mampu membuat graph dan algoritma dasar.

### ✅ Manfaat

Digunakan pada:

* Google Maps
* Social media
* Network

### 📘 Representasi

* Adjacency Matrix
* Adjacency List

### 🧪 Praktikum

* Implement BFS
* Implement DFS

### 📝 Tugas

Buat simulasi pencarian rute sederhana.

---

# 🔹 PERTEMUAN 12-13

## SORTING

### 🎯 Tujuan

Mahasiswa memahami dan membandingkan:

* Bubble
* Selection
* Insertion
* Merge
* Quick Sort

### ✅ Manfaat

Digunakan dalam:

* Database
* Ranking
* Data processing

### 🧪 Praktikum

Bandingkan waktu eksekusi tiap algoritma.

### 📝 Tugas 3 (Sesuai RPS)

Sorting menggunakan Tree

Repo:

```
struktur-data-tugas-3
```

---

# 🔹 PERTEMUAN 14-15

## SEARCHING

### 🎯 Tujuan

Mahasiswa mampu mengimplementasikan:

* Linear Search
* Binary Search
* Hashing

### ✅ Manfaat

Digunakan dalam:

* Sistem login
* Database lookup
* Search engine

### 🧪 Praktikum

* Bandingkan linear vs binary
* Implement hash table sederhana

### 📝 Tugas 4 (Sesuai RPS)

Repo:

```
struktur-data-tugas-4
```

---

# 🔹 PERTEMUAN 16

## UAS (PROYEK BESAR)

Buat:
Sistem Manajemen Data Mahasiswa berbasis CLI

Harus mengandung:

* Linked List
* Stack/Queue
* Tree
* Sorting
* Searching

Upload ke:

```
struktur-data-final-project
```

---

# 📊 SISTEM PENILAIAN (Sesuai RPS) 

| Komponen  | Bobot |
| --------- | ----- |
| Keaktifan | 10%   |
| Tugas     | 35%   |
| Kuis      | 5%    |
| UTS       | 20%   |
| UAS       | 30%   |

---

# 📌 FORMAT WAJIB GITHUB

Setiap mahasiswa wajib:

* 1 Repository per tugas
* README menjelaskan:

  * Konsep
  * Flowchart
  * Analisis kompleksitas
* Minimal 5 commit per tugas
* Gunakan branch develop

