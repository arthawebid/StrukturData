# 📌 PERTEMUAN 1  
## Struktur Data Dasar

## 🎯 Tujuan Pembelajaran
Setelah mengikuti pertemuan ini mahasiswa mampu:

1. Menjelaskan konsep struktur data dan peran array.
2. Memahami penyimpanan memori secara kontigu.
3. Mengimplementasikan array 1 dimensi.
4. Menganalisis kompleksitas waktu dasar (Big-O).
5. Membandingkan operasi akses, insert, dan delete.

## 📘 1. Konsep Struktur Data

Struktur data adalah cara mengorganisasi dan menyimpan data agar dapat diakses secara efisien.

Dalam ilmu komputer, pemilihan struktur data yang tepat sangat mempengaruhi performa algoritma.

Referensi akademik utama:
Cormen et al., *Introduction to Algorithms*, MIT Press, 2009.  
DOI: 10.7551/mitpress/9434.001.0001

## 📘 2. Definisi List
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

### 🧪 Latihan Praktikum 1
1. Buat list berisi nama 5 mahasiswa.
2. Tambahkan 1 nama baru menggunakan `.append()`.
3. Hapus satu elemen menggunakan `.remove()`.

```python
# Buat list berisi nama 5 mahasiswa
mahasiswa = ["Andi", "Budi", "Citra", "Dewi", "Eko"]
print("List nama mahasiswa:")
print(mahasiswa)
```
```python
# Tambahkan 1 nama baru menggunakan `.append()`.
mahasiswa.append("Fajar")
print("\nSetelah menambahkan nama baru:")
print(mahasiswa)
```
```python
# Hapus satu elemen menggunakan `.remove()`.
mahasiswa.remove("Citra")
print("\nSetelah menghapus nama Citra:")
print(mahasiswa)
```

### 🧪 Latihan Praktikum 2
Input 10 data kedalam sebuah List:
1. Buat definisi list
2. Proses input 10 data dengan perulangan for
3. Tampilkan data list, nilai tertinggi, terendah dan Rata-rata
4. buat grafik bar

```python
# Definisikan list kosong untuk menyimpan angka
list = []
```
```python
# input 10 angka
for i in range(10):
    angka = int(input("Masukkan angka: "))
    list.append(angka)
```
```python
# tampilkan nilai maksimum, minimum, dan rata-rata
print("List:", list)
print("Nilai maksimum:", max(list))
print("Nilai minimum:", min(list))
print("Rata-rata:", sum(list)/len(list))
```
```python
#buat grafik batang menggunakan matplotlib
import matplotlib.pyplot as plt 
plt.bar(range(len(list)), list)
plt.title("Grafik Array")   
plt.xlabel("Indeks")
plt.ylabel("Nilai")
plt.show()
```

## 📘 3. Definisi Array
Array adalah struktur data linear yang menyimpan elemen dengan tipe data yang sama dan disimpan dalam memori yang berurutan (contiguous memory allocation).
Menurut Goodrich, Tamassia & Goldwasser (2014), array memungkinkan akses elemen secara langsung (random access) dengan kompleksitas waktu O(1).

Array adalah struktur data linier yang:
- Menyimpan elemen dengan tipe data yang sama
- Disimpan secara berurutan (contiguous memory)
- Diakses menggunakan indeks

