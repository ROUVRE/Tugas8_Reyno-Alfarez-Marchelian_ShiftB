# Tugas 8 Praktikum Pemrograman Mobile

Nama: Reyno Alfarez Marchelian

NIM: H1D022111

Shift: B

## Tampilan Awal

![Lampiran Tampilan Awal](daftar-mahasiswa_awal.png)

## Tampilan Tambah Mahasiswa

![Lampiran Tampilan Tambah Mahasiswa](tambah-mahasiswa.png)

Memanggil fungsi ```openModalTambah()``` untuk menampilkan halaman tambah mahasiswa. </br>
Fungsi ```tambahMahasiswa()``` mengambil nilai input dari form dan mengirim data ke ```tambah.php``` menggunakan fungsi ```this.api.tambah(data, 'tambah.php')```.</br>
Data mahasiswa diterima API. Jika nama dan jurusan tidak kosong, data disimpan ke tabel mahasiswa</br> 
Kemudian data mahasiswa akan direfresh dan modal tambah mahasiswa akan ditutup dengan fungsi ```this.modal.dismiss();```.

## Tampilan Daftar Mahasiswa Setelah Penambahan Data

![Lampiran Tampilan Setelah Tambah](daftar-mahasiswa_new.png)

Program menggunakan fungsi ```getMahasiswa()``` untuk memanggil API tampil.php dan menampilkan seluruh data mahasiswa yang ada di database dalam bentuk komponen card.

## Tampilan Edit Mahasiswa

![Lampiran Tampilan Edit](edit-mahasiswa.png)

Memanggil fungsi ```openModalEdit()``` untuk menampilkan halaman edit mahasiswa. </br>
Fungsi ```editMahasiswa()``` mengambil nilai input dari form dan mengirim data ke ```edit.php``` menggunakan fungsi ```this.api.edit(data, 'edit.php')```.</br>
Data mahasiswa yang baru akan diterima API. Data yang baru akan disimpan ke tabel mahasiswa, kemudian data mahasiswa akan direfresh dan modal edit mahasiswa akan ditutup menggunakan fungsi ```this.modal.dismiss()```.

## Tampilan Daftar Mahasiswa Setelah Editing

![Lampiran Tampilan Setelah Di-edit](daftar-mahasiswa_edited.png)

## Tampilan Konfirmasi Hapus Data

![Lampiran Tampilan Konfirmasi Hapus](konfirmasi-hapus.png)

Pada halaman ```mahasiswa.page.html```, terdapat kode berikut pada komponen tombol hapus.

```
<ion-button color="danger" slot="end" (click)="konfirmasiHapus(item.id)">
  Hapus
</ion-button>
```

Hal ini berfungsi untuk memanggil fungsi ```konfirmasiHapus(item.id)``` ketika tombol hapus ditekan.

fungsi ```konfirmasiHapus(id: any)``` berfungsi menampilkan modal konfirmasi dengan opsi "Ya" dan "Tidak" ketika menekan tombol hapus di halaman daftar mahasiswa.</br>
Jika memilih "Ya", maka data akan dihapus dengan memanggil fungsi ```hapusMahasiswa(id)```.</br>
Jika memilih "Tidak", modal akan ditutup tanpa aksi lebih lanjut.

fungsi ```hapusMahasiswa(id: any)``` menerima parameter ID mahasiswa yang ingin dihapus. </br>
Fungsi ```this.api.hapus(id, 'hapus.php?id=')``` digunakan untuk mengirim permintaan hapus ke endpoint API ```hapus.php```. </br>
Kemudian memanggil fungsi ```getMahasiswa()``` untuk memperbarui tampilan daftar siswa.

## Tampilan Daftar Mahasiswa Setelah Data Dihapus

![Lampiran Tampilan Setelah Dihapus](daftar-mahasiswa_deleted.png)
