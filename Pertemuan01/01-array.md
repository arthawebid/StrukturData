# 📘 PERTEMUAN 1

# Pengantar Struktur Data dan Kompleksitas Algoritma

---

## 🎯 Tujuan Pembelajaran

Setelah mengikuti pertemuan ini, mahasiswa mampu:

1. Menjelaskan perbedaan antara **data, tipe data, struktur data, dan algoritma**.
2. Memahami peran struktur data dalam efisiensi program.
3. Menjelaskan konsep **abstraksi data (Abstract Data Type / ADT)**.
4. Memahami konsep dasar **analisis kompleksitas waktu dan ruang (Big-O Notation)**.
5. Menganalisis permasalahan sederhana dan menentukan struktur data yang sesuai.

---

## 💡 Manfaat Pembelajaran

* Mahasiswa memahami **fondasi utama pemrograman tingkat lanjut**.
* Mahasiswa mampu berpikir **logis, sistematis, dan efisien** dalam menyelesaikan masalah komputasi.
* Menjadi dasar untuk mata kuliah lanjutan seperti:

  * Algoritma Lanjut
  * Basis Data
  * Kecerdasan Buatan
  * Machine Learning
  * Sistem Operasi

---

# 1️⃣ Konsep Dasar Struktur Data

## 1.1 Apa itu Data?

Data adalah representasi fakta mentah yang dapat diproses menjadi informasi.

Contoh:

* Angka: 10, 25, 99
* Teks: "Andi"
* Nilai Mahasiswa: 85

Menurut teori komputasi klasik, data merupakan entitas yang diproses oleh algoritma dalam sistem komputasi (Knuth, 1997).

