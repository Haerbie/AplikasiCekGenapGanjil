# Tugas 1: Aplikasi Cek Nomor Genap/Ganjil

### Pembuat
- **Nama**: Muhammad Irwan Habibie
- **NPM**: 2210010461

---

## 1. Deskripsi Program
Aplikasi ini memungkinkan pengguna untuk:
- Memasukkan sebuah angka pada TextField.
- Menekan tombol **Cek** untuk memverifikasi apakah angka tersebut genap atau ganjil.
- Hasil pengecekan ditampilkan pada JLabel di aplikasi.

## 2. Komponen GUI
- **JFrame**: Window utama aplikasi.
- **JPanel**: Panel untuk menampung komponen.
- **JLabel**: Menampilkan hasil apakah angka genap atau ganjil.
- **JTextField**: Input untuk memasukkan angka yang akan diperiksa.
- **JButton**: Tombol untuk melakukan pemeriksaan angka.

## 3. Logika Program
- Menggunakan struktur kondisional (if-else) untuk memeriksa apakah angka genap atau ganjil.
- Validasi input untuk memastikan pengguna hanya memasukkan angka.

## 4. Events
Menggunakan **ActionListener** dan **KeyAdapter** untuk mempermudah interaksi pengguna:

### A. Tombol Cek
Menampilkan hasil pemeriksaan angka (genap atau ganjil) setelah memvalidasi input.

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
### B. Key Adapter untuk membatasi input hanya angka
```java
    private void inputAngkaKeyTyped(java.awt.event.KeyEvent evt) {                                    
        char karakter = evt.getKeyChar();
        if (!Character.isDigit(karakter)) { // Memeriksa jika karakter bukan angka
            evt.consume(); // Mengabaikan input selain angka
        }
    }   
```

## 5. Variasi
Aplikasi ini memiliki variasi tambahan berikut:
### A. Pemeriksaan Bilangan Prima
```java
            String hasil = "Angka " + angka + " adalah ";
            hasil += (angka % 2 == 0) ? "Genap" : "Ganjil";
            hasil += (cekPrima(angka)) ? " dan Prima." : " dan Bukan Prima.";
```
### B. JOptionPane
Menampilkan pesan hasil dan pesan error menggunakan JOptionPane.
```java
         catch (NumberFormatException e) {
            JOptionPane.showMessageDialog(this, "Input tidak valid! Masukkan angka saja.", "Error", JOptionPane.ERROR_MESSAGE);
        }
```
### C. FocusListener
Menghapus isi JTextField saat mendapatkan fokus.
```java
    private void inputAngkaFocusGained(java.awt.event.FocusEvent evt) {                                       
        inputAngka.setText("");
    }  
```
## 6. Tampilan Saat di Run :
 ![TampilanPertambahanDuaAngka](https://github.com/user-attachments/assets/8e5dc7b0-e482-4582-adac-9bc13f5f5dc1)
  

## Indikator Penilaian:

| No  | Komponen         |  Persentase  |
| :-: | --------------   |   :-----:    |
|  1  | Komponen GUI     |    20    |
|  2  | Logika Program   |    20    |
|  3  | Events           |    15    |
|  4  | Kesesuaian UI    |    15    |
|  5  | Memenuhi Variasi |    30    |
|     | TOTAL        | 100 |
