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


## 📘 2. Definisi Array

Array adalah struktur data linier yang:

- Menyimpan elemen dengan tipe data yang sama
- Disimpan secara berurutan (contiguous memory)
- Diakses menggunakan indeks

Contoh:
```

Index:  0   1   2   3   4
Value: [10, 20, 30, 40, 50]

````

---

## 📘 3. Karakteristik Array

| Karakteristik | Penjelasan |
|--------------|------------|
| Homogen | Semua elemen bertipe sama |
| Fixed size | Ukuran ditentukan di awal |
| Indexed | Akses menggunakan indeks |
| Kontigu | Disimpan berurutan di memori |


## 📘 4. Kompleksitas Operasi

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

## Praktikum 1 – Implementasi Array Dasar

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

# 📝 PROJECT TUGAS (WAJIB GITHUB)

## Studi Kasus

Buat sistem sederhana pengelolaan nilai mahasiswa menggunakan array.

Fitur minimal:

1. Input 10 nilai
2. Tampilkan nilai tertinggi & terendah
3. Hitung rata-rata
4. Hitung jumlah mahasiswa lulus (>= 60)
5. Analisis kompleksitas tiap operasi

## Struktur Repository

```
01-array/
    main.py
    fungsi_array.py
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
