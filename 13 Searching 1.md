# Materi Perkuliahan Struktur Data

## Sub Materi: Searching (Pencarian Data)

---

# Identitas Mata Kuliah

* Mata Kuliah : Struktur Data
* Sub Materi : Searching
* Pertemuan : Searching pada Struktur Data
* Target Pembelajaran : Mahasiswa memahami konsep pencarian data, jenis-jenis algoritma searching, implementasi, analisis kompleksitas, serta penerapannya pada sistem nyata.

---

# Capaian Pembelajaran

Mahasiswa mampu:

1. Memahami konsep dasar searching.
2. Menjelaskan perbedaan sequential dan binary search.
3. Mengimplementasikan algoritma searching.
4. Menganalisis kompleksitas algoritma pencarian.
5. Memilih algoritma searching yang sesuai.
6. Mengimplementasikan searching pada studi kasus nyata.

---

# Pendahuluan

Searching (pencarian) adalah proses menemukan data tertentu di dalam kumpulan data.

Searching merupakan salah satu operasi paling penting dalam struktur data karena hampir seluruh aplikasi komputer memerlukan proses pencarian data.

Contoh penggunaan searching:

* Pencarian kontak pada smartphone
* Pencarian data mahasiswa
* Mesin pencari (search engine)
* Pencarian produk e-commerce
* Sistem rekomendasi
* Database management system
* GPS dan navigasi

---

# Konsep Dasar Searching

## Tujuan Searching

Mencari:

* posisi data
* keberadaan data
* nilai tertentu
* hubungan data

---

# Jenis-Jenis Searching

Secara umum searching dibagi menjadi:

1. Sequential Search (Linear Search)
2. Binary Search
3. Interpolation Search
4. Jump Search
5. Hashing Search
6. Tree Search
7. Graph Search

Pada perkuliahan dasar, fokus utama adalah:

* Sequential Search
* Binary Search

---

# 1. Sequential Search (Linear Search)

## Pengertian

Sequential Search adalah metode pencarian dengan memeriksa data satu per satu dari awal hingga akhir.

---

# Ilustrasi

Data:

```text
[12, 7, 25, 9, 30]
```

Mencari nilai 9:

```text
12 → bukan
7  → bukan
25 → bukan
9  → ditemukan
```

---

# Algoritma Sequential Search

1. Mulai dari indeks pertama.
2. Bandingkan data dengan key.
3. Jika sama → ditemukan.
4. Jika tidak → lanjut ke data berikutnya.
5. Berhenti ketika data ditemukan atau data habis.

---
```text
# Flowchart Sequential Search

Mulai
  ↓
Input Data dan Key
  ↓
Bandingkan Data[i] dengan Key
  ↓
Apakah Sama?
 ├── Ya → Data Ditemukan
 └── Tidak → i + 1
  ↓
Apakah Data Habis?
 ├── Ya → Data Tidak Ditemukan
 └── Tidak → Ulangi
```
---

# Implementasi Sequential Search (Python)

```python

def sequential_search(data, key):
    for i in range(len(data)):
        if data[i] == key:
            return i
    return -1

angka = [12, 7, 25, 9, 30]

hasil = sequential_search(angka, 9)

if hasil != -1:
    print("Data ditemukan pada indeks", hasil)
else:
    print("Data tidak ditemukan")
```

---



---

# Kelebihan Sequential Search

* Mudah diimplementasikan
* Tidak memerlukan data terurut
* Cocok untuk data kecil

---

# Kekurangan Sequential Search

* Lambat untuk data besar
* Harus memeriksa satu per satu
* Tidak efisien

---

# Kompleksitas Sequential Search

| Kondisi      | Kompleksitas |
| ------------ | ------------ |
| Best Case    | O(1)         |
| Average Case | O(n)         |
| Worst Case   | O(n)         |

---

# 2. Binary Search

## Pengertian

Binary Search adalah algoritma pencarian dengan membagi data menjadi dua bagian secara berulang.

Syarat utama:

## Data HARUS terurut.

---

# Ilustrasi Binary Search

Data:

```text
[2, 5, 8, 12, 16, 23, 38, 56]
```

Mencari nilai 23.

Langkah:

```text
Tengah = 12
23 > 12 → cari kanan

Tengah = 23
Ditemukan
```

---

# Cara Kerja Binary Search

1. Tentukan indeks tengah.
2. Bandingkan nilai tengah dengan key.
3. Jika sama → ditemukan.
4. Jika key lebih kecil → cari kiri.
5. Jika key lebih besar → cari kanan.
6. Ulangi hingga ditemukan.

---

# Flowchart Binary Search

```text
Mulai
  ↓
Input Data Terurut
  ↓
Tentukan Mid
  ↓
Bandingkan Data[mid] dengan Key
  ↓
Apakah Sama?
 ├── Ya → Ditemukan
 └── Tidak
       ↓
Key < Mid ?
 ├── Ya → Cari Kiri
 └── Tidak → Cari Kanan
```

