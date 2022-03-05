
# Excel-FungsiAUTOSUM-SUMIF-SUMIFS

## A. Fungsi Auto SUM
 - Digunakan untuk menjumlahkan data di sebuah kolom/field
 - Perlu diingat bahwa pastikan tidak ada cell yang kosong saat akan melakukan proses/menggunakan fungsi AUTO SUM, karena jika ada cell yang kosong maka AUTO SUM akan berhenti pada cell yang kosong dan mencetak hasil penjumlahan pada cell kosong tersebut.

#### Cara Memanfaatkan/Menggunakan Fungsi AUTO SUM
- Kita akan menjumlahkan kolom/field “Total”, pertama dengan cara mem-blok seluruh data yang akan dijumlahkan, ingat untuk mempercepat menge-blok dengan cara Ctrl + Shift + arah panah (dalam hal ini menggunakan arah panah ke bawah saja) > kemudian klik home > kemudian klik AUTO SUM. Untuk mempermudah lihat gambar di bawah ini.
###
![ss1](https://user-images.githubusercontent.com/86678205/156878144-5548914e-d038-4b32-bc68-593034fcb122.PNG)

## B. Fungsi SUM-IF
 - Digunakan untuk menggali informasi yang ada di data

#### B.1. Menggunakan Fungsi SUM-IF untuk Mengetahui Berapa total penjualan per lokasi dalam setahun?
Dengan cara sebagai berikut :
- 1.) Membuat tabel baru yang berisi dua kolom/field baru yaitu kolom Market & kolom penjualan pertahun. Kolom Market ada 3 data sesuai isi data yaitu Jatim, Jabodetabek, Jateng. Seperti Gambar di bawah.
###
![ss1sumif](https://user-images.githubusercontent.com/86678205/156879857-cec7277a-0031-421c-9f6a-9eb75eab4e00.PNG)

- 2.) Kemudian kita gunakan rumus/fungsi SUM-IF untuk mencari penjualan pertahun
Struktur fungsi/rumus SUM-IF pada excel yaitu :
```http
  =SUMIF(range; criteria; [sum_range])
```
Dalam struktur rumus tersebut berarti SUM-IF mempunyai 3 parameter yaitu range, criteria, dan [sum_range]. 

Karena acuannya adalah lokasi maka:
```http
  Parameter Range diisi semua baris yang ada di cell lokasi (semua data di kolom lokasi) (C4:C23)
```
```http
  Parameter Criteria diisi Jabodetabek (karena market/lokasi pertama yang akan dicari) (K4)
```
```http
  Parameter [sum_range] diisi semua baris yang ada di cell total (semua data di kolom total) (l4:l23)
```
###
![ss2sumif](https://user-images.githubusercontent.com/86678205/156879889-fb95f7fe-c2cd-440d-9dd4-479ef8eab1f1.PNG)

Perlu sangat penting diingat bahwa agar dapat ditarik kebawah menghasilkan nilai yang sesuai atau diingkan dengan formula/fungsi/rumus yang sama maka harus diberi nilai absolut dengan cara lakukan blok di stuktur rumus/fungsi pada (l4:l23) & (C4:C23) > kemudian tekan f4 untuk memberi tanda $ pada (l4:l23) & (C4:C23) agar tidak berubah-ubah saat ditarik kebawah, sehingga yang berubah-ubah hanya parameter Criteria (marketnya saja).
###
![ss3sumif](https://user-images.githubusercontent.com/86678205/156879941-b5780b66-e34f-4b0c-865c-fae28f705515.PNG)

## C. Fungsi SUM-IFS
- Digunakan untuk menggali informasi yang ada di data yang persoalannya/kasusnya membutuhkan lebih dari satu acuan

#### B.1. Menggunakan Fungsi SUM-IFS untuk Mengetahui Berapa total penjualan per lokasi dalam setiap bulan?
Dengan cara sebagai berikut :
- 1.) Membuat table baru yang berisi tiga kolom/field baru yaitu kolom Bulan, kolom Market & kolom jumlah. Seperti Gambar di bawah.
###

- 2.) Berbeda dengan kasus sebelumnya tadi (SUM-IF) yang acuannya hanya lokasi, di kasus ini terdapat dua acuan yaitu bulan & lokasi. Maka dari itu kita menggunakan rumus/fungsi SUM-IFS
Struktur fungsi/rumus SUM-IFS pada excel yaitu :
```http
  =SUMIFS(sum_range; criteria_range1; criteria1; [criteria_range2; ...)
```
Acuannya adalah bulan & market
kriteria pertama yaitu bulan maka:
```http
  Parameter Sum_range diisi semua baris yang ada di cell total (semua data di kolom total) (l4:l23)
```
```http
  Parameter criteria_range1 diisi semua baris yang ada di cell bulan (semua data di kolom bulan) (b4:b23)
```
```http
  Parameter criteria1 diisi bulan ke 1 pada tabel yang baru (k10) untuk memfilter bulan pertama/ke-1 saja
```
selanjutnya kriteria kedua yaitu market maka:
```http
  Parameter criteria_range2 diisi semua baris yang ada di cell lokasi (semua data di kolom lokasi) (c4:c23)
```
```http
  Parameter criteria2 diisi market/lokasi Jabodetabek pada tabel yang baru (l10) untuk memfilter lokasi Jabodetabek saja
```
Perlu sangat penting diingat bahwa agar dapat ditarik kebawah menghasilkan nilai yang sesuai atau diingkan dengan formula/fungsi/rumus yang sama maka harus diberi nilai absolut dengan cara lakukan blok di stuktur rumus/fungsi pada (l4:l23), (b4:b23), & (c4:c23) > kemudian tekan f4 untuk memberi tanda $ pada (l4:l23), (b4:b23), & (c4:c23) agar tidak berubah-ubah saat di tarik kebawah, sehingga yang berubah-ubah hanya parameter marketnya (lokasi) saja.

Selanjutnya mencari dengan cara yang sama pada lokasi Jatim & Jateng. Untuk mempercepat silahkan copy-paste dua kali tabel market Jabodetabek, kemudian ganti nama market menjadi Jatim dan satunya Jateng, selanjutnya tarik ke bawah kolom jumlah maka akan berubah secara otomatis karena sudah dikasih/diberi nilai absolut.
