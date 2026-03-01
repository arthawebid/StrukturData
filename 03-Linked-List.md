# 📚 PERTEMUAN 3 Konsep Dasar Linked List & Single Linked List

## 🎯 Tujuan Pembelajaran

Mahasiswa mampu:

1. Memahami konsep dasar struktur data Linked List.


2. Menjelaskan perbedaan array dan linked list.


3. Memahami struktur node.


4. Mengimplementasikan Single Linked List sederhana.




---

1. Konsep Dasar Linked List

Linked List adalah struktur data linear dinamis yang terdiri dari sekumpulan node yang saling terhubung melalui pointer (referensi alamat memori).

Berbeda dengan array:

Array → alokasi memori berurutan (contiguous memory).

Linked List → alokasi memori tidak harus berurutan.


Menurut Mark Allen Weiss dalam buku
Data Structures and Algorithm Analysis in C,
Linked List memberikan fleksibilitas dalam manajemen memori karena elemen dapat ditambahkan atau dihapus tanpa harus menggeser elemen lainnya.


---

2. Struktur Node

Setiap node terdiri dari:

Data

Pointer (next)


Ilustrasi:

[Data | Next] → [Data | Next] → [Data | NULL]

Struktur dalam C:

struct Node {
    int data;
    struct Node* next;
};


---

3. Karakteristik Single Linked List

Hanya memiliki satu pointer (next)

Traversal satu arah

Node terakhir menunjuk ke NULL



---

4. Operasi Dasar

1. Insert di awal


2. Insert di akhir


3. Delete


4. Traversal




---

5. Kompleksitas Waktu

Operasi	Kompleksitas

Akses elemen	O(n)
Insert awal	O(1)
Insert akhir	O(n)
Delete	O(n)


Menurut Cormen dkk. dalam
Introduction to Algorithms,
Linked List unggul dalam operasi insert/delete dibanding array karena tidak memerlukan pergeseran elemen.


---

🧪 Praktikum Pertemuan 3

Latihan 1

Buat program:

Insert 5 data

Tampilkan seluruh data


Latihan 2

Tambahkan fungsi:

Insert di awal

Insert di akhir




📊 ANALISIS KONSEPTUAL (Pemahaman Mahasiswa)

Mahasiswa harus mampu menjawab:

1. Mengapa akses array lebih cepat daripada linked list?


2. Mengapa insert di awal linked list lebih cepat?


3. Kapan linked list lebih baik daripada array?


4. Apa kelemahan utama linked list?




---

💻 PROJECT TUGAS AKHIR LINKED LIST

🎓 Project: Sistem Manajemen Data Mahasiswa

Deskripsi:

Buat program menggunakan Double Linked List untuk:

Menu:

1. Tambah Mahasiswa


2. Hapus Mahasiswa


3. Edit Data


4. Cari Mahasiswa


5. Tampilkan Semua


6. Sorting berdasarkan NIM


7. Keluar



Struktur Data:

NIM

Nama

Jurusan

IPK


Ketentuan:

Gunakan Double Linked List

Terapkan Searching

Terapkan Sorting

Gunakan Modular Function

Tambahkan validasi input



---

📈 Kriteria Penilaian

Aspek	Bobot

Struktur Program	20%
Implementasi Linked List	30%
Searching & Sorting	20%
UI & Interaksi	10%
Dokumentasi & Laporan	20%



---

📌 Referensi

1. Weiss, Mark Allen. Data Structures and Algorithm Analysis in C.


2. Cormen, Thomas H. dkk. Introduction to Algorithms.


3. Modul Praktikum Struktur Data.



