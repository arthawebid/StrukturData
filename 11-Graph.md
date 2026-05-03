# 📘 MATERI LANJUTAN: GRAPH (TINGKAT LANJUT)

# 1. 🔹 Definisi Formal Graph

Graph didefinisikan sebagai:

$G = (V, E)$

* **V (Vertex)**: himpunan simpul
* **E (Edge)**: himpunan sisi (relasi)

---

# 2. 🔹 Terminologi Lanjutan

* **Degree (derajat)**: jumlah edge pada node
* **In-degree / Out-degree** (digraph)
* **Path length**: panjang jalur
* **Simple path**: tanpa node berulang
* **Cycle**: jalur kembali ke awal
* **Connected component**
* **Strongly Connected Component (SCC)**
* **Cut vertex / articulation point**

---

# 3. 🔹 Representasi Graph (Analisis Mendalam)

---

## 🔸 Adjacency Matrix

$A[i][j] = 1 \text{ jika ada edge}$

### Kompleksitas:

* Space: O(V²)
* Edge check: O(1)

✔ cepat cek koneksi
❌ boros memori

---

## 🔸 Adjacency List

```python
A: B, C
B: A, D
```

### Kompleksitas:

* Space: O(V + E)
* Iterasi: efisien

✔ paling umum digunakan

---

## 🔸 Edge List

```python
[(A,B), (A,C), (B,D)]
```

✔ sederhana
❌ kurang efisien untuk traversal

---

# 4. 🔹 Jenis Graph (Detail)

---

## 🔸 Directed vs Undirected

* Directed: (u → v)
* Undirected: (u — v)

---

## 🔸 Weighted Graph

* Edge memiliki bobot (cost, distance)

---

## 🔸 Dense vs Sparse

* Dense: banyak edge
* Sparse: sedikit edge

---

## 🔸 DAG (Directed Acyclic Graph)

* Tidak ada cycle
* Penting untuk dependency system

---

# 5. 🔹 Algoritma Traversal

---

# 🔥 BFS (Breadth First Search)

## 🔸 Konsep:

Menjelajah per level (queue)

## 🔸 Kompleksitas:

$O(V + E)$

---

## 🔸 Kegunaan:

* Shortest path (unweighted)
* Social network
* Broadcast system

---

# 🔥 DFS (Depth First Search)

## 🔸 Konsep:

Masuk sedalam mungkin (stack/rekursi)

---

## 🔸 Kegunaan:

* Deteksi cycle
* Topological sort
* SCC

---

# 6. 🔹 Algoritma Penting Lanjutan

---

# 🔹 Dijkstra (Shortest Path)

## 🔸 Digunakan untuk:

* Graph berbobot positif

## 🔸 Kompleksitas:

$O((V + E)\log V)$

---

# 🔹 Floyd-Warshall

* Semua pasangan shortest path
* Kompleksitas:
  $(n^3)$

---

# 🔹 Minimum Spanning Tree (MST)

---

## 🔸 Kruskal

* Greedy + Union Find

---

## 🔸 Prim

* Mirip Dijkstra

---

# 🔹 Topological Sort

* Hanya untuk DAG
* Mengurutkan dependency

---

# 🔹 Cycle Detection

* DFS (back edge)
* Union-Find

---

# 7. 🔹 Studi Kasus Kompleks

---

## 🎯 Kasus 1: Google Maps

* Node: lokasi
* Edge: jalan
* Algoritma: Dijkstra

---

## 🎯 Kasus 2: Sistem Akademik

* Graph dependency mata kuliah
* Gunakan Topological Sort

---

## 🎯 Kasus 3: Social Network

* BFS untuk rekomendasi teman

---

# 8. 🔥 DEMO STREAMLIT (INTERAKTIF)

Mahasiswa bisa:

* Input graph
* Pilih BFS / DFS
* Lihat hasil traversal
* Visualisasi graph

---

# 📦 INSTALL

```bash
pip install streamlit networkx matplotlib
```

---

# 💻 KODE STREAMLIT GRAPH VISUALIZER

Simpan: `graph_streamlit.py`

