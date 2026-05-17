# Pertemuan 12 — Sorting I

## Bubble Sort, Selection Sort, dan Insertion Sort

**Mata Kuliah:** Struktur Data
**Level:** C4 (Analyze)
**Jenis:** Tugas

---

# 1. Tujuan Pembelajaran

Setelah mengikuti materi ini mahasiswa mampu:

1. Memahami konsep dasar sorting.
2. Menjelaskan cara kerja algoritma sorting sederhana.
3. Menganalisis proses pertukaran data pada sorting.
4. Mengimplementasikan Bubble Sort, Selection Sort, dan Insertion Sort menggunakan Python.
5. Membandingkan efisiensi algoritma sorting berdasarkan kompleksitas waktu.
6. Menentukan algoritma yang cocok berdasarkan kondisi data.

---

# 2. Pengertian Sorting

Sorting adalah proses mengurutkan sekumpulan data berdasarkan aturan tertentu.

Pengurutan dapat dilakukan:

* Dari kecil ke besar (**Ascending**)
* Dari besar ke kecil (**Descending**)

Contoh:

Data awal:

```python id="ik4gxg"
[7, 2, 9, 1, 5]
```

Ascending:

```python id="te7r2g"
[1, 2, 5, 7, 9]
```

Descending:

```python id="g6sv6k"
[9, 7, 5, 2, 1]
```

---

# 3. Mengapa Sorting Penting?

Sorting sangat penting dalam ilmu komputer karena:

| Kegunaan                  | Penjelasan                             |
| ------------------------- | -------------------------------------- |
| Mempermudah pencarian     | Binary Search membutuhkan data terurut |
| Mempermudah analisis data | Data lebih mudah dibaca                |
| Digunakan dalam database  | ORDER BY menggunakan sorting           |
| Digunakan dalam laporan   | Ranking dan statistik                  |

---

# 4. Jenis-Jenis Sorting

Secara umum sorting dibagi menjadi:

| Jenis               | Contoh                       |
| ------------------- | ---------------------------- |
| Simple Sort         | Bubble, Selection, Insertion |
| Efficient Sort      | Merge, Quick, Heap           |
| Non-Comparison Sort | Counting, Radix              |

Pada pertemuan ini fokus pada:

1. Bubble Sort
2. Selection Sort
3. Insertion Sort

---

# 5. Bubble Sort

# 5.1 Pengertian Bubble Sort

Bubble Sort adalah algoritma sorting yang bekerja dengan:

* Membandingkan dua elemen berdekatan
* Menukar posisi jika salah urut
* Dilakukan berulang hingga seluruh data terurut

Disebut “Bubble” karena elemen terbesar akan “mengambang” ke atas seperti gelembung.

---

# 5.2 Cara Kerja Bubble Sort

Contoh data:

```python id="hm5v7h"
[5, 3, 8, 1]
```

---

## Iterasi 1

Bandingkan:

```text id="gff27w"
5 dan 3
```

Karena:

```text id="oy4mfh"
5 > 3
```

Maka ditukar:

```python id="ggx7tm"
[3, 5, 8, 1]
```

---

Bandingkan:

```text id="o0z2a4"
5 dan 8
```

Tidak ditukar:

```python id="tk0h5z"
[3, 5, 8, 1]
```

---

Bandingkan:

```text id="ozv2wc"
8 dan 1
```

Ditukar:

```python id="s1hmwt"
[3, 5, 1, 8]
```

Angka terbesar sudah berada di belakang.

---

## Iterasi 2

Bandingkan:

```text id="m4r44o"
3 dan 5
```

Tidak ditukar.

---

Bandingkan:

```text id="ebl5y5"
5 dan 1
```

Ditukar:

```python id="09yqbo"
[3, 1, 5, 8]
```

---

## Iterasi 3

Bandingkan:

```text id="s3qv80"
3 dan 1
```

Ditukar:

```python id="eq4g1y"
[1, 3, 5, 8]
```

