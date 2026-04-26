# 📘 MATERI: STRUKTUR DATA TREE

## 1. Konsep dan Jenis-Jenis Struktur Data Tree

### 🔹 Konsep Dasar Tree

Tree adalah struktur data non-linear yang terdiri dari node-node yang saling terhubung dalam bentuk hierarki.

**Istilah penting:**

* **Node**: elemen data
* **Root**: node paling atas
* **Parent & Child**: hubungan antar node
* **Leaf**: node tanpa anak
* **Subtree**: bagian dari tree
* **Height (tinggi)**: jumlah level maksimum
* **Depth**: jarak node dari root

### 🔹 Karakteristik Tree

* Tidak memiliki siklus (acyclic)
* Memiliki satu root
* Setiap node (kecuali root) punya satu parent

---

### 🔹 Jenis-Jenis Tree

#### 1. General Tree

* Tidak ada batasan jumlah anak
* Struktur fleksibel

#### 2. Binary Tree

* Maksimal 2 anak (left & right)

**Jenis Binary Tree:**

* Full Binary Tree (setiap node punya 0 atau 2 anak)
* Complete Binary Tree (terisi penuh kecuali level terakhir)
* Perfect Binary Tree (semua level penuh)
* Skewed Tree (condong ke satu sisi)

#### 3. Binary Search Tree (BST)

* Kiri < Root < Kanan
* Digunakan untuk pencarian cepat

#### 4. AVL Tree (Balanced Tree)

* Selisih tinggi kiri dan kanan maksimal 1

#### 5. Heap Tree

* Min Heap / Max Heap
* Digunakan dalam priority queue

---

## 2. Pemanfaatan Struktur Data Tree

Tree digunakan luas dalam berbagai bidang:

### 🔹 Contoh Penggunaan:

* **File System** → struktur folder (hierarki)
* **Database Indexing** → B-Tree, B+ Tree
* **Artificial Intelligence** → decision tree
* **Compiler** → syntax tree
* **Networking** → routing tree
* **Game Development** → behavior tree
* **Machine Learning** → decision tree & random forest

---

## 3. Implementasi Struktur Data Tree (Python)

### 🔹 Contoh Binary Tree Sederhana

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None

# Membuat tree
root = Node(10)
root.left = Node(5)
root.right = Node(15)
```

---

### 🔹 Traversal Tree

#### 1. Preorder (Root - Left - Right)

```python
def preorder(node):
    if node:
        print(node.data, end=" ")
        preorder(node.left)
        preorder(node.right)
```

#### 2. Inorder (Left - Root - Right)

```python
def inorder(node):
    if node:
        inorder(node.left)
        print(node.data, end=" ")
        inorder(node.right)
```

#### 3. Postorder (Left - Right - Root)

```python
def postorder(node):
    if node:
        postorder(node.left)
        postorder(node.right)
        print(node.data, end=" ")
```

---

### 🔹 Implementasi Binary Search Tree (BST)

```python
def insert(root, data):
    if root is None:
        return Node(data)
    if data < root.data:
        root.left = insert(root.left, data)
    else:
        root.right = insert(root.right, data)
    return root
```

---

## 4. Konsep dan Logika Balanced Tree

### 🔹 Apa itu Balanced Tree?

Tree dikatakan **balanced** jika tinggi subtree kiri dan kanan tidak berbeda jauh.

### 🔹 Kenapa penting?

* Mencegah tree menjadi **linked list**
* Menjaga performa operasi tetap:

  * Search: O(log n)
  * Insert: O(log n)
  * Delete: O(log n)

---

### 🔹 Masalah pada Tree Tidak Seimbang

Contoh:

```
10
  \
   20
     \
      30
        \
         40
```

➡️ Ini menjadi seperti linked list → performa O(n)

---

### 🔹 Balance Factor (AVL Tree)

[
BF = tinggi(kiri) - tinggi(kanan)
]

Nilai yang diperbolehkan:

* -1, 0, +1 → seimbang

---

### 🔹 Rotasi pada Balanced Tree

#### 1. Rotasi Kanan (Right Rotation)

#### 2. Rotasi Kiri (Left Rotation)

#### 3. Left-Right Rotation

#### 4. Right-Left Rotation

---

## 5. Implementasi & Konversi Tree menjadi Balanced Tree

### 🔹 Strategi Umum

#### Cara 1: Menggunakan AVL Tree (Self-balancing)

* Otomatis melakukan rotasi saat insert/delete

#### Cara 2: Konversi dari BST ke Balanced Tree

### Langkah:

1. Simpan node dalam array (inorder traversal)
2. Bangun ulang tree dari array (divide & conquer)

---

### 🔹 Contoh Konversi

#### Step 1: Simpan ke array

```python
def store_inorder(root, arr):
    if root:
        store_inorder(root.left, arr)
        arr.append(root.data)
        store_inorder(root.right, arr)
```

---

#### Step 2: Bangun Balanced Tree

```python
def build_balanced(arr, start, end):
    if start > end:
        return None

    mid = (start + end) // 2
    node = Node(arr[mid])

    node.left = build_balanced(arr, start, mid - 1)
    node.right = build_balanced(arr, mid + 1, end)

    return node
```

---

#### Step 3: Fungsi Utama

```python
def balance_bst(root):
    arr = []
    store_inorder(root, arr)
    return build_balanced(arr, 0, len(arr) - 1)
```

---

## 🎯 Kesimpulan

* Tree adalah struktur data penting berbasis hierarki
* BST mempermudah pencarian, tapi bisa tidak efisien jika tidak seimbang
* Balanced Tree menjaga performa optimal
* AVL Tree adalah contoh self-balancing tree
* Konversi ke balanced tree dapat dilakukan dengan teknik traversal + rebuild

---

## 📌 Latihan (Opsional untuk Mahasiswa)

1. Buat program BST dan tampilkan traversalnya
2. Simulasikan tree yang tidak seimbang
3. Implementasikan fungsi balance tree
4. Bandingkan waktu pencarian sebelum & sesudah balancing
5. Implementasikan AVL Tree lengkap (dengan rotasi)

---

Kalau mau, saya bisa bantu:

* 🔥 Versi **slide PPT siap mengajar**
* 🎥 Animasi visual step-by-step (HTML/JS)
* 🧪 Soal kuis + auto grading
* 💻 Project mini (Tree Visualizer interaktif)

Tinggal bilang saja 👍