```python
import streamlit as st
import networkx as nx
import matplotlib.pyplot as plt
from collections import deque

st.set_page_config(layout="wide")

st.title("📊 Graph Visualizer (BFS & DFS)")

# ================= INPUT =================
st.sidebar.header("Input Graph")

edges_input = st.sidebar.text_area(
    "Masukkan edges (format: A-B, A-C, B-D)",
    "A-B,A-C,B-D,C-D"
)

algo = st.sidebar.selectbox("Pilih Algoritma", ["BFS", "DFS"])

start_node = st.sidebar.text_input("Start Node", "A")

# ================= BUILD GRAPH =================
G = nx.Graph()

edges = edges_input.split(",")

for edge in edges:
    if "-" in edge:
        u, v = edge.strip().split("-")
        G.add_edge(u, v)

# ================= VISUAL =================
col1, col2 = st.columns(2)

with col1:
    st.subheader("Visualisasi Graph")

    fig, ax = plt.subplots()
    pos = nx.spring_layout(G)

    nx.draw(G, pos, with_labels=True, node_color="lightblue", ax=ax)

    st.pyplot(fig)

# ================= ALGORITHM =================
def bfs(graph, start):
    visited = []
    queue = deque([start])

    while queue:
        node = queue.popleft()
        if node not in visited:
            visited.append(node)
            queue.extend(graph[node])

    return visited

def dfs(graph, node, visited=None):
    if visited is None:
        visited = []
    visited.append(node)

    for neighbor in graph[node]:
        if neighbor not in visited:
            dfs(graph, neighbor, visited)

    return visited

# ================= EXECUTION =================
with col2:
    st.subheader("Hasil Traversal")

    adj_list = {n: list(G.neighbors(n)) for n in G.nodes()}

    if algo == "BFS":
        result = bfs(adj_list, start_node)
    else:
        result = dfs(adj_list, start_node)

    st.write("Traversal:", " → ".join(result))

    st.subheader("Adjacency List")
    st.write(adj_list)
```

---

# ▶️ CARA MENJALANKAN

```bash
streamlit run graph_streamlit.py
```

# 🎯 KESIMPULAN

* Graph adalah struktur paling fleksibel
* Digunakan di hampir semua sistem modern
* BFS & DFS adalah dasar
* Dijkstra & MST adalah lanjutan penting
* Visualisasi sangat membantu pemahaman

## GRAPH AI RECOMMENDATION SYSTEM

---

# 1. 🔹 Konsep Dasar

## 🔸 Apa itu Recommendation System?

Sistem yang memberikan rekomendasi berdasarkan:

* preferensi user
* hubungan antar data

---

## 🔸 Kenapa pakai Graph?

Graph sangat cocok karena:

* relasi kompleks (user ↔ item ↔ kategori)
* fleksibel (multi relasi)
* mudah dikembangkan ke AI (Graph ML)

---

## 🔸 Representasi Graph

Misalnya:

```text
User ---likes---> Item
User ---friend---> User
Item ---category---> Category
```

---

## 🔸 Contoh Nyata

* Netflix (film recommendation)
* Tokopedia / Shopee (produk)
* Spotify (musik)
* LinkedIn (connection suggestion)

---

# 2. 🔹 Model Graph Recommendation

---

## 🔸 1. Content-Based Filtering

* Berdasarkan kemiripan item
* Graph: Item ↔ fitur

---

## 🔸 2. Collaborative Filtering

* Berdasarkan user lain
* Graph: User ↔ User ↔ Item

---

## 🔸 3. Hybrid (Paling kuat)

* Gabungan keduanya

---

# 3. 🔹 Algoritma Graph untuk Recommendation

---

## 🔥 1. BFS Recommendation

Cari node terdekat (friend-of-friend)

---

## 🔥 2. Similarity (Cosine / Jaccard)

$Similarity(A,B) = \frac{|A \cap B|}{|A \cup B|}$

---

## 🔥 3. PageRank (Advanced)

* Menilai “kepentingan” node

---

## 🔥 4. Personalized Recommendation

* Graph traversal + scoring

---

