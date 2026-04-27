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

## Simulasi Tree
```bash

<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<title>Tree Visualizer</title>
<style>
    body {
        font-family: Arial;
        text-align: center;
        background: #0f172a;
        color: white;
    }

    button {
        margin: 5px;
        padding: 10px;
        border-radius: 8px;
        border: none;
        cursor: pointer;
        background: #38bdf8;
        color: black;
        font-weight: bold;
    }

    svg {
        width: 100%;
        height: 500px;
        background: #020617;
        margin-top: 20px;
    }

    .node {
        fill: #22c55e;
        stroke: white;
        stroke-width: 2;
    }

    .active {
        fill: #facc15;
    }

    .line {
        stroke: white;
        stroke-width: 2;
    }
</style>
</head>
<body>

<h1>🌳 Tree Visualizer (BST + Balancing)</h1>

<input type="number" id="value" placeholder="Masukkan angka">
<br>

<button onclick="insertNode()">Insert</button>
<button onclick="inorderTraversal()">Inorder</button>
<button onclick="balanceTree()">Balance Tree</button>

<p id="log"></p>

<svg id="canvas"></svg>

<script>
class Node {
    constructor(data) {
        this.data = data;
        this.left = null;
        this.right = null;
        this.x = 0;
        this.y = 0;
    }
}

let root = null;
let svg = document.getElementById("canvas");

function log(msg) {
    document.getElementById("log").innerText = msg;
}

// ================= BST INSERT =================
function insert(root, data) {
    if (!root) return new Node(data);

    if (data < root.data) {
        root.left = insert(root.left, data);
    } else {
        root.right = insert(root.right, data);
    }
    return root;
}

function insertNode() {
    let val = parseInt(document.getElementById("value").value);
    if (isNaN(val)) return;

    root = insert(root, val);
    log("Insert: " + val);

    drawTree();
}

// ================= DRAW TREE =================
function drawTree() {
    svg.innerHTML = "";
    setPosition(root, window.innerWidth / 2, 40, 200);
    drawNode(root);
}

function setPosition(node, x, y, offset) {
    if (!node) return;

    node.x = x;
    node.y = y;

    setPosition(node.left, x - offset, y + 80, offset / 2);
    setPosition(node.right, x + offset, y + 80, offset / 2);
}

function drawNode(node) {
    if (!node) return;

    if (node.left) drawLine(node, node.left);
    if (node.right) drawLine(node, node.right);

    drawCircle(node);

    drawNode(node.left);
    drawNode(node.right);
}

function drawCircle(node) {
    let g = document.createElementNS("http://www.w3.org/2000/svg", "g");

    let circle = document.createElementNS("http://www.w3.org/2000/svg", "circle");
    circle.setAttribute("cx", node.x);
    circle.setAttribute("cy", node.y);
    circle.setAttribute("r", 20);
    circle.setAttribute("class", "node");

    let text = document.createElementNS("http://www.w3.org/2000/svg", "text");
    text.setAttribute("x", node.x);
    text.setAttribute("y", node.y + 5);
    text.setAttribute("text-anchor", "middle");
    text.setAttribute("fill", "black");
    text.textContent = node.data;

    g.appendChild(circle);
    g.appendChild(text);
    svg.appendChild(g);
}

function drawLine(parent, child) {
    let line = document.createElementNS("http://www.w3.org/2000/svg", "line");
    line.setAttribute("x1", parent.x);
    line.setAttribute("y1", parent.y);
    line.setAttribute("x2", child.x);
    line.setAttribute("y2", child.y);
    line.setAttribute("class", "line");

    svg.appendChild(line);
}

// ================= INORDER =================
function inorderTraversal() {
    let result = [];
    inorder(root, result);
    log("Inorder: " + result.join(", "));
}

function inorder(node, arr) {
    if (!node) return;
    inorder(node.left, arr);
    arr.push(node.data);
    inorder(node.right, arr);
}

// ================= BALANCING =================
function storeInorder(node, arr) {
    if (!node) return;
    storeInorder(node.left, arr);
    arr.push(node.data);
    storeInorder(node.right, arr);
}

function buildBalanced(arr, start, end) {
    if (start > end) return null;

    let mid = Math.floor((start + end) / 2);
    let node = new Node(arr[mid]);

    node.left = buildBalanced(arr, start, mid - 1);
    node.right = buildBalanced(arr, mid + 1, end);

    return node;
}

function balanceTree() {
    let arr = [];
    storeInorder(root, arr);

    root = buildBalanced(arr, 0, arr.length - 1);

    log("Tree berhasil di-balance!");
    drawTree();
}
</script>

</body>
</html>
```