Sorting selesai.

---

# 5.3 Visualisasi Bubble Sort

```text id="7w4c3u"
[5, 3, 8, 1]

5 ↔ 3
[3, 5, 8, 1]

8 ↔ 1
[3, 5, 1, 8]

5 ↔ 1
[3, 1, 5, 8]

3 ↔ 1
[1, 3, 5, 8]
```

---

# 5.4 Implementasi Bubble Sort Python

```python id="z9tnfp"
def bubble_sort(data):

    n = len(data)

    for i in range(n):

        for j in range(0, n-i-1):

            if data[j] > data[j+1]:

                data[j], data[j+1] = data[j+1], data[j]

    return data


angka = [5, 3, 8, 1]

hasil = bubble_sort(angka)

print("Hasil:", hasil)
```

---

# 5.5 Penjelasan Kode Bubble Sort

## Bagian:

```python id="2d59r8"
n = len(data)
```

Digunakan untuk mendapatkan jumlah data.

---

## Bagian:

```python id="5wimyb"
for i in range(n):
```

Perulangan utama untuk iterasi sorting.

---

## Bagian:

```python id="owc0r0"
for j in range(0, n-i-1):
```

Digunakan untuk membandingkan elemen berdekatan.

---

## Bagian:

```python id="rqb8ea"
if data[j] > data[j+1]:
```

Jika elemen kiri lebih besar maka tukar.

---

## Bagian:

```python id="4lzwm0"
data[j], data[j+1] = data[j+1], data[j]
```

Swap atau pertukaran data.

---

# 5.6 Kompleksitas Bubble Sort

| Kondisi      | Kompleksitas |
| ------------ | ------------ |
| Best Case    | O(n)         |
| Average Case | O(n²)        |
| Worst Case   | O(n²)        |

---

# 5.7 Kelebihan Bubble Sort

* Mudah dipahami
* Mudah diimplementasikan
* Cocok untuk pembelajaran dasar

---

# 5.8 Kekurangan Bubble Sort

* Lambat untuk data besar
* Banyak pertukaran data
* Tidak efisien

---

# 6. Selection Sort

# 6.1 Pengertian Selection Sort

Selection Sort bekerja dengan:

1. Mencari nilai terkecil
2. Menempatkannya di posisi awal
3. Mengulangi proses untuk sisa data

---

# 6.2 Cara Kerja Selection Sort

Data:

```python id="ng61tl"
[64, 25, 12, 22, 11]
```

---

## Iterasi 1

Cari nilai terkecil:

```text id="fvg4f3"
11
```

Tukar dengan indeks pertama:

```python id="m2vvtl"
[11, 25, 12, 22, 64]
```

---

## Iterasi 2

Cari nilai terkecil berikutnya:

```text id="4k4o2t"
12
```

Hasil:

```python id="q7tr7w"
[11, 12, 25, 22, 64]
```

---

## Iterasi 3

Cari nilai terkecil:

```text id="i2lrln"
22
```

Hasil:

```python id="ksq9xw"
[11, 12, 22, 25, 64]
```

---

# 6.3 Implementasi Selection Sort

```python id="26f8qv"
def selection_sort(data):

    n = len(data)

    for i in range(n):

        min_index = i

        for j in range(i+1, n):

            if data[j] < data[min_index]:
                min_index = j

        data[i], data[min_index] = data[min_index], data[i]

    return data


angka = [64, 25, 12, 22, 11]

print(selection_sort(angka))
```

---

# 6.4 Penjelasan Kode

## Bagian:

```python id="2mqxko"
min_index = i
```

Menandai indeks terkecil sementara.

---

## Bagian:

```python id="8u7n84"
if data[j] < data[min_index]:
```

Mencari nilai paling kecil.

---

## Bagian:

```python id="84v8nh"
data[i], data[min_index]
```

Menukar data.

---

# 6.5 Kompleksitas

