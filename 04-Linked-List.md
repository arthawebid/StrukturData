# 📚 PERTEMUAN 4 Double Linked List & Circular Linked List

## 🎯 Tujuan Pembelajaran

Mahasiswa mampu:
1. Memahami Double Linked List.  
2. Memahami Circular Linked List.  
3. Menganalisis perbedaan ketiga jenis Linked List.  
4. Mengimplementasikan Double Linked List.




---

1. Double Linked List

Node memiliki:

data

next

prev


Struktur:

struct Node {
    int data;
    struct Node* next;
    struct Node* prev;
};

Ilustrasi:

NULL ← [Prev|Data|Next] ↔ [Prev|Data|Next] → NULL

Keunggulan:

Bisa traversal dua arah

Delete lebih mudah jika node diketahui


Kekurangan:

Memori lebih besar

Implementasi lebih kompleks



---

2. Circular Linked List

Ciri:

Node terakhir menunjuk ke node pertama.

Tidak ada NULL.


Ilustrasi:

[Data|Next] → [Data|Next]  
   ↑                        ↓  
   ←──────────────  

Digunakan pada:

Round Robin Scheduling

Sistem antrian melingkar



---

3. Perbandingan Jenis Linked List

Jenis	Pointer	Arah	Kompleksitas

Single	1	Satu arah	Sederhana
Double	2	Dua arah	Lebih fleksibel
Circular	1/2	Melingkar	Efisien untuk sistem loop



---

🧪 Praktikum Pertemuan 4

1. Buat Double Linked List:

Insert awal

Insert akhir

Delete node tertentu



2. Buat Circular Linked List sederhana:

Tambah 4 data

Tampilkan dengan looping hingga kembali ke head
