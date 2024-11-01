# Aplikasi Cek Angka Genap, Ganjil, dan Prima

**Pembuat**: Muhammad Irwan Habibie  
**NPM**: 2210010461  
**Tugas 1**

## Deskripsi
Aplikasi ini adalah sebuah program GUI sederhana yang dibuat dengan Java Swing untuk memeriksa apakah angka yang dimasukkan adalah bilangan genap atau ganjil, sekaligus mengecek apakah angka tersebut merupakan bilangan prima. Hasil pengecekan ditampilkan dalam dialog pesan menggunakan `JOptionPane`.

## Fitur
- Memeriksa apakah angka yang dimasukkan adalah **Genap** atau **Ganjil**.
- Memeriksa apakah angka tersebut merupakan **Bilangan Prima**.
- Menampilkan pesan hasil dalam `JOptionPane` dengan status **Informasi**.
- Menampilkan pesan **Error** dalam `JOptionPane` jika input tidak valid.

## Struktur Tampilan GUI
1. **Label Utama**: Menampilkan judul "Aplikasi Cek Angka Genap Ganjil".
2. **Input Field**: Text field untuk memasukkan angka yang ingin diperiksa.
3. **Tombol Cek**: Tombol untuk memulai pengecekan genap/ganjil dan prima.

## Cara Penggunaan
1. Jalankan aplikasi.
2. Masukkan angka ke dalam kolom input.
3. Klik tombol **Cek** untuk melihat hasilnya.
4. Hasil akan muncul dalam dialog `JOptionPane` yang menunjukkan apakah angka tersebut genap atau ganjil, dan apakah angka tersebut merupakan bilangan prima atau bukan.

## Logika Utama
- **Genap/Ganjil**: Program memeriksa apakah angka habis dibagi 2 (`angka % 2 == 0`) untuk menentukan genap atau ganjil.
- **Bilangan Prima**: Program memiliki metode `cekPrima(int number)` yang memeriksa apakah sebuah angka hanya memiliki dua faktor (1 dan dirinya sendiri). Jika demikian, maka angka tersebut adalah bilangan prima.

## Kode Utama
### Fungsi Cek Angka dan Tampilkan Hasil
```java
private void tombolCekActionPerformed(java.awt.event.ActionEvent evt) {                                          
    String teksInput = inputAngka.getText();
    try {
        int angka = Integer.parseInt(teksInput);

        String hasil = "Angka " + angka + " adalah ";
        hasil += (angka % 2 == 0) ? "Genap" : "Ganjil";
        hasil += (cekPrima(angka)) ? " dan Prima." : " dan Bukan Prima.";

        JOptionPane.showMessageDialog(this, hasil, "Hasil", JOptionPane.INFORMATION_MESSAGE);
    } catch (NumberFormatException e) {
        JOptionPane.showMessageDialog(this, "Input tidak valid! Masukkan angka saja.", "Error", JOptionPane.ERROR_MESSAGE);
    }
}
```
### Fungsi untuk Mengecek Bilangan Prima
```java

private boolean cekPrima(int number) {
    if (number <= 1) return false;
    for (int i = 2; i <= Math.sqrt(number); i++) {
        if (number % i == 0) return false;
    }
    return true;
}
```
