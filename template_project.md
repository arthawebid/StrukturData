# 📚 Struktur Data – Pertemuan 1
## Pengantar Struktur Data dan Kompleksitas Algoritma

---

## 👤 Identitas Mahasiswa

- Nama        : [ISI NAMA]
- NIM         : [ISI NIM]
- Kelas       : [ISI KELAS]
- Mata Kuliah : Struktur Data

---

# 🎯 Tujuan Praktikum

1. Memahami konsep dasar struktur data.
2. Memahami hubungan algoritma dan struktur data.
3. Menganalisis kompleksitas waktu (Big-O).
4. Mengimplementasikan contoh program sederhana.

---

# 📖 Ringkasan Teori

## 1. Apa itu Struktur Data?

Struktur data adalah cara mengorganisasi dan menyimpan data agar dapat digunakan secara efisien.

Menurut Cormen et al. (2009), pemilihan struktur data sangat mempengaruhi efisiensi algoritma.

Contoh:
- Array
- List
- Stack
- Queue
- Tree
- Graph

---

## 2. Kompleksitas Algoritma

Kompleksitas waktu digunakan untuk mengukur efisiensi algoritma terhadap ukuran input (n).

Contoh:
- O(1)  → Konstan
- O(n)  → Linear
- O(n²) → Kuadratik

---

# 💻 Implementasi Program

## 1️⃣ Program Kompleksitas O(1)

```python
def constant(n):
    return n * 2

print(constant(10))