# 4. 🔹 Studi Kasus

---

## 🎯 Kasus: Rekomendasi Produk

Graph:

```text
User A → membeli → Laptop
User B → membeli → Laptop
User B → membeli → Mouse
```

➡️ Rekomendasi untuk A:
👉 Mouse

---

# 5. 🔥 IMPLEMENTASI STREAMLIT (INTERAKTIF)

Mahasiswa bisa:

* Input data user-item
* Lihat graph
* Generate rekomendasi otomatis

---

# 📦 INSTALL

```bash
pip install streamlit networkx matplotlib
```

---

# 💻 KODE: graph_recommendation.py

```python
import streamlit as st
import networkx as nx
import matplotlib.pyplot as plt

st.set_page_config(layout="wide")

st.title("🤖 Graph AI Recommendation System")

# ================= INPUT =================
st.sidebar.header("Input Data")

data_input = st.sidebar.text_area(
    "Format: user-item (contoh: A-Laptop,A-HP,B-Laptop,B-Mouse)",
    "A-Laptop,A-HP,B-Laptop,B-Mouse,C-HP,C-Tablet"
)

target_user = st.sidebar.text_input("Target User", "A")

# ================= BUILD GRAPH =================
G = nx.Graph()

pairs = data_input.split(",")

user_items = {}

for pair in pairs:
    u, i = pair.strip().split("-")

    G.add_node(u, type="user")
    G.add_node(i, type="item")

    G.add_edge(u, i)

    if u not in user_items:
        user_items[u] = set()
    user_items[u].add(i)

# ================= VISUAL =================
col1, col2 = st.columns(2)

with col1:
    st.subheader("Graph")

    pos = nx.spring_layout(G)
    fig, ax = plt.subplots()

    colors = []
    for node in G.nodes():
        if node in user_items:
            colors.append("lightblue")
        else:
            colors.append("lightgreen")

    nx.draw(G, pos, with_labels=True, node_color=colors, ax=ax)

    st.pyplot(fig)

# ================= RECOMMENDATION =================
def recommend(user):
    if user not in user_items:
        return []

    recommendations = set()

    for other_user in user_items:
        if other_user == user:
            continue

        # cek kesamaan
        common = user_items[user].intersection(user_items[other_user])

        if len(common) > 0:
            for item in user_items[other_user]:
                if item not in user_items[user]:
                    recommendations.add(item)

    return list(recommendations)

with col2:
    st.subheader("Recommendation Result")

    recs = recommend(target_user)

    if recs:
        st.success(f"Rekomendasi untuk {target_user}: {', '.join(recs)}")
    else:
        st.warning("Tidak ada rekomendasi")

    st.subheader("User-Item Mapping")
    st.write(user_items)
```

---

# ▶️ CARA MENJALANKAN

```bash
streamlit run graph_recommendation.py
```


# 6. 🔹 PENJELASAN LOGIKA AI

## 🔸 Cara sistem berpikir:

1. Cari user lain yang punya item sama
2. Ambil item lain dari mereka
3. Filter yang belum dimiliki user

---

## 🔸 Ini disebut:

👉 **Collaborative Filtering berbasis Graph**

---

# 7. 🔥 UPGRADE (LEVEL AI SESUNGGUHNYA)

---

## 🔹 Tambahkan Scoring

```python
score = jumlah_kemiripan
```

---

## 🔹 Gunakan Jaccard Similarity

$\frac{|A \cap B|}{|A \cup B|}$

---

## 🔹 Gunakan PageRank

```python
nx.pagerank(G)
```

---

## 🔹 Gunakan Graph Neural Network (GNN)

* Deep learning pada graph

---

# 8. 🔹 Pengembangan Project Mahasiswa

---

## 🎓 Ide Project:

* Sistem rekomendasi buku
* Rekomendasi mata kuliah
* Rekomendasi teman
* Rekomendasi film

---

# 🎯 KESIMPULAN

* Graph sangat powerful untuk AI
* Recommendation system berbasis graph:

  * fleksibel
  * scalable
* Digunakan di industri besar
* Mudah dikembangkan ke AI lanjutan