Contoh:
```
Index:  0   1   2   3   4
Value: [10, 20, 30, 40, 50]
````
Dalam konteks komputasi numerik modern, library **NumPy** menggunakan struktur array yang dioptimalkan untuk komputasi ilmiah.

Karakteristik Array
| Karakteristik | Penjelasan |
|--------------|------------|
| Homogen | Semua elemen bertipe sama |
| Fixed size | Ukuran ditentukan di awal |
| Indexed | Akses menggunakan indeks |
| Kontigu | Disimpan berurutan di memori |

Pendeklarasian Array
### 3.1 Array 1 Dimensi
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
### 🧪 Latihan Praktikum (Minimal 3)
1. Buat array berisi 10 angka ganjil pertama.
2. Buat array berisi nilai mahasiswa dan tampilkan nilai tertinggi
3. Buat array berisi 5 angka, lalu hitung rata-ratanya menggunakan `.mean()`.
4. Buat array berisi data jumlah Anggota Pria dan Wanita, buat grafik Pie untuk menggambarkan data tersebut

```python
## Mengimpor library NumPy untuk bekerja dengan array
import numpy as np 
```
```python
# 1. Array berisi 10 bilangan ganjil pertama
print("1. Array berisi 10 bilangan ganjil pertama:  ")
## Membuat array bilangan ganjil pertama
bilganjil = np.array([1, 3, 5, 7, 9, 11, 13, 15, 17, 19]) 
print(bilganjil)
```
```python
# 2. Array berisi nilai mahasiswa dan tampilkan nilai tertinggi
print("\n2. Array berisi nilai mahasiswa dan tampilkan nilai tertinggi:  ")
## Membuat array nilai mahasiswa
nilai_mahasiswa = np.array([85, 90, 78, 92, 88, 95, 80, 91, 89, 94, 87, 93, 86, 90, 91])

## Menghitung nilai tertinggi
nilai_tertinggi = np.max(nilai_mahasiswa)
print(nilai_mahasiswa)
print("Nilai tertinggi:", nilai_tertinggi)  
```
```python
# 3. Array array berisi 5 angka, lalu hitung rata-ratanya menggunakan .mean():
print("\n3. Array array berisi 5 angka, lalu hitung rata-ratanya menggunakan .mean():  ")
## Membuat array angka
angka = np.array([10, 20, 30, 40, 50])

## Menghitung rata-rata
rata_rata = np.mean(angka)
print("Array:", angka)
print("Rata-rata:", rata_rata)
```
```python
# 4. Buat array berisi data jumlah Anggota Pria dan Wanita
print("\n4. Buat array berisi data jumlah Anggota Pria dan Wanita:  ")
## Membuat array jumlah anggota pria dan wanita
jumlah_anggota = np.array([60, 40])  # Contoh: 60 pria dan 40 wanita
print("Jumlah anggota (Pria, Wanita):", jumlah_anggota)
```
```python
# Buat grafik pie chart menggunakan matplotlib
import matplotlib.pyplot as plt
labels = ['Pria', 'Wanita']
sizes = jumlah_anggota
plt.pie(sizes, labels=labels, autopct='%1.1f%%', startangle=140)
plt.title("Grafik Pie Chart Jumlah Anggota")
plt.axis('equal')  # Membuat grafik menjadi lingkaran
plt.show()
```

### 3.2 Array 2 Dimensi
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
1. Buat matriks 3x3 dan tampilkan elemen tengahnya.
2. Hitung jumlah seluruh elemen matriks.
3. Buat tabel nilai 3 mahasiswa × 4 mata kuliah.


```python
## import library numpy
import numpy as np

print("1. Matriks 3x3 dan tampilkan elemen tengahnya:  ")
matriks = np.array([[1, 2, 3],
                    [4, 5, 6],
                    [7, 8, 9]])
print(matriks)
print("Elemen tengah:", matriks[1,1])
```
```python
print("\n2. Hitung jumlah seluruh elemen matriks:  ")
jumlah_elemen = np.sum(matriks)
print("Jumlah elemen:", jumlah_elemen) 
```
```python
print("\n3. Buat tabel nilai 3 mahasiswa × 4 mata kuliah:  ")
nilai_mahasiswa = np.array([[85, 90, 78, 92],
                             [88, 95, 80, 91],
                             [89, 94, 87, 93]])
