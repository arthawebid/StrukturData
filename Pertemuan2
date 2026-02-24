# Pertemuan 2 – Rekursi (Recursive Thinking & Problem Solving)

---

# 1️⃣ Capaian Pembelajaran

Setelah mengikuti pertemuan ini, mahasiswa mampu:

1. Menjelaskan konsep rekursi secara formal
2. Mengidentifikasi base case dan recursive case
3. Menggambarkan call stack dari fungsi rekursif
4. Menganalisis kompleksitas waktu dan ruang sederhana
5. Mengimplementasikan rekursi untuk masalah numerik dan string
6. Membandingkan rekursi dan iterasi

---

# 2️⃣ Dasar Teori

---

## 2.1 Definisi Rekursi

Rekursi adalah teknik pemrograman di mana suatu fungsi menyelesaikan masalah dengan memanggil dirinya sendiri pada sub-masalah yang lebih kecil.

Menurut Cormen dkk. [1], pendekatan rekursif bekerja dengan prinsip:

> “Solve a problem by solving smaller instances of the same problem.”

Rekursi membutuhkan dua komponen utama:

### ✅ Base Case

Kondisi berhenti untuk mencegah infinite recursion.

### ✅ Recursive Case

Pemanggilan ulang fungsi dengan parameter yang lebih kecil.

---

## 2.2 Struktur Umum Rekursi

```python
def fungsi(n):
    if kondisi_berhenti:
        return nilai
    return fungsi(n-1)
```

Tanpa base case → terjadi **infinite recursion** → stack overflow.

---

## 2.3 Cara Kerja Call Stack

Setiap pemanggilan fungsi akan:

1. Disimpan dalam stack memory
2. Menunggu hingga pemanggilan berikutnya selesai
3. Dibuka kembali dari bawah ke atas

Menurut Goodrich dkk. [2], penggunaan rekursi memiliki implikasi langsung terhadap kompleksitas ruang karena bergantung pada tinggi stack pemanggilan.

---

## 2.4 Kompleksitas Rekursi

### Kompleksitas Waktu

Bergantung pada jumlah pemanggilan fungsi.

Contoh:

* Faktorial → O(n)
* Fibonacci naif → O(2ⁿ)

### Kompleksitas Ruang

Bergantung pada kedalaman rekursi (depth).

Jika depth = n → ruang O(n).

---

# 3️⃣ Praktikum Inti

---

# 🔹 Latihan 1 – Faktorial

### Definisi Matematis

[
n! = n \times (n-1)!
]

Base case:
[
0! = 1
]

### Implementasi

```python
def faktorial(n):
    if n == 0:
        return 1
    return n * faktorial(n-1)
```

### Analisis

* Waktu: O(n)
* Ruang: O(n)

---

# 🔹 Latihan 2 – Fibonacci (Naif)

Relasi:

[
F(n) = F(n-1) + F(n-2)
]

Implementasi:

```python
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n-1) + fibonacci(n-2)
```

Konsep ini dikenal sebagai Fibonacci sequence.

Analisis:

* Waktu: O(2ⁿ)
* Ruang: O(n)

Diskusi kelas:
Mengapa sangat lambat?
→ Terjadi perhitungan ulang (overlapping subproblems).

---

# 🔹 Latihan 3 – Penjumlahan Array

```python
def jumlah(arr, n):
    if n == 0:
        return arr[0]
    return arr[n] + jumlah(arr, n-1)
```

Diskusi:

* Bagaimana jika array kosong?
* Alternatif dengan iterasi?

---

# 🔹 Latihan 4 – Reverse String

```python
def reverse(s):
    if len(s) <= 1:
        return s
    return reverse(s[1:]) + s[0]
```

Analisis:

* Waktu: O(n²) (karena slicing)
* Ruang: O(n)

---

# 🔹 Latihan 5 – Pangkat (Exponentiation)

[
x^n = x \times x^{n-1}
]

```python
def pangkat(x, n):
    if n == 0:
        return 1
    return x * pangkat(x, n-1)
```

Diskusi lanjutan:
Optimasi dengan Divide and Conquer (Exponentiation by Squaring) → O(log n)

