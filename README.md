

##  **Arsitektur Multiprosesor**

Multiprosesor adalah sistem komputer yang menggunakan **lebih dari satu CPU** (Central Processing Unit) untuk menjalankan proses-proses dalam sistem. Tujuannya adalah meningkatkan kinerja sistem, efisiensi pemrosesan, dan kemampuan multitasking.

Ada dua jenis utama:

1. **Non-SMP (Non-Symmetric Multiprocessing)**
2. **SMP (Symmetric Multiprocessing)**

![image](https://github.com/user-attachments/assets/83042bae-c831-4531-9216-b3f4ec5cfbb3)

---

## **1. Arsitektur Multiple Prosesor (Non-SMP) (**

###  **Karakteristik Utama:**

* Tiap CPU memiliki **memori lokal sendiri**.
* CPU tidak bisa langsung mengakses memori milik CPU lain.
* Dibutuhkan **jaringan interkoneksi** agar CPU bisa berkomunikasi dan berbagi data.
* Sistem lebih **kompleks** dan sulit disinkronisasi.

###  **Komponen dalam Gambar:**

* **CPU 1 & CPU 2**: Dua prosesor bekerja secara **terpisah**, masing-masing punya memori sendiri.
* **Memori lokal**: Tiap CPU hanya bisa akses memorinya sendiri, jadi pembagian data harus melalui jaringan.
* **Jaringan Interkoneksi**: Digunakan untuk menghubungkan CPU, memori, I/O, dan perangkat lainnya.
* **I/O, Disk, dan Periferal**: Diakses melalui jaringan, sehingga ada latensi (keterlambatan) akses.

###  **Konsekuensi Teknis:**

* **Komunikasi antar CPU lambat** karena melalui interkoneksi.
* **Manajemen memori dan data lebih sulit**, karena tidak ada memori bersama.
* **Kurang efisien** untuk aplikasi yang memerlukan pertukaran data antar CPU secara intensif.
* Biasanya digunakan dalam sistem **terdistribusi** atau **cluster komputer**, bukan satu komputer tunggal.

---

##  **2. Arsitektur Multiprosesor Simetris (SMP)**

###  **Karakteristik Utama:**

* Semua CPU **berbagi akses ke memori yang sama** (memori bersama).
* Semua CPU juga bisa mengakses **semua perangkat I/O secara langsung**.
* Komponen utama terhubung melalui **bus sistem**.

### **Komponen dalam Gambar:**

* **CPU 1, 2, dan 3**: Semua bekerja secara **simetris**, tidak ada pembagian tugas khusus. Bisa berbagi beban kerja.
* **Bus Sistem**: Jalur komunikasi tunggal untuk menghubungkan semua CPU dengan memori dan perangkat lain.
* **Memori Bersama**: Semua CPU dapat membaca dan menulis data dari memori yang sama.
* **Pengontrol I/O & Disk**: Perangkat I/O dikelola oleh CPU manapun, tidak eksklusif.
* **Periferal dan DISK 1 & DISK 2**: Bisa diakses oleh semua CPU tanpa perlu jaringan tambahan.

###  **Konsekuensi Teknis:**

* **Kinerja lebih tinggi** karena tidak perlu transfer data antar memori.
* **Lebih mudah dikelola** oleh sistem operasi modern (misalnya Linux, Windows Server).
* **Beban kerja lebih seimbang**, karena semua CPU bisa digunakan sesuai kebutuhan.
* Cocok untuk sistem **server**, **komputasi paralel**, dan **aplikasi multitasking**.

---

##  **Perbandingan Detail: Non-SMP vs SMP**

| Aspek                       | Non-SMP                           | SMP                                         |
| --------------------------- | --------------------------------- | ------------------------------------------- |
| Akses memori                | Terpisah (lokal)                  | Bersama                                     |
| Komunikasi antar CPU        | Lewat jaringan interkoneksi       | Lewat memori bersama (langsung)             |
| Efisiensi kerja sama CPU    | Rendah                            | Tinggi                                      |
| Pengelolaan I/O             | Terpisah                          | Terintegrasi                                |
| Kompleksitas sistem         | Tinggi (butuh pengaturan rumit)   | Lebih sederhana                             |
| Contoh penerapan            | Cluster komputer, superkomputer   | Server multiprosesor, workstation           |
| Skalabilitas                | Bisa lebih fleksibel secara fisik | Terbatas pada arsitektur bus                |
| Keandalan (fault tolerance) | Lebih baik jika satu CPU gagal    | Lebih rendah bila memori bersama bermasalah |

---

## **Kesimpulan Akhir:**

* **Non-SMP** cocok untuk sistem yang perlu **pemrosesan terpisah** dan **tidak banyak komunikasi** antar CPU. Misalnya: komputasi besar yang dibagi menjadi blok-blok terisolasi.
* **SMP** cocok untuk sistem yang memerlukan **kerja sama antar CPU**, **akses data bersama**, dan **kinerja yang tinggi dalam multitasking**.

---

##  **Catatan Tambahan untuk Mahasiswa:**

* Sistem operasi **modern lebih mendukung SMP**, karena lebih mudah dalam pengelolaan proses dan memori.
* Perkembangan teknologi multi-core saat ini adalah **implementasi SMP** dalam satu chip (misalnya, CPU quad-core di laptop).
* Penting untuk memahami perbedaan ini agar bisa memilih arsitektur sesuai kebutuhan aplikasi (server, komputasi paralel, dll.)

---

