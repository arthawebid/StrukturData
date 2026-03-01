# 📚 PERTEMUAN 6 STACK & QUEUE (Implementasi Array dan Linked List)

## 1️⃣ Identitas Pertemuan

**Mata Kuliah**: Struktur Data  
**Topik**: Stack
**Pertemuan ke**: 6   
**Durasi**: 1 × 150 menit  

## 2️⃣ Capaian Pembelajaran (Sub-CPMK)

Mahasiswa mampu:

1. Menjelaskan konsep struktur data Stack dan Queue.
2. Mengimplementasikan Stack menggunakan:

   * Array
   * Linked List
3. Mengimplementasikan Queue menggunakan:

   * Array
   * Linked List
4. Menganalisis kompleksitas operasi dasar.
5. Menentukan struktur yang sesuai untuk studi kasus tertentu.

## 3️⃣ Tujuan Pembelajaran

Setelah pertemuan ini mahasiswa mampu:

* Memahami konsep LIFO dan FIFO.
* Mengimplementasikan push, pop, enqueue, dequeue.
* Menjelaskan perbedaan implementasi array vs linked list.
* Menganalisis kompleksitas waktu dan ruang.

## 4️⃣ STACK

### 🔹 4.1 Definisi

Stack adalah struktur data linear dengan prinsip:

> **LIFO (Last In First Out)**

Elemen terakhir masuk akan pertama keluar.

Konsep ini dijelaskan dalam pembahasan struktur linear pada
Introduction to Algorithms

### 🔹 4.2 Operasi Dasar Stack

| Operasi   | Keterangan               |
| --------- | ------------------------ |
| push(x)   | Menambahkan elemen       |
| pop()     | Menghapus elemen teratas |
| peek()    | Melihat elemen teratas   |
| isEmpty() | Mengecek kosong          |

## 5️⃣ Implementasi Stack dengan Array (Python)

```python
class StackArray:
    def __init__(self):
        self.stack = []

    def push(self, data):
        self.stack.append(data)

    def pop(self):
        if not self.is_empty():
            return self.stack.pop()
        return None

    def peek(self):
        if not self.is_empty():
            return self.stack[-1]
        return None

    def is_empty(self):
        return len(self.stack) == 0
```

Kompleksitas:

* Push → O(1)
* Pop → O(1)

## 6️⃣ Implementasi Stack dengan Linked List

Keunggulan:

* Tidak terbatas kapasitas
* Lebih fleksibel

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class StackLinkedList:
    def __init__(self):
        self.top = None

    def push(self, data):
        node_baru = Node(data)
        node_baru.next = self.top
        self.top = node_baru

    def pop(self):
        if self.top is None:
            return None
        popped = self.top.data
        self.top = self.top.next
        return popped
```

Semua operasi O(1).