| Kondisi | Kompleksitas |
| ------- | ------------ |
| Best    | O(n²)        |
| Average | O(n²)        |
| Worst   | O(n²)        |

---

# 6.6 Kelebihan

* Jumlah swap lebih sedikit
* Sederhana

---

# 6.7 Kekurangan

* Tetap lambat
* Tidak adaptif

---

# 7. Insertion Sort

# 7.1 Pengertian

Insertion Sort bekerja seperti menyusun kartu.

Data akan disisipkan pada posisi yang tepat.

---

# 7.2 Cara Kerja

Data:

```python id="b13kj3"
[9, 5, 1, 4]
```

---

## Langkah 1

Ambil:

```text id="6xg2a5"
5
```

Bandingkan dengan:

```text id="mwt1x8"
9
```

Geser:

```python id="2f42je"
[5, 9, 1, 4]
```

---

## Langkah 2

Ambil:

```text id="vtr9xt"
1
```

Geser:

```python id="u8j2mf"
[1, 5, 9, 4]
```

---

## Langkah 3

Ambil:

```text id="oj2x5q"
4
```

Hasil:

```python id="n5z1x8"
[1, 4, 5, 9]
```

---

# 7.3 Implementasi Python

```python id="1v7m9v"
def insertion_sort(data):

    for i in range(1, len(data)):

        key = data[i]
        j = i - 1

        while j >= 0 and key < data[j]:

            data[j + 1] = data[j]
            j -= 1

        data[j + 1] = key

    return data


angka = [9, 5, 1, 4]

print(insertion_sort(angka))
```

---

# 7.4 Penjelasan Kode

## Bagian:

```python id="q0a4l7"
key = data[i]
```

Menyimpan nilai yang akan disisipkan.

---

## Bagian:

```python id="1c0c90"
while j >= 0 and key < data[j]:
```

Menggeser elemen lebih besar.

---

## Bagian:

```python id="mjlwm5"
data[j + 1] = key
```

Menyisipkan elemen.

---

# 7.5 Kompleksitas

| Kondisi | Kompleksitas |
| ------- | ------------ |
| Best    | O(n)         |
| Average | O(n²)        |
| Worst   | O(n²)        |

---

# 7.6 Kelebihan

* Cepat untuk data kecil
* Efektif untuk data hampir terurut

---

# 7.7 Kekurangan

* Tidak cocok untuk data besar

---

# 8. Perbandingan Algoritma

| Algoritma | Swap    | Kecepatan   | Stabil |
| --------- | ------- | ----------- | ------ |
| Bubble    | Banyak  | Lambat      | Ya     |
| Selection | Sedikit | Lambat      | Tidak  |
| Insertion | Sedang  | Cukup cepat | Ya     |

---

# 9. Analisis Pemilihan Algoritma

| Kondisi          | Algoritma Cocok |
| ---------------- | --------------- |
| Data kecil       | Bubble          |
| Sedikit swap     | Selection       |
| Data hampir urut | Insertion       |

---

# 10. Studi Kasus

## Kasus

Sebuah aplikasi nilai mahasiswa ingin:

* Mengurutkan nilai dari kecil ke besar
* Menampilkan ranking mahasiswa

Data:

```python id="gk7t3i"
[78, 90, 65, 88, 70]
```

Gunakan salah satu algoritma sorting.

---

# 11. Latihan

## Latihan 1

Urutkan data:

```python id="m8gwx8"
[12, 5, 9, 1, 20]
```

Menggunakan Bubble Sort.

---

## Latihan 2

Gunakan Selection Sort untuk:

```python id="0t6g1j"
[44, 11, 88, 22]
```

---

## Latihan 3

Gunakan Insertion Sort untuk:

```python id="5i0y6v"
[7, 3, 5, 2]
```

---

# 12. Tugas C4

1. Buat program Bubble Sort ascending dan descending.
2. Buat visualisasi proses sorting.
3. Hitung jumlah:

   * iterasi
   * swap
   * perbandingan
