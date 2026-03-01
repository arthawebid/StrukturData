# 📚 PERTEMUAN 4 DOUBLE LINKED LIST & CIRCULAR LINKED LIST

# 1️⃣ Identitas Pertemuan

**Mata Kuliah**: Struktur Data
**Topik**: Double Linked List & Circular Linked List
**Pertemuan ke**: 4
**Waktu**: 1 × 150 menit


# 2️⃣ Capaian Pembelajaran (Sub-CPMK)

Mahasiswa mampu:

1. Menjelaskan perbedaan Single, Double, dan Circular Linked List.
2. Menganalisis kelebihan dan kekurangan masing-masing struktur.
3. Mengimplementasikan Double Linked List.
4. Mengimplementasikan Circular Linked List.
5. Menganalisis kompleksitas waktu operasional.
6. Menentukan struktur yang tepat untuk studi kasus tertentu.

# 3️⃣ Tujuan Pembelajaran

Setelah pertemuan ini mahasiswa mampu:

* Memahami konsep pointer dua arah (prev dan next).
* Memahami konsep struktur melingkar (circular reference).
* Mengimplementasikan operasi insert dan traversal.
* Menjelaskan implikasi kompleksitas waktu dan penggunaan memori.

# 4️⃣ Tinjauan Konseptual

## 🔹 Evolusi Struktur Linked List

1. Single Linked List → satu arah
2. Double Linked List → dua arah
3. Circular Linked List → struktur melingkar

Menurut Introduction to Algorithms, variasi struktur list dikembangkan untuk mengoptimalkan efisiensi traversal dan fleksibilitas manipulasi data.

# 5️⃣ DOUBLE LINKED LIST (DLL)


## 5.1 Definisi

Double Linked List adalah struktur linear dinamis di mana setiap node memiliki dua referensi:

* next → menunjuk ke node berikutnya
* prev → menunjuk ke node sebelumnya

## 5.2 Representasi Konseptual

```
None ← [10] ⇄ [20] ⇄ [30] → None
```

## 5.3 Karakteristik

* Traversal dua arah
* Lebih fleksibel untuk operasi delete
* Membutuhkan memori lebih besar (2 pointer)

## 5.4 Struktur Node DLL (Python)

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
        self.prev = None
```
## 5.5 Struktur Double Linked List

```python
class DoubleLinkedList:
    def __init__(self):
        self.head = None
```
## 5.6 Operasi Insert di Awal (O(1))

```python
def insert_awal(self, data):
    node_baru = Node(data)

    if self.head is not None:
        self.head.prev = node_baru
        node_baru.next = self.head

    self.head = node_baru
```

## 5.7 Operasi Insert di Akhir (O(n))

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
    node_baru.prev = current
```
## 5.8 Traversal Maju dan Mundur

### Traversal Maju

```python
def tampilkan_maju(self):
    current = self.head
    while current:
        print(current.data, end=" <-> ")
        current = current.next
    print("None")
```

### Traversal Mundur

```python
def tampilkan_mundur(self):
    current = self.head
    if current is None:
        return

    while current.next:
        current = current.next

    while current:
        print(current.data, end=" <-> ")
        current = current.prev
    print("None")
```

## 5.9 Analisis Kompleksitas DLL

| Operasi      | Kompleksitas                 |
| ------------ | ---------------------------- |
| Insert Awal  | O(1)                         |
| Insert Akhir | O(n)                         |
| Traversal    | O(n)                         |
| Delete Node  | O(1)* jika pointer diketahui |

# 6️⃣ CIRCULAR LINKED LIST (CLL)

## 6.1 Definisi

Circular Linked List adalah struktur di mana node terakhir menunjuk kembali ke head, membentuk siklus.

## 6.2 Representasi Konseptual

```
[10] → [20] → [30]
  ↑               ↓
  ← ← ← ← ← ← ← ←
```

## 6.3 Karakteristik

* Tidak memiliki nilai None di akhir
* Cocok untuk sistem rotasi
* Harus berhati-hati dalam traversal (hindari infinite loop)

Struktur ini banyak digunakan dalam simulasi sistem penjadwalan seperti Round Robin (lihat pembahasan pada Data Structures and Algorithm Analysis in C).

## 6.4 Struktur Node CLL

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
```
## 6.5 Struktur Circular Linked List

```python
class CircularLinkedList:
    def __init__(self):
        self.head = None
```
## 6.6 Insert di Akhir (O(n))

```python
def insert(self, data):
    node_baru = Node(data)

    if self.head is None:
        self.head = node_baru
        node_baru.next = self.head
        return

    current = self.head
    while current.next != self.head:
        current = current.next

    current.next = node_baru
    node_baru.next = self.head
```
## 6.7 Traversal Circular

```python
def tampilkan(self):
    if self.head is None:
        return

    current = self.head
    while True:
        print(current.data, end=" -> ")
        current = current.next
        if current == self.head:
            break
    print("(kembali ke head)")
```

# 7️⃣ Perbandingan Akademik Struktur

| Aspek        | Single      | Double         | Circular           |
| ------------ | ----------- | -------------- | ------------------ |
| Pointer      | 1           | 2              | 1                  |
| Traversal    | Satu arah   | Dua arah       | Melingkar          |
| Memori       | Lebih hemat | Lebih besar    | Sedang             |
| Implementasi | Mudah       | Lebih kompleks | Butuh kontrol loop |

# 8️⃣ Studi Kasus Akademik

## 🔹 Double Linked List

Kasus:

* Implementasi Undo/Redo pada editor teks
* Navigasi browser (Back & Forward)

## 🔹 Circular Linked List

Kasus:

* Penjadwalan CPU (Round Robin)
* Multiplayer turn-based game
* Sistem playlist lagu

Diskusi kelas:

* Mengapa Circular lebih cocok untuk sistem rotasi?
* Mengapa Double Linked List lebih fleksibel untuk delete?

# 🧪 Praktikum Pertemuan 4

## Latihan 1 (DLL)

Buat program:

* Insert awal
* Insert akhir
* Traversal maju
* Traversal mundur

## Latihan 2 (CLL)

Simulasikan sistem Round Robin:

* Tambah proses
* Tampilkan giliran proses

# 🎯 Mini Project Pertemuan 4

## Project: “Simulasi Sistem Antrian Bank”

### Opsi A – Double Linked List

Fitur:

* Tambah nasabah
* Hapus nasabah tertentu
* Tampilkan maju & mundur

### Opsi B – Circular Linked List

Fitur:

* Tambah nasabah
* Simulasikan pelayanan bergilir

# 📊 Rubrik Penilaian

| Aspek                 | Bobot |
| --------------------- | ----- |
| Implementasi Node     | 15%   |
| Operasi Insert        | 25%   |
| Traversal             | 20%   |
| Logika Circular       | 20%   |
| Analisis Kompleksitas | 20%   |

# 📖 Referensi
1. Introduction to Algorithms
2. Data Structures and Algorithm Analysis in C