---

# Implementasi Binary Search (Python)

```python

def binary_search(data, key):
    kiri = 0
    kanan = len(data) - 1

    while kiri <= kanan:
        tengah = (kiri + kanan) // 2

        if data[tengah] == key:
            return tengah

        elif data[tengah] < key:
            kiri = tengah + 1

        else:
            kanan = tengah - 1

    return -1

angka = [2, 5, 8, 12, 16, 23, 38, 56]

hasil = binary_search(angka, 23)

if hasil != -1:
    print("Data ditemukan pada indeks", hasil)
else:
    print("Data tidak ditemukan")
```

---

---

# Kelebihan Binary Search

* Sangat cepat
* Efisien untuk data besar
* Kompleksitas kecil

---

# Kekurangan Binary Search

* Data harus terurut
* Implementasi lebih kompleks

---

# Kompleksitas Binary Search

| Kondisi      | Kompleksitas |
| ------------ | ------------ |
| Best Case    | O(1)         |
| Average Case | O(log n)     |
| Worst Case   | O(log n)     |

---

# Perbandingan Sequential dan Binary Search

| Aspek        | Sequential Search | Binary Search  |
| ------------ | ----------------- | -------------- |
| Data Terurut | Tidak wajib       | Wajib          |
| Kecepatan    | Lambat            | Cepat          |
| Kompleksitas | O(n)              | O(log n)       |
| Implementasi | Mudah             | Lebih kompleks |
| Cocok Untuk  | Data kecil        | Data besar     |

---

# Visualisasi Perbandingan

## Sequential Search

```text
1 → 2 → 3 → 4 → 5 → 6
```

Memeriksa satu per satu.

---

## Binary Search

```text
1 2 3 4 5 6 7 8
        ↑
      Tengah
```

Membagi data menjadi dua.

---

# Searching pada Struktur Data Lain

## Searching pada Array

* Sequential Search
* Binary Search

---

## Searching pada Linked List

Umumnya menggunakan:

* Sequential Search

Karena linked list tidak memiliki indeks langsung.

---

## Searching pada Tree

Menggunakan:

* DFS
* BFS
* Binary Search Tree

---

## Searching pada Graph

Menggunakan:

* Breadth First Search (BFS)
* Depth First Search (DFS)

---

# Searching pada Dunia Nyata

## Mesin Pencari

Google menggunakan searching sangat kompleks untuk menemukan halaman web.

---

## Database

SQL menggunakan indexing dan searching.

---

## E-Commerce

Shopee dan Tokopedia menggunakan searching produk.

---

## Media Sosial

Searching teman dan postingan.

---

## Artificial Intelligence

AI menggunakan searching pada:

* pathfinding
* recommendation system
* graph traversal
* optimization

---

# Studi Kasus

## Kasus 1

Cari angka 45 pada data:

```text
[10, 20, 30, 45, 50]
```

Menggunakan:

* Sequential Search
* Binary Search

Bandingkan jumlah langkah.

---

# Analisis Kompleksitas

## Mengapa Binary Search Lebih Cepat?

Karena setiap langkah mengurangi data menjadi setengah.

Contoh:

| Jumlah Data | Sequential     | Binary     |
| ----------- | -------------- | ---------- |
| 1000        | 1000 langkah   | 10 langkah |
| 1 juta      | 1 juta langkah | 20 langkah |

---

# Kesalahan Umum Penggunaan

## Sequential Search

* Lupa return
* Salah perulangan
* Salah kondisi

---

## Binary Search

* Data belum sorting
* Salah menghitung middle
* Infinite loop
* Salah update kiri dan kanan

---

# Praktikum

## Latihan 1

Buat program Sequential Search untuk mencari nama mahasiswa.

---

## Latihan 2

Buat program Binary Search untuk mencari angka.

---

## Latihan 3

Bandingkan waktu Sequential dan Binary Search.

---

## Latihan 4

Buat visualisasi searching menggunakan:

* Python
* Streamlit

---

# Mini Project

## DSS Pencarian Buku Perpustakaan

Fitur:

* Input buku
* Searching judul
* Searching penulis
* Sorting data
* Binary Search
* Interface GUI

---

# Rangkuman

## Sequential Search

* Mudah
* Tidak perlu sorting
* Lambat

---

## Binary Search

* Cepat
* Efisien
* Wajib sorting

---

# Kesimpulan

Searching merupakan operasi penting dalam struktur data.

Pemilihan algoritma searching yang tepat akan mempengaruhi:

* performa sistem
* efisiensi program
* penggunaan memori
* kecepatan aplikasi

Sequential Search cocok untuk data kecil dan sederhana.

Binary Search cocok untuk data besar yang sudah terurut.