---

# 4️⃣ Studi Kasus Konseptual

---

## 📌 Kasus 1 – Menghitung Digit Angka

Input:
1234

Proses:
1234 → 123 + 4
123 → 12 + 3

Implementasi:

```python
def jumlahDigit(n):
    if n == 0:
        return 0
    return n % 10 + jumlahDigit(n // 10)
```

---

## 📌 Kasus 2 – Climbing Stairs

Masalah:
Naik tangga n langkah, boleh 1 atau 2 langkah.

Relasi identik dengan Fibonacci.

Tujuan pedagogis:
Melatih mahasiswa mengenali pola rekursif dalam masalah nyata.

---

# 5️⃣ Perbandingan Rekursi vs Iterasi

| Aspek        | Rekursi           | Iterasi           |
| ------------ | ----------------- | ----------------- |
| Kode         | Lebih ringkas     | Lebih eksplisit   |
| Memori       | Menggunakan stack | Lebih hemat       |
| Kompleksitas | Tergantung kasus  | Biasanya stabil   |
| Cocok untuk  | Masalah hierarkis | Perulangan linear |

---

# 6️⃣ Mini Project (Fondasi ke Tree/Graph)

## 🎯 Project: Sistem Analisis Bilangan

Mahasiswa diminta membuat program yang:

1. Menghitung faktorial
2. Menghitung Fibonacci
3. Menghitung jumlah digit
4. Menghitung pangkat
5. Menghitung jumlah elemen array

Semua harus menggunakan rekursi.

### Tujuan

Agar mahasiswa memahami:

* Struktur pemanggilan bertingkat
* Kedalaman rekursi
* Kompleksitas waktu
* Pola berpikir divide & reduce

Project ini akan menjadi dasar untuk:

* Tree traversal (rekursi pada subtree)
* DFS pada graph

---

# 7️⃣ Soal Kuis (10 Nomor)

1. Jelaskan dua komponen utama rekursi.
2. Apa yang menyebabkan stack overflow?
3. Gambarkan call stack untuk faktorial(4).
4. Tentukan kompleksitas waktu Fibonacci naif.
5. Mengapa slicing memperburuk kompleksitas reverse string?
6. Apa perbedaan base case dan recursive case?
7. Jika rekursi memiliki depth n, berapa kompleksitas ruangnya?
8. Mengapa Fibonacci naif tidak efisien?
9. Ubah fungsi rekursif pangkat menjadi iteratif.
10. Berikan contoh masalah nyata yang cocok diselesaikan dengan rekursi.

---

# 8️⃣ Template Laporan Praktikum Mahasiswa

---

## HALAMAN JUDUL

Nama
NIM
Mata Kuliah
Pertemuan
Tanggal

---

## 1. Tujuan

Tuliskan capaian pembelajaran.

---

## 2. Dasar Teori

Jelaskan:

* Definisi rekursi
* Base case
* Recursive case
* Kompleksitas

---

## 3. Implementasi Program

Sertakan:

* Source code
* Output program

---

## 4. Analisis

* Gambarkan call stack salah satu fungsi
* Analisis waktu
* Analisis ruang

---

## 5. Kesimpulan

Refleksi pemahaman pribadi.

---

# 9️⃣ Rubrik Penilaian

| Aspek                 | Bobot |
| --------------------- | ----- |
| Implementasi benar    | 35%   |
| Pemahaman konsep      | 25%   |
| Analisis kompleksitas | 20%   |
| Dokumentasi           | 10%   |
| Kerapian              | 10%   |

---

# 🔟 Referensi
[1] T. H. Cormen, C. E. Leiserson, R. L. Rivest, and C. Stein, *Introduction to Algorithms*, 3rd ed. Cambridge, MA, USA: MIT Press, 2009.
[2] M. T. Goodrich, R. Tamassia, and M. H. Goldwasser, *Data Structures and Algorithms in Python*. Hoboken, NJ, USA: Wiley, 2013.
[3] R. Sedgewick and K. Wayne, *Algorithms*, 4th ed. Boston, MA, USA: Addison-Wesley, 2011.
