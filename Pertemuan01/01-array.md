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

## Contoh Jawaban yang Diharapkan (Arah Penalaran)

| Kebutuhan   | Struktur Data      | Alasan         |
| ----------- | ------------------ | -------------- |
| Data Pasien | List / Array       | Mudah disimpan |
| Antrian     | Queue              | FIFO           |
| Riwayat     | List / Linked List | Dinamis        |

Mahasiswa harus menjelaskan dalam bentuk analisis, bukan hanya menyebutkan jawaban.

---

# 💻 Praktikum Pertemuan 1

## Praktikum 1: Analisis Kompleksitas Sederhana

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