4. Bandingkan ketiga algoritma.
5. Analisis algoritma terbaik untuk:

   * data kecil
   * data hampir terurut
   * data acak

---
# 13 Contoh Sort Data
```bash
import streamlit as st
import time

st.set_page_config(page_title="Sorting I Animation", layout="wide")

st.title("📘 Pertemuan 12 — Sorting I")
st.markdown("## Bubble Sort, Selection Sort, dan Insertion Sort")

st.write(
    "Materi ini menampilkan simulasi animasi algoritma sorting dasar "
    "menggunakan Streamlit."
)

algorithms = {
    "Bubble Sort": {
        "description": "Membandingkan dua elemen berdekatan lalu menukarnya jika salah urut.",
        "steps": [
            [5, 3, 8, 1],
            [3, 5, 8, 1],
            [3, 5, 1, 8],
            [3, 1, 5, 8],
            [1, 3, 5, 8],
        ],
        "code": '''def bubble_sort(data):
    n = len(data)

    for i in range(n):
        for j in range(0, n-i-1):

            if data[j] > data[j+1]:
                data[j], data[j+1] = data[j+1], data[j]

    return data'''
    },

    "Selection Sort": {
        "description": "Mencari nilai terkecil lalu menempatkannya di posisi awal.",
        "steps": [
            [64, 25, 12, 22, 11],
            [11, 25, 12, 22, 64],
            [11, 12, 25, 22, 64],
            [11, 12, 22, 25, 64],
        ],
        "code": '''def selection_sort(data):
    n = len(data)

    for i in range(n):

        min_index = i

        for j in range(i+1, n):

            if data[j] < data[min_index]:
                min_index = j

        data[i], data[min_index] = data[min_index], data[i]

    return data'''
    },

    "Insertion Sort": {
        "description": "Menyisipkan elemen pada posisi yang benar.",
        "steps": [
            [9, 5, 1, 4, 3],
            [5, 9, 1, 4, 3],
            [1, 5, 9, 4, 3],
            [1, 4, 5, 9, 3],
            [1, 3, 4, 5, 9],
        ],
        "code": '''def insertion_sort(data):
    for i in range(1, len(data)):

        key = data[i]
        j = i - 1

        while j >= 0 and key < data[j]:
            data[j + 1] = data[j]
            j -= 1

        data[j + 1] = key

    return data'''
    }
}

selected_algo = st.selectbox(
    "Pilih Algoritma Sorting",
    list(algorithms.keys())
)

algo = algorithms[selected_algo]

st.subheader(selected_algo)
st.write(algo["description"])

st.code(algo["code"], language="python")

chart_placeholder = st.empty()
text_placeholder = st.empty()

if st.button("▶ Jalankan Animasi"):

    for i, step in enumerate(algo["steps"]):

        chart_placeholder.bar_chart(step)
        text_placeholder.success(f"Step {i+1}: {step}")

        time.sleep(1.2)

    st.success("Sorting selesai!")

st.markdown("---")

st.header("📝 Tugas C4")

st.markdown(
    '''
1. Buat program Bubble Sort ascending.
2. Modifikasi menjadi descending.
3. Bandingkan Bubble, Selection, dan Insertion Sort.
4. Hitung jumlah iterasi tiap algoritma.
5. Gunakan data input dari user.
'''
)

st.markdown("---")

st.subheader("▶ Cara Menjalankan")

st.code(
    '''pip install streamlit
streamlit run app.py''',
    language="bash"
)


```
---
# 14. Kesimpulan

* Sorting digunakan untuk mengurutkan data.
* Bubble Sort bekerja dengan pertukaran elemen berdekatan.
* Selection Sort memilih elemen terkecil.
* Insertion Sort menyisipkan elemen pada posisi yang benar.
* Ketiga algoritma sederhana namun memiliki kompleksitas O(n²).
* Insertion Sort lebih baik untuk data kecil atau hampir terurut.
