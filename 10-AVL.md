# 📘 MATERI: AVL TREE (BALANCED TREE)

---

# 1. Konsep Dasar AVL Tree

## 🔹 Apa itu AVL Tree?

AVL Tree adalah **Binary Search Tree (BST)** yang selalu dijaga **seimbang (balanced)**.

➡️ Diperkenalkan oleh:

* **Adelson-Velsky dan Landis (1962)**

---

## 🔹 Mengapa Perlu AVL Tree?

Masalah pada BST biasa:

```text
10
  \
   20
     \
      30
        \
         40
```

➡️ Tree menjadi seperti **linked list**
➡️ Kompleksitas berubah dari:

* O(log n) ❌ → O(n)

---

## 🔹 Solusi AVL

AVL Tree menjaga:
[
|tinggi_kiri - tinggi_kanan| \leq 1
]

---

# 2. Konsep Balance Factor

## 🔹 Definisi

[
BF = tinggi(kiri) - tinggi(kanan)
]

---

## 🔹 Nilai yang valid:

* -1 → seimbang
* 0 → seimbang
* +1 → seimbang

---

## 🔹 Tidak seimbang jika:

* BF > 1
* BF < -1

---

## 🔹 Contoh

```text
    30
   /
  20
 /
10
```

* BF(30) = 2 ❌ → perlu rotasi

---

# 3. Jenis Rotasi pada AVL Tree

---

# 🔹 1. LL (Left-Left Case)

## 🔸 Kondisi:

* Node berat di kiri
* Insert di subtree kiri-kiri

---

### Sebelum:

```text
    30
   /
  20
 /
10
```

---

### Setelah (Right Rotation):

```text
    20
   /  \
 10   30
```

---

---

# 🔹 2. RR (Right-Right Case)

## 🔸 Kondisi:

* Node berat di kanan
* Insert di subtree kanan-kanan

---

### Sebelum:

```text
10
  \
   20
     \
      30
```

---

### Setelah (Left Rotation):

```text
    20
   /  \
 10   30
```

---

---

# 🔹 3. LR (Left-Right Case)

## 🔸 Kondisi:

* Berat di kiri
* Insert di subtree kiri-kanan

---

### Sebelum:

```text
    30
   /
  10
    \
     20
```

---

### Proses:

1. Rotasi kiri pada 10
2. Rotasi kanan pada 30

---

### Setelah:

```text
    20
   /  \
 10   30
```

---

---

# 🔹 4. RL (Right-Left Case)

## 🔸 Kondisi:

* Berat di kanan
* Insert di subtree kanan-kiri

---

### Sebelum:

```text
10
  \
   30
  /
 20
```

---

### Proses:

1. Rotasi kanan pada 30
2. Rotasi kiri pada 10

---

### Setelah:

```text
    20
   /  \
 10   30
```

---

# 4. Operasi pada AVL Tree

---

## 🔹 1. Insertion

### Langkah:

1. Insert seperti BST
2. Update height
3. Hitung balance factor
4. Lakukan rotasi jika perlu

---

## 🔹 2. Deletion

Lebih kompleks karena:

* Setelah delete, tree bisa tidak seimbang
* Harus rebalance kembali

---

## 🔹 3. Searching

Sama seperti BST:
[
O(\log n)
]

---

# 5. Kompleksitas AVL Tree

| Operasi | Kompleksitas |
| ------- | ------------ |
| Insert  | O(log n)     |
| Delete  | O(log n)     |
| Search  | O(log n)     |

---

# 6. Implementasi AVL Tree (Python)

---

## 🔹 Struktur Node

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None
        self.height = 1
```

---

## 🔹 Fungsi Pendukung

```python
def height(node):
    return node.height if node else 0

def get_balance(node):
    return height(node.left) - height(node.right)
```

---

## 🔹 Rotasi Kanan

```python
def right_rotate(y):
    x = y.left
    T2 = x.right

    x.right = y
    y.left = T2

    y.height = 1 + max(height(y.left), height(y.right))
    x.height = 1 + max(height(x.left), height(x.right))

    return x
```

---

## 🔹 Rotasi Kiri

```python
def left_rotate(x):
    y = x.right
    T2 = y.left

    y.left = x
    x.right = T2

    x.height = 1 + max(height(x.left), height(x.right))
    y.height = 1 + max(height(y.left), height(y.right))

    return y
```

---

## 🔹 Insert AVL

```python
def insert(node, key):
    if not node:
        return Node(key)

    if key < node.data:
        node.left = insert(node.left, key)
    elif key > node.data:
        node.right = insert(node.right, key)

    node.height = 1 + max(height(node.left), height(node.right))

    balance = get_balance(node)

    # LL
    if balance > 1 and key < node.left.data:
        return right_rotate(node)

    # RR
    if balance < -1 and key > node.right.data:
        return left_rotate(node)

    # LR
    if balance > 1 and key > node.left.data:
        node.left = left_rotate(node.left)
        return right_rotate(node)

    # RL
    if balance < -1 and key < node.right.data:
        node.right = right_rotate(node.right)
        return left_rotate(node)

    return node
```

---

# 7. Studi Kasus

---

## 🎯 Kasus: Sistem Ranking Real-time

Masalah:

* Data terus masuk (nilai mahasiswa)
* Harus selalu terurut
* Harus cepat mencari ranking

---

## 🔹 Solusi:

Gunakan AVL Tree karena:

* Insert cepat (O(log n))
* Search cepat
* Tree selalu seimbang

---

---

## 🎯 Kasus: Database Index

AVL digunakan untuk:

* Index data
* Query cepat

---

# 8. Perbandingan AVL vs BST

| Fitur             | BST        | AVL                  |
| ----------------- | ---------- | -------------------- |
| Balance           | ❌          | ✔                    |
| Search            | O(n) worst | O(log n)             |
| Insert            | Cepat      | Sedikit lebih lambat |
| Kompleksitas kode | Sederhana  | Lebih kompleks       |

---

# 9. Kelebihan & Kekurangan

---

## 🔹 Kelebihan

✔ Selalu seimbang
✔ Performa stabil
✔ Cocok untuk data dinamis

---

## 🔹 Kekurangan

❌ Implementasi kompleks
❌ Overhead rotasi

---

# 🎯 Kesimpulan

* AVL Tree adalah solusi untuk BST yang tidak seimbang
* Menggunakan konsep **balance factor**
* Rotasi adalah kunci utama
* Cocok untuk sistem yang membutuhkan performa stabil

---

# 🧪 Latihan Mahasiswa

1. Implementasikan AVL dari nol
2. Simulasikan semua jenis rotasi
3. Bandingkan AVL vs BST
4. Tambahkan operasi delete
5. Integrasi AVL ke project nyata

