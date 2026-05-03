# 📘 MATERI: AVL TREE (BALANCED TREE)
[Materi Graph](https://notebooklm.google.com/notebook/6bbdcd1d-f5ef-42b4-abd3-bc2714336972/artifact/64c346be-d89c-46c1-ae61-42707c3fc623?utm_source=nlm_web_share&utm_medium=google_oo&utm_campaign=art_share_1&utm_content=&utm_smc=nlm_web_share_google_oo_art_share_1_)

# 1. Konsep Dasar AVL Tree

## 🔹 Apa itu AVL Tree?

AVL Tree adalah **Binary Search Tree (BST)** yang selalu dijaga **seimbang (balanced)**.

➡️ Diperkenalkan oleh:

* **Adelson-Velsky dan Landis (1962)**


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


## 🔹 Solusi AVL

AVL Tree menjaga:
[
|tinggi_kiri - tinggi_kanan| \leq 1
]

# 2. Konsep Balance Factor

## 🔹 Definisi

[
BF = tinggi(kiri) - tinggi(kanan)
]

## 🔹 Nilai yang valid:

* -1 → seimbang
* 0 → seimbang
* +1 → seimbang


## 🔹 Tidak seimbang jika:

* BF > 1
* BF < -1

## 🔹 Contoh

```text
    30
   /
  20
 /
10
```

* BF(30) = 2 ❌ → perlu rotasi


# 3. Jenis Rotasi pada AVL Tree


# 🔹 1. LL (Left-Left Case)

## 🔸 Kondisi:

* Node berat di kiri
* Insert di subtree kiri-kiri


### Sebelum:

```text
    30
   /
  20
 /
10
```

### Setelah (Right Rotation):

```text
    20
   /  \
 10   30
```

# 🔹 2. RR (Right-Right Case)

## 🔸 Kondisi:

* Node berat di kanan
* Insert di subtree kanan-kanan

### Sebelum:

```text
10
  \
   20
     \
      30
```


### Setelah (Left Rotation):

```text
    20
   /  \
 10   30
```


# 🔹 3. LR (Left-Right Case)

## 🔸 Kondisi:

* Berat di kiri
* Insert di subtree kiri-kanan

### Sebelum:

```text
    30
   /
  10
    \
     20
```

### Proses:

1. Rotasi kiri pada 10
2. Rotasi kanan pada 30

### Setelah:

```text
    20
   /  \
 10   30
```

# 🔹 4. RL (Right-Left Case)

## 🔸 Kondisi:

* Berat di kanan
* Insert di subtree kanan-kiri

### Sebelum:

```text
10
  \
   30
  /
 20
```

### Proses:

1. Rotasi kanan pada 30
2. Rotasi kiri pada 10

### Setelah:

```text
    20
   /  \
 10   30
```

# 4. Operasi pada AVL Tree

## 🔹 1. Insertion

### Langkah:

1. Insert seperti BST
2. Update height
3. Hitung balance factor
4. Lakukan rotasi jika perlu

## 🔹 2. Deletion

Lebih kompleks karena:

* Setelah delete, tree bisa tidak seimbang
* Harus rebalance kembali

## 🔹 3. Searching

Sama seperti BST:
[
O(\log n)
]

# 5. Kompleksitas AVL Tree

| Operasi | Kompleksitas |
| ------- | ------------ |
| Insert  | O(log n)     |
| Delete  | O(log n)     |
| Search  | O(log n)     |

# 6. Implementasi AVL Tree (Python)

## 🔹 Struktur Node

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None
        self.height = 1
```

## 🔹 Fungsi Pendukung

```python
def height(node):
    return node.height if node else 0

def get_balance(node):
    return height(node.left) - height(node.right)
```
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

# 7. Studi Kasus

## 🎯 Kasus: Sistem Ranking Real-time

Masalah:

* Data terus masuk (nilai mahasiswa)
* Harus selalu terurut
* Harus cepat mencari ranking

## 🔹 Solusi:

Gunakan AVL Tree karena:

* Insert cepat (O(log n))
* Search cepat
* Tree selalu seimbang

## 🎯 Kasus: Database Index

AVL digunakan untuk:

* Index data
* Query cepat

# 8. Perbandingan AVL vs BST

| Fitur             | BST        | AVL                  |
| ----------------- | ---------- | -------------------- |
| Balance           | ❌          | ✔                    |
| Search            | O(n) worst | O(log n)             |
| Insert            | Cepat      | Sedikit lebih lambat |
| Kompleksitas kode | Sederhana  | Lebih kompleks       |

# 9. Kelebihan & Kekurangan

## 🔹 Kelebihan

✔ Selalu seimbang
✔ Performa stabil
✔ Cocok untuk data dinamis

## 🔹 Kekurangan

❌ Implementasi kompleks
❌ Overhead rotasi

# 🎯 Kesimpulan

* AVL Tree adalah solusi untuk BST yang tidak seimbang
* Menggunakan konsep **balance factor**
* Rotasi adalah kunci utama
* Cocok untuk sistem yang membutuhkan performa stabil

Berikut versi **AVL Tree Visualizer berbasis Streamlit (Python)** — cocok untuk pembelajaran karena mahasiswa bisa **melihat visual + membaca kode Python langsung**.

---

# 🎬 FITUR

* Input angka step-by-step
* Visualisasi AVL Tree (pakai `graphviz`)
* Tampilkan **Balance Factor**
* Deteksi & tampilkan jenis rotasi (LL, RR, LR, RL)
* Mode:
  * Insert manual
  * Auto sequence
* Menampilkan log proses

---

# 📦 INSTALL DEPENDENCY

```bash
pip install streamlit graphviz
```

# 💻 KODE LENGKAP (STREAMLIT)

Simpan sebagai: `avl_streamlit.py`

```python
import streamlit as st
from graphviz import Digraph

# ================= NODE =================
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None
        self.height = 1

# ================= AVL UTIL =================
def height(n):
    return n.height if n else 0

def get_balance(n):
    return height(n.left) - height(n.right) if n else 0

# ================= ROTATIONS =================
def right_rotate(y, logs):
    logs.append("Rotasi Kanan (LL)")
    x = y.left
    T2 = x.right

    x.right = y
    y.left = T2

    y.height = 1 + max(height(y.left), height(y.right))
    x.height = 1 + max(height(x.left), height(x.right))

    return x

def left_rotate(x, logs):
    logs.append("Rotasi Kiri (RR)")
    y = x.right
    T2 = y.left

    y.left = x
    x.right = T2

    x.height = 1 + max(height(x.left), height(x.right))
    y.height = 1 + max(height(y.left), height(y.right))

    return y

# ================= INSERT =================
def insert(node, key, logs):
    if not node:
        return Node(key)

    if key < node.data:
        node.left = insert(node.left, key, logs)
    elif key > node.data:
        node.right = insert(node.right, key, logs)

    node.height = 1 + max(height(node.left), height(node.right))

    balance = get_balance(node)

    # LL
    if balance > 1 and key < node.left.data:
        return right_rotate(node, logs)

    # RR
    if balance < -1 and key > node.right.data:
        return left_rotate(node, logs)

    # LR
    if balance > 1 and key > node.left.data:
        logs.append("Rotasi LR")
        node.left = left_rotate(node.left, logs)
        return right_rotate(node, logs)

    # RL
    if balance < -1 and key < node.right.data:
        logs.append("Rotasi RL")
        node.right = right_rotate(node.right, logs)
        return left_rotate(node, logs)

    return node

# ================= DRAW TREE =================
def draw_tree(node, dot=None):
    if dot is None:
        dot = Digraph()
        dot.attr(bgcolor="#0f172a", fontcolor="white")

    if node:
        bf = get_balance(node)
        label = f"{node.data}\nBF={bf}"

        color = "lightgreen"
        if abs(bf) > 1:
            color = "red"

        dot.node(str(id(node)), label, style="filled", fillcolor=color)

        if node.left:
            dot.edge(str(id(node)), str(id(node.left)))
            draw_tree(node.left, dot)

        if node.right:
            dot.edge(str(id(node)), str(id(node.right)))
            draw_tree(node.right, dot)

    return dot

# ================= STREAMLIT UI =================
st.set_page_config(page_title="AVL Visualizer", layout="wide")

st.title("🌳 AVL Tree Visualizer (Python - Streamlit)")

# Session state
if "root" not in st.session_state:
    st.session_state.root = None
if "logs" not in st.session_state:
    st.session_state.logs = []

# Input
col1, col2 = st.columns(2)

with col1:
    val = st.number_input("Masukkan angka", step=1)

    if st.button("Insert"):
        st.session_state.root = insert(
            st.session_state.root, val, st.session_state.logs
        )

with col2:
    seq = st.text_input("Auto Sequence (contoh: 30,20,10,25)")

    if st.button("Run Sequence"):
        for x in seq.split(","):
            if x.strip():
                st.session_state.root = insert(
                    st.session_state.root, int(x), st.session_state.logs
                )

# Draw tree
st.subheader("Visualisasi Tree")
if st.session_state.root:
    dot = draw_tree(st.session_state.root)
    st.graphviz_chart(dot)
else:
    st.info("Tree masih kosong")

# Logs
st.subheader("Log Proses")
for log in st.session_state.logs[::-1]:
    st.write("•", log)

# Reset
if st.button("Reset Tree"):
    st.session_state.root = None
    st.session_state.logs = []
```

# CARA MENJALANKAN
```bash
streamlit run avl_streamlit.py
```

# 🧪 Latihan Mahasiswa

1. Implementasikan AVL dari nol
2. Simulasikan semua jenis rotasi
3. Bandingkan AVL vs BST
4. Tambahkan operasi delete
5. Integrasi AVL ke project nyata