```bash
import streamlit as st
import time

st.set_page_config(page_title="Searching Visualizer", layout="wide")

st.title("🔍 Searching Algorithm Visualizer")
st.markdown("Implementasi Sequential Search dan Binary Search menggunakan Python + Streamlit")

# =========================
# INPUT DATA
# =========================

st.header("Input Data")

input_data = st.text_input(
    "Masukkan data angka dipisahkan koma",
    "12,7,25,9,30,45,18"
)

search_key = st.number_input("Masukkan angka yang dicari", value=9)

algoritma = st.selectbox(
    "Pilih Algoritma",
    ["Sequential Search", "Binary Search"]
)

speed = st.slider("Kecepatan Visualisasi", 0.1, 2.0, 0.5)

# =========================
# PARSE DATA
# =========================

try:
    data = [int(x.strip()) for x in input_data.split(",")]
except:
    st.error("Input data tidak valid")
    st.stop()

# =========================
# VISUALISASI DATA
# =========================

st.header("Data")

cols = st.columns(len(data))

for i, val in enumerate(data):
    cols[i].metric(f"Index {i}", val)

# =========================
# SEQUENTIAL SEARCH
# =========================

def sequential_search(data, key):

    visual = st.empty()
    info = st.empty()

    for i in range(len(data)):

        cols = visual.columns(len(data))

        for j, val in enumerate(data):

            if j == i:
                cols[j].success(val)
            else:
                cols[j].metric(f"{j}", val)

        info.info(f"Mengecek index {i} dengan nilai {data[i]}")

        time.sleep(speed)

        if data[i] == key:
            info.success(f"Data ditemukan pada index {i}")
            return i

    info.error("Data tidak ditemukan")
    return -1

# =========================
# BINARY SEARCH
# =========================

def binary_search(data, key):

    data = sorted(data)

    st.subheader("Data Setelah Sorting")

    cols = st.columns(len(data))

    for i, val in enumerate(data):
        cols[i].metric(f"{i}", val)

    kiri = 0
    kanan = len(data) - 1

    visual = st.empty()
    info = st.empty()

    while kiri <= kanan:

        tengah = (kiri + kanan) // 2

        cols = visual.columns(len(data))

        for i, val in enumerate(data):

            if i == tengah:
                cols[i].success(val)
            elif i >= kiri and i <= kanan:
                cols[i].warning(val)
            else:
                cols[i].metric(f"{i}", val)

        info.info(
            f"Kiri={kiri}, Tengah={tengah}, Kanan={kanan}"
        )

        time.sleep(speed)

        if data[tengah] == key:
            info.success(f"Data ditemukan pada index {tengah}")
            return tengah

        elif data[tengah] < key:
            kiri = tengah + 1

        else:
            kanan = tengah - 1

    info.error("Data tidak ditemukan")
    return -1

# =========================
# EKSEKUSI
# =========================

if st.button("▶ Jalankan Searching"):

    st.divider()

    if algoritma == "Sequential Search":

        st.header("Sequential Search")

        start = time.time()

        hasil = sequential_search(data, search_key)

        end = time.time()

        st.write(f"Waktu eksekusi: {end-start:.5f} detik")

        st.subheader("Kompleksitas")
        st.write("Best Case : O(1)")
        st.write("Average Case : O(n)")
        st.write("Worst Case : O(n)")

    else:

        st.header("Binary Search")

        start = time.time()

        hasil = binary_search(data, search_key)

        end = time.time()

        st.write(f"Waktu eksekusi: {end-start:.5f} detik")

        st.subheader("Kompleksitas")
        st.write("Best Case : O(1)")
        st.write("Average Case : O(log n)")
        st.write("Worst Case : O(log n)")

# =========================
# PENJELASAN
# =========================

st.divider()

st.header("Penjelasan Algoritma")

with st.expander("Sequential Search"):
    st.write("""
    Sequential Search bekerja dengan memeriksa data satu per satu
    dari awal hingga akhir.

    Cocok untuk:
    - Data kecil
    - Data belum terurut

    Kekurangan:
    - Lambat pada data besar
    """)

with st.expander("Binary Search"):
    st.write("""
    Binary Search bekerja dengan membagi data menjadi dua bagian.

    Syarat:
    - Data harus terurut.

    Kelebihan:
    - Sangat cepat
    - Efisien untuk data besar
    """)

# =========================
# FOOTER
# =========================

st.divider()
st.caption("Mata Kuliah Struktur Data - Sub Materi Searching")

```
Isntall Modul Streamlit
```bash
pip install streamlit
```
Jalankan Script
```bash
streamlit run app.py
```
---

# Referensi

1. Data Structures and Algorithms in Python
2. Introduction to Algorithms - Cormen
3. Data Structures Using Java
4. Struktur Data dan Algoritma
5. GeeksForGeeks Searching Algorithms