print(nilai_mahasiswa)
```
### 3.3 Array n Dimensi
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
1. Buat array 3D berukuran 2x2x2.
2. Tampilkan elemen pada indeks [1][0][1].
3. Hitung total seluruh elemen array 3D.

```python
# import library numpy
import numpy as np
```
```python
# 1. Array 3D berukuran 2x2x2.
array_3d = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]]])
print("Array 3D berukuran 2x2x2:")
print(array_3d)
```
```python
# 2. Tampilkan elemen pada indeks [1][0][1].
print("Elemen pada indeks [1][0][1]:", array_3d[1, 0, 1])
```
```python
# 3. Hitung total seluruh elemen array 3D.
total = np.sum(array_3d)
print("Total seluruh elemen array 3D:", total)
```


## 📘 5. Kompleksitas Operasi

| Operasi | Kompleksitas |
|----------|-------------|
| Akses elemen | O(1) |
| Update elemen | O(1) |
| Traversal | O(n) |
| Insert tengah | O(n) |
| Delete tengah | O(n) |

Penjelasan:
- Akses O(1) karena alamat memori dihitung langsung.
- Insert/delete O(n) karena perlu shifting.
---

# 🧪 PRAKTIKUM

## Praktikum 1 – Implementasi List

Buat program Python:

```python
arr = []

# input 10 angka
for i in range(10):
    angka = int(input("Masukkan angka: "))
    arr.append(angka)

print("Array:", arr)
print("Nilai maksimum:", max(arr))
print("Nilai minimum:", min(arr))
print("Rata-rata:", sum(arr)/len(arr))
````
## Praktikum 2 – Operasi Insert & Delete Manual
Tanpa menggunakan method bawaan seperti `.insert()` atau `.remove()`.

Buat fungsi:
* insert_tengah(arr, posisi, nilai)
* delete_tengah(arr, posisi)
Tujuan: memahami shifting elemen.

Buat bar grafik dari data yang di inputkan
```python
#buat grafik batang menggunakan matplotlib
import matplotlib.pyplot as plt 
plt.bar(range(len(arr)), arr)
plt.title("Grafik Array")   
plt.xlabel("Indeks")
plt.ylabel("Nilai")
plt.show()
```
## Array 

# 📝 PROJECT TUGAS (WAJIB GITHUB)

## Studi Kasus

Buat sistem sederhana pengelolaan nilai mahasiswa menggunakan array.

Fitur minimal:

1. Input 10 nilai
2. Tampilkan nilai tertinggi & terendah
3. Hitung rata-rata
4. Hitung jumlah mahasiswa lulus (>= 60)
5. Buat grafik untuk menggambarkan nilai tertinggi dan terendah
6. Buat grafik untuk menggambarkan data kelulusan
7. Analisis kompleksitas tiap operasi

## Struktur Repository

```
01-array/
    Soal_01.py
    soal_02.py
    README.md
```
## Isi README.md Wajib

1. Penjelasan konsep array
2. Screenshot hasil eksekusi
3. Analisis kompleksitas
4. Refleksi pembelajaran

# 📊 RUBRIK PENILAIAN TUGAS ARRAY

| Aspek                 | Bobot   |
| --------------------- | ------- |
| Pemahaman Konsep      | 20      |
| Implementasi Program  | 30      |
| Analisis Kompleksitas | 20      |
| Dokumentasi README    | 15      |
| Manajemen Git         | 15      |
| **Total**             | **100** |

---

## Detail Penilaian

### Pemahaman Konsep (20)

* 18–20: Penjelasan sangat tepat & runtut
* 14–17: Cukup tepat
* <14: Kurang tepat

### Implementasi (30)

* Program berjalan tanpa error
* Logika benar
* Tanpa penggunaan shortcut berlebihan

### Analisis Kompleksitas (20)

* Menjelaskan O(1), O(n) dengan benar
* Ada alasan logis

### Dokumentasi (15)

* Lengkap
* Sistematis
* Ada bukti eksekusi

### Git (15)

* Minimal 5 commit
* Commit message jelas
* Tidak sekali upload

# ⚠️ Ketentuan

* Plagiarisme = 0
* Tidak ada README = nilai maksimal 60
* Tidak ada analisis kompleksitas = nilai maksimal 70
