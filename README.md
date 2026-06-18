Struktur ini menggambarkan sistem manajemen bengkel mobil dengan entitas utama:
Pelanggan → atribut: pel_id, nama, kontak.
Kendaraan → atribut: ken_id, pel_id, plat_nomor, model.
Service → atribut: service_id, tanggal, deskripsi.
Montir → atribut: montir_id, nama_montir, keahlian.
Sparepart → atribut: part_id, nama_part, harga.
Invoice → atribut: invoice_id, service_id, total_biaya, status_bayar.
Pelanggan memiliki Kendaraan (1:N).
Kendaraan ditangani oleh Service (1:N).
Service dikerjakan oleh Montir (M:N).
Service menggunakan Sparepart (M:N).
Service dicatat dalam Invoice (1:1).

Dengan ERD ini, alur data bengkel mobil bisa dipahami: mulai dari pelanggan membawa kendaraan, montir melakukan service dengan sparepart, hingga pencatatan biaya dalam invoice.

DFD Level 0 (Context Diagram)
Menunjukkan interaksi antara Pelanggan, Montir, dan Admin dengan Sistem Bengkel Mobil.
Alur data mencakup:
Data Kendaraan dari pelanggan ke sistem.
Penyelesaian Servis dari montir ke sistem.
Invoice & Pembayaran dari admin ke sistem

Alur data mencakup:
Data Kendaraan dari pelanggan ke sistem.
Penyelesaian Servis dari montir ke sistem.
Invoice & Pembayaran dari admin ke sistem.
Sistem terhubung dengan dua data store utama: Data Kendaraan dan Data Servis.

DFD Level 1 (Proses Detail)
Memecah sistem menjadi empat proses utama:
Penerimaan Servis → mencatat data pelanggan dan kendaraan.
Pelaksanaan Servis → montir melakukan servis dan mencatat sparepart yang digunakan.
Pembayaran & Invoice → admin membuat invoice dan mencatat transaksi.
Feedback Pelanggan → pelanggan memberikan ulasan dan rating.
Setiap proses terhubung dengan data store seperti Data Pelanggan, Data Sparepart, Data Invoice, dan Data Feedback.

Diagram ini menggambarkan alur data lengkap dari pelanggan datang ke bengkel hingga pembayaran dan pemberian feedback.
Diagram ini menggambarkan alur kerja utama dari pelanggan datang hingga proses servis dan pembayaran selesai, dengan empat swimlane:
Pelanggan → memulai proses dengan menginput data kendaraan, melakukan pembayaran, dan memberi feedback.
Admin → membuat formulir servis dan invoice.
Montir → memeriksa kendaraan, mengecek sparepart, dan melakukan perbaikan.
Sistem Bengkel Mobil → mencatat data servis, memperbarui status pembayaran, dan menyimpan feedback.

Pelanggan datang → input data kendaraan.
Admin membuat formulir servis.
Montir memeriksa kendaraan dan mengecek sparepart.
Jika sparepart tidak ada → sistem menampilkan notifikasi stok kosong.
Jika tersedia → montir memperbaiki kendaraan.
Setelah servis selesai → sistem mencatat status “Servis Selesai”.
Admin membuat invoice → pelanggan melakukan pembayaran.
Sistem memperbarui status menjadi “Lunas”.
Pelanggan memberikan feedback dan rating.
Proses berakhir di titik End.

Diagram ini membantu memahami urutan aktivitas dan tanggung jawab setiap aktor dalam sistem bengkel mobil.

Diagram ini memperlihatkan urutan interaksi antara empat aktor utama:
Pelanggan → mengirim permintaan servis dan melakukan pembayaran.
Admin → memverifikasi data, membuat invoice, dan mengelola transaksi.
Sistem Bengkel Mobil → memproses data servis, mengirim instruksi, dan menyimpan hasil.
Montir → menerima instruksi servis, melakukan pemeriksaan, dan mengirim hasil diagnosa.

Alur utama interaksi:
Pelanggan mengirim Permintaan Servis ke Admin.
Admin memverifikasi data dan mengirim Data Servis ke Sistem.
Sistem meneruskan Instruksi Servis ke Montir.
Montir melakukan pemeriksaan kendaraan dan mengirim Hasil Diagnosa ke Sistem.
Sistem mengirim Status Servis ke Admin.
Admin membuat dan mengirim Invoice ke Pelanggan.
Pelanggan melakukan Pembayaran ke Sistem.
Sistem mengonfirmasi pembayaran dan mengirim Update “Lunas” ke Admin.
Pelanggan memberikan Feedback, lalu Sistem menyimpan Data Feedback.

Diagram ini menampilkan struktur kelas dan relasi antar objek utama dalam sistem bengkel:
Pelanggan → atribut: pel_id, nama, kontak.
Kendaraan → atribut: ken_id, pel_id, plat_nomor, model.
Service → atribut: service_id, tanggal, deskripsi; metode: tambahSparepart(), assignMontir().
Montir → atribut: montir_id, nama_montir, keahlian.
Sparepart → atribut: part_id, nama_part, harga.
Invoice → atribut: invoice_id, service_id, total_biaya, status_bayar.

Relasi antar kelas:
Pelanggan memiliki Kendaraan (1:N).
Kendaraan ditangani oleh Service (1:N).
Service dikerjakan oleh Montir (M:N).
Service menggunakan Sparepart (M:N).
Service dicatat dalam Invoice (1:1).

Diagram ini membantu memahami struktur logis sistem bengkel mobil — bagaimana setiap kelas saling berhubungan untuk mendukung proses servis, penggunaan sparepart, dan pencatatan transaksi.

Diagram ini menampilkan tiga aktor utama:
Pelanggan → melakukan Melihat Menu, Memesan Makanan & Minuman, Melakukan Pembayaran, dan Memberi Feedback.
Relasi <<include>> menghubungkan Melihat Menu ke Memesan Makanan & Minuman.
Relasi <<extend>> menghubungkan Memesan Makanan & Minuman ke Memberi Feedback.

Kasir → menangani Menerima Pesanan, Mengelola Transaksi, Mencetak Struk, dan Mengelola Stok.
Manajer → bertanggung jawab atas Melihat Laporan Penjualan, Mengelola Menu, dan Mengatur Karyawan.

Diagram ini menggambarkan alur kerja lengkap dari pelanggan hingga manajemen cafe — mulai dari pemesanan hingga pengelolaan operasional.
Diagram ini menampilkan objek-objek nyata yang terlibat dalam satu transaksi di cafe:
Pelanggan1 → pel_id = 101, nama = "Budi", kontak = "08123456789".
Meja3 → meja_no = 3, kapasitas = 4.
Pesanan1 → order_id = 2001, tgl_pesanan = "2024-05-01", status = "Diproses".
Menu1 → nama = "Nasi Goreng", harga = 25000.
Menu2 → nama = "Latte", harga = 20000.
Kasir1 → nama = "Susi", shift = "Pagi".
Struk1 → struk_id = 9001, total = 45000, metode_bayar = "Tunai".

Relasi antar objek:
Pelanggan1 dan Meja3 terhubung ke Pesanan1.
Pesanan1 terhubung ke Menu1 dan Menu2 (item pesanan).
Pesanan1 juga terhubung ke Kasir1 (yang memproses transaksi) dan Struk1 (hasil pembayaran).