📚 Referensi:
Knuth, D. E. (1997). *The Art of Computer Programming*. Addison-Wesley.
DOI: [https://doi.org/10.5555/270146](https://doi.org/10.5555/270146)

---

## 1.2 Apa itu Struktur Data?

Struktur data adalah cara menyimpan dan mengorganisasi data di memori agar dapat digunakan secara efisien.

Menurut Aho, Hopcroft & Ullman (1983), struktur data merupakan representasi logis dan matematis dari hubungan antar elemen data.

📚 Referensi:
Aho, A. V., Hopcroft, J. E., & Ullman, J. D. (1983). *Data Structures and Algorithms*.
DOI: [https://doi.org/10.5555/578775](https://doi.org/10.5555/578775)

---

## 1.3 Hubungan Struktur Data dan Algoritma

Struktur data dan algoritma tidak bisa dipisahkan.

> Algoritma yang baik dengan struktur data yang buruk → tetap lambat
> Struktur data yang tepat dengan algoritma sederhana → bisa sangat cepat

Menurut teori kompleksitas komputasi (Cormen et al., 2009), pemilihan struktur data sangat mempengaruhi efisiensi waktu eksekusi.

📚 Referensi:
Cormen, T. H., et al. (2009). *Introduction to Algorithms (3rd ed.)*. MIT Press.
DOI: [https://doi.org/10.7551/mitpress/9436.001.0001](https://doi.org/10.7551/mitpress/9436.001.0001)

---

# 2️⃣ Tipe Data vs Struktur Data

| Tipe Data | Struktur Data |
| --------- | ------------- |
| Integer   | Array         |
| Float     | Linked List   |
| Boolean   | Stack         |
| Char      | Queue         |
| String    | Tree          |
|           | Graph         |

### Penjelasan

* **Tipe data** → jenis nilai yang disimpan.
* **Struktur data** → bagaimana data tersebut diorganisasi.

Contoh:

```python
nilai = [80, 85, 90, 95]
```

* Integer → tipe data
* List → struktur data

---

# 3️⃣ Klasifikasi Struktur Data

## 3.1 Struktur Data Linear

* Array
* Linked List
* Stack
* Queue

Karakteristik:

* Elemen tersusun berurutan
* Satu jalur traversal

## 3.2 Struktur Data Non-Linear

* Tree
* Graph

Karakteristik:

* Hubungan bercabang
* Banyak jalur traversal

---

# 4️⃣ Abstract Data Type (ADT)

ADT adalah konsep abstraksi yang mendefinisikan:

1. Nilai yang bisa disimpan
2. Operasi yang bisa dilakukan

Contoh: ADT Stack
Operasi:

* push()
* pop()
* isEmpty()

ADT membantu pemrogram fokus pada **apa yang dilakukan**, bukan bagaimana diimplementasikan.

Menurut Liskov (1974), abstraksi data meningkatkan modularitas dan keamanan sistem.

📚 Referensi:
Liskov, B., & Zilles, S. (1974). Programming with Abstract Data Types.
DOI: [https://doi.org/10.1145/361011.361014](https://doi.org/10.1145/361011.361014)

---

# 5️⃣ Analisis Kompleksitas Algoritma

Mengapa penting?

Karena program harus:

* Cepat
* Efisien
* Skalabel

## 5.1 Kompleksitas Waktu (Time Complexity)

Mengukur jumlah operasi terhadap ukuran input (n).

Notasi yang digunakan: Big-O

Contoh:

| Kompleksitas | Contoh        |
| ------------ | ------------- |
| O(1)         | Akses array   |
| O(n)         | Linear search |
| O(log n)     | Binary search |
| O(n²)        | Bubble sort   |

## 5.2 Kompleksitas Ruang (Space Complexity)

Mengukur penggunaan memori terhadap ukuran input.

---

# 🔎 Studi Kasus Project (Berbasis Penalaran)

## Studi Kasus: Sistem Manajemen Antrian Klinik

Sebuah klinik ingin membuat sistem:

* Pendaftaran pasien
* Pemanggilan pasien
* Riwayat kunjungan

### Permasalahan

1. Bagaimana menyimpan data pasien?
2. Bagaimana mengatur antrian?
3. Bagaimana mencari pasien tertentu dengan cepat?

---

## 🎓 Tugas Analisis Mahasiswa

Mahasiswa diminta:

1. Menentukan struktur data yang tepat untuk:

   * Penyimpanan pasien
   * Sistem antrian
   * Riwayat kunjungan
2. Menjelaskan alasan pemilihan berdasarkan:

   * Efisiensi waktu
   * Kemudahan implementasi
   * Skalabilitas

---

# 💻 Praktikum Pertemuan 1
---

# 📘 MATERI PRAKTIKUM

# Array dan List dalam Python

---

# 📚 Dasar Teori Array

Array adalah struktur data linear yang menyimpan elemen dengan tipe data yang sama dan disimpan dalam memori yang berurutan (contiguous memory allocation).

Menurut Goodrich, Tamassia & Goldwasser (2014), array memungkinkan akses elemen secara langsung (random access) dengan kompleksitas waktu O(1).

📖 Referensi:
Goodrich, M. T., Tamassia, R., & Goldwasser, M. H. (2014). *Data Structures and Algorithms in Python*.
DOI: [https://doi.org/10.1002/9781118290279](https://doi.org/10.1002/9781118290279)

Dalam konteks komputasi numerik modern, library **NumPy** menggunakan struktur array yang dioptimalkan untuk komputasi ilmiah.

📖 Referensi:
Harris, C. R., et al. (2020). Array programming with NumPy. *Nature*, 585.
DOI: [https://doi.org/10.1038/s41586-020-2649-2](https://doi.org/10.1038/s41586-020-2649-2)

---

# 🔷 1️⃣ Pendeklarasian Array

---

## 1.1 Array 1 Dimensi

### 🔎 Teori

Array 1 dimensi adalah struktur linear dengan satu indeks.

Secara matematis:
A[i], i = 0,1,2,...,n-1

Akses langsung:

* Kompleksitas: O(1)
* Memori: Kontigu

---

### 💻 Contoh

```python
import numpy as np

arr = np.array([10, 20, 30, 40, 50])
print(arr)
```

---

### 🧪 Latihan Praktikum (Minimal 3)

1️⃣ Buat array berisi 10 angka ganjil pertama.
2️⃣ Buat array berisi nilai mahasiswa dan tampilkan nilai tertinggi.
3️⃣ Buat array berisi 5 angka, lalu hitung rata-ratanya menggunakan `.mean()`.

---

## 1.2 Array 2 Dimensi

### 🔎 Teori

Array 2 dimensi direpresentasikan sebagai matriks.

Secara matematis:
A[i][j]

Digunakan untuk:

* Tabel data
* Matriks matematika
* Representasi citra (image)

Kompleksitas akses:
O(1)

---

### 💻 Contoh

```python
import numpy as np

matrix = np.array([[1,2,3],
                   [4,5,6]])
print(matrix)
```

---

### 🧪 Latihan Praktikum

1️⃣ Buat matriks 3x3 dan tampilkan elemen tengahnya.
2️⃣ Hitung jumlah seluruh elemen matriks.
3️⃣ Buat tabel nilai 3 mahasiswa × 4 mata kuliah.

---

## 1.3 Array n Dimensi

### 🔎 Teori

Array multidimensi digunakan dalam:

* Machine Learning
* Pengolahan Citra
* Data Tensor

NumPy mendukung n-dimensi array (ndarray).

📖 Referensi tambahan:
Van der Walt et al. (2011). The NumPy array.
DOI: [https://doi.org/10.1109/MCSE.2011.37](https://doi.org/10.1109/MCSE.2011.37)

---

### 💻 Contoh

```python
import numpy as np

arr3d = np.array([
    [[1,2],[3,4]],
    [[5,6],[7,8]]
])
print(arr3d)
```

---

### 🧪 Latihan Praktikum

1️⃣ Buat array 3D berukuran 2x2x2.
2️⃣ Tampilkan elemen pada indeks [1][0][1].
3️⃣ Hitung total seluruh elemen array 3D.

---

## 1.4 List (Alternatif Array Dinamis)

### 🔎 Teori

List adalah struktur data dinamis dalam Python yang:

* Mutable
* Bisa heterogen
* Tidak harus kontigu seperti array NumPy

Namun:

* Tidak seefisien NumPy untuk komputasi numerik besar.

📖 Referensi:
Oliphant, T. (2006). *Guide to NumPy*.
DOI: [https://doi.org/10.5555/1129774](https://doi.org/10.5555/1129774)

---

### 💻 Contoh

```python
data = [10, "Andi", 3.14, True]
print(data)
```

---

### 🧪 Latihan Praktikum

1️⃣ Buat list berisi nama 5 mahasiswa.
2️⃣ Tambahkan 1 nama baru menggunakan `.append()`.
3️⃣ Hapus satu elemen menggunakan `.remove()`.

---

# 🔷 2️⃣ Akses Array

---

## 🔎 Teori

Akses elemen array dilakukan menggunakan indeks.

Karena array menggunakan contiguous memory:
Alamat memori dihitung secara matematis.

Untuk array 1D:
Address = base + (index × ukuran_tipe_data)

Kompleksitas:
O(1)

📖 Referensi:
Cormen et al. (2009). *Introduction to Algorithms*.
DOI: [https://doi.org/10.7551/mitpress/9436.001.0001](https://doi.org/10.7551/mitpress/9436.001.0001)

---

### 💻 Contoh Akses 1D

```python
arr = np.array([5, 10, 15])
print(arr[1])
```

---

### 💻 Contoh Akses 2D

```python
matrix = np.array([[1,2],[3,4]])
print(matrix[1,0])
```

---

### 💻 Modifikasi Nilai

```python
matrix[0,1] = 100
print(matrix)
```

---

### 🧪 Latihan Praktikum

1️⃣ Buat array 1D dan ubah elemen indeks ke-2 menjadi 999.
2️⃣ Buat matriks 2x2 dan ubah semua elemennya menjadi 0 menggunakan perulangan.
3️⃣ Buat array 3D lalu tampilkan semua elemennya menggunakan nested loop.

---

# 🔷 3️⃣ Contoh Program Dengan Array

---

## 🔎 Teori

NumPy menyediakan fungsi statistik bawaan:

* min()
* max()
* mean()
* sum()
* std()
* argmin()
* argmax()

Operasi ini dioptimalkan menggunakan vectorized computation.

📖 Referensi:
Harris et al. (2020).
DOI: [https://doi.org/10.1038/s41586-020-2649-2](https://doi.org/10.1038/s41586-020-2649-2)

---

### 💻 Contoh Program Statistik

```python
import numpy as np

arr = np.array([10, 20, 30, 40, 50])

print("Minimum:", arr.min())
print("Maximum:", arr.max())
print("Mean:", arr.mean())
print("Sum:", arr.sum())
print("Std:", arr.std())
```

---

### 💻 Contoh Program Argmin & Argmax

```python
print("Index Minimum:", arr.argmin())
print("Index Maximum:", arr.argmax())
```

---

### 💻 Studi Kasus Mini

Analisis Nilai Mahasiswa

```python
nilai = np.array([75, 80, 90, 60, 85])

if nilai.mean() >= 75:
    print("Rata-rata lulus")
else:
    print("Rata-rata tidak lulus")
```

---

### 🧪 Latihan Praktikum

1. Buat program menghitung nilai rata-rata 10 mahasiswa.  
2. Buat program menentukan nilai tertinggi dan terendah.  
3. Buat program menghitung standar deviasi dan jelaskan maknanya.  

---

# 📌 Tugas Pengumpulan GitHub

Mahasiswa wajib mengumpulkan:

📂 struktur-data-pertemuan-1/

* array1d.py
* array2d.py
* array3d.py
* list.py
* akses_array.py
* statistik_array.py
* README.md (analisis & refleksi)

---

# 🧠 Pertanyaan Analitis untuk Mahasiswa

1. Mengapa array lebih cepat daripada list dalam komputasi numerik besar?
2. Apa dampak jika data sangat besar (1 juta elemen)?
3. Kapan sebaiknya menggunakan list dibanding NumPy array?
4. Buatlah kesimpulan perbedaan Array dan List pada Python! 

---

# 📌 Kesimpulan Praktikum

* Array efisien untuk komputasi numerik.
* List fleksibel untuk data heterogen.
* Akses indeks pada array bersifat O(1).
* NumPy menggunakan optimasi C-level untuk performa tinggi.

## Analisis Kompleksitas Sederhana

Mahasiswa membuat 3 fungsi Python:

1. Fungsi O(1)
2. Fungsi O(n)
3. Fungsi O(n²)

Contoh:

```python
def constant(n):
    return n * 2

def linear(n):
    for i in range(n):
        print(i)

def quadratic(n):
    for i in range(n):
        for j in range(n):
            print(i, j)
```

Mahasiswa diminta menjelaskan:

* Mengapa termasuk O(1), O(n), O(n²)?
* Bagaimana jika n = 1.000.000?

---

# 📂 Tugas yang Dikumpulkan ke GitHub

Mahasiswa wajib:

1. Membuat repository:
   `struktur-data-pertemuan-1`

2. Isi repository:

   * README.md berisi:

     * Penjelasan konsep struktur data
     * Analisis studi kasus klinik
     * Analisis kompleksitas
   * File Python:

     * kompleksitas.py
     * simulasi_antrian.py (versi sederhana)

3. Screenshot hasil running program

4. Link dikumpulkan di LMS

---

# 🧠 Pertanyaan Reflektif (Untuk Diskusi)

1. Apakah struktur data mempengaruhi performa database?
2. Apakah semua masalah bisa diselesaikan dengan satu struktur data?
3. Jika data sangat besar (Big Data), apa konsekuensinya terhadap kompleksitas?

---

# 📌 Kesimpulan Pertemuan 1

* Struktur data adalah fondasi utama ilmu komputer.
* Pemilihan struktur data menentukan efisiensi sistem.
* Analisis kompleksitas membantu memprediksi performa.
* Berpikir komputasional adalah kunci keberhasilan di bidang informatika.

