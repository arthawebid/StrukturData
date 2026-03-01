# 7️⃣ QUEUE

## 🔹 1 Definisi

Queue adalah struktur data linear dengan prinsip:

> **FIFO (First In First Out)**

Elemen pertama masuk akan pertama keluar.

Dijelaskan dalam literatur klasik struktur data seperti
Data Structures and Algorithm Analysis in C

## 🔹 2 Operasi Dasar Queue

| Operasi    | Keterangan         |
| ---------- | ------------------ |
| enqueue(x) | Tambah elemen      |
| dequeue()  | Hapus elemen depan |
| front()    | Lihat elemen depan |
| isEmpty()  | Cek kosong         |

## Implementasi Queue dengan Array

```python
class QueueArray:
    def __init__(self):
        self.queue = []

    def enqueue(self, data):
        self.queue.append(data)

    def dequeue(self):
        if not self.is_empty():
            return self.queue.pop(0)
        return None

    def is_empty(self):
        return len(self.queue) == 0
```

Catatan:

* dequeue() menggunakan pop(0) → O(n)

## Implementasi Queue dengan Linked List (Optimal)

Menggunakan head dan tail pointer.

```python
class QueueLinkedList:
    def __init__(self):
        self.front = None
        self.rear = None

    def enqueue(self, data):
        node_baru = Node(data)
        if self.rear is None:
            self.front = self.rear = node_baru
            return
        self.rear.next = node_baru
        self.rear = node_baru

    def dequeue(self):
        if self.front is None:
            return None
        temp = self.front
        self.front = self.front.next
        if self.front is None:
            self.rear = None
        return temp.data
```

Kompleksitas:

* Enqueue → O(1)
* Dequeue → O(1)

## Perbandingan Implementasi

| Struktur    | Insert | Delete | Catatan       |
| ----------- | ------ | ------ | ------------- |
| Stack Array | O(1)   | O(1)   | Sederhana     |
| Stack LL    | O(1)   | O(1)   | Fleksibel     |
| Queue Array | O(1)   | O(n)   | Tidak efisien |
| Queue LL    | O(1)   | O(1)   | Optimal       |

## Studi Kasus

### 🔹 Stack

* Undo/Redo
* Evaluasi ekspresi postfix
* Validasi tanda kurung

## 🔹 Queue

* Sistem antrian bank
* Printer job scheduling
* BFS pada graph


# 📊 Rubrik Penilaian

| Aspek                 | Bobot |
| --------------------- | ----- |
| Implementasi Struktur | 30%   |
| Operasi Dasar         | 30%   |
| Studi Kasus           | 20%   |
| Analisis Kompleksitas | 20%   |

# 📌 Penutup Akademik

Pada tahap ini mahasiswa telah memahami:

* Linked List
* Stack
* Queue
* Implementasi berbasis array dan pointer

* Hash Table
* Tree Structure
