# Latihan Inheritance
# Soal
<img src= "soal.jpeg">

# 1. Kelas ```Pegawai``` (Superclass)
a. Atribut (```nama``` dan ```gajiPokok```)
Kelas ```Pegawai``` memiliki dua atribut:

```nama```: untuk menyimpan nama pegawai (tipe data ```String```).

```gajiPokok```: untuk menyimpan gaji pokok pegawai (tipe data ```double```).

Kedua atribut ini disimpan dalam mode ```private```, yang artinya hanya bisa diakses atau diubah menggunakan metode ```getter``` dan ```setter```. Konsep ini disebut **enkapsulasi**, yaitu menyembunyikan detail implementasi kelas agar data tetap aman dan hanya dapat dimodifikasi melalui metode yang tersedia.

b. Metode ```setNama(String nama)``` dan ```getNama()```

```setNama(String nama)```: Metode ini digunakan untuk mengatur (men-set) nilai dari atribut ```nama```.

```
public void setNama(String nama) {
    this.nama = nama;
}
```
```getNama()```: Metode ini digunakan untuk mendapatkan nilai dari atribut ```nama```.

```
public String getNama() {
    return nama;
}
```
c. Metode ```setGajiPokok(double gajiPokok)``` dan ```getGajiPokok()```

```setGajiPokok(double gajiPokok)```: Metode ini berfungsi untuk mengatur nilai gaji pokok.

```
public void setGajiPokok(double gajiPokok) {
    this.gajiPokok = gajiPokok;
}
```
```getGajiPokok()```: Metode ini berfungsi untuk mendapatkan nilai gaji pokok.

```
public double getGajiPokok() {
    return gajiPokok;
}
```
d. Metode ```cetakInfo()```

Metode ini mencetak informasi dari pegawai, yaitu nama dan gaji pokoknya.

```
public void cetakInfo() {
    System.out.println("Nama: " + getNama());
    System.out.println("Gaji Pokok: " + getGajiPokok());
}
```
```getNama()``` dan ```getGajiPokok()``` digunakan untuk mengambil data yang sudah diatur sebelumnya, kemudian data tersebut dicetak ke layar.
# 2. Kelas ```Manager``` (Subclass dari Pegawai)
**A. Atribut** ```tunjangan```

Kelas ```Manager``` menambahkan atribut baru yang tidak ada di kelas ```Pegawai```, yaitu ```tunjangan```, yang menyimpan tunjangan untuk seorang manajer (tipe ```double```). Seperti atribut di kelas induknya, ``tunjangan``` juga disimpan dalam mode ```private```.

**B. Metode** ```setTunjangan(double tunjangan)``` dan ```getTunjangan()```
```setTunjangan(double tunjangan)```: Metode ini mengatur nilai tunjangan.

```
public void setTunjangan(double tunjangan) {
    this.tunjangan = tunjangan;
}
```
```getTunjangan()```: Metode ini digunakan untuk mendapatkan nilai tunjangan.

```
public double getTunjangan() {
    return tunjangan;
}
```
**C. Override Metode** ```cetakInfo()```

Kelas ```Manager``` meng-override metode ```cetakInfo()``` dari kelas ```Pegawai```. Ini dilakukan karena selain mencetak nama dan gaji pokok, kita juga ingin mencetak tunjangan khusus untuk manajer.

```
@Override
public void cetakInfo() {
    super.cetakInfo();
    System.out.println("Tunjangan: " + getTunjangan());
}
```
```super.cetakInfo()``` memanggil metode ```cetakInfo()``` dari kelas induk ```(Pegawai)```, sehingga nama dan gaji pokok akan dicetak terlebih dahulu.

Setelah itu, metode ini mencetak nilai tunjangan dari manajer.

**D. Metode** ```cetakTunjangan()```

Metode ini khusus digunakan untuk mencetak tunjangan saja, tanpa mencetak atribut lain.

```
public void cetakTunjangan() {
    System.out.println("Tunjangan: " + getTunjangan());
}
```
# 3. Kelas ```Programmer``` (Subclass dari Pegawai)
**a. Atribut** ```bonus```

Kelas Programmer menambahkan atribut baru yaitu bonus, yang menyimpan bonus bagi seorang programmer (tipe ```double)```.

**b. Metode** ```setBonus(double bonus)``` dan ```getBonus()```

```setBonus(double bonus)```: Metode ini digunakan untuk mengatur nilai bonus.

```
public void setBonus(double bonus) {
    this.bonus = bonus;
}
```
```getBonus()```: Metode ini digunakan untuk mendapatkan nilai bonus.

```
public double getBonus() {
    return bonus;
}
```
**c. Override Metode** ```cetakInfo()```
Kelas ```Programmer``` juga meng-override metode ```cetakInfo()``` dari kelas induk. Selain mencetak nama dan gaji pokok, metode ini juga mencetak bonus untuk seorang programmer.

```
@Override
public void cetakInfo() {
    super.cetakInfo();
    System.out.println("Bonus: " + getBonus());
}
```
**d. Metode** ```cetakBonus()```

Metode ini digunakan untuk mencetak nilai bonus saja.

```
public void cetakBonus() {
    System.out.println("Bonus: " + getBonus());
}
```
# 4. Kelas ```Main``` (Untuk Uji Coba)

Kelas ```Main``` adalah tempat untuk menjalankan program dan menguji kelas-kelas yang sudah dibuat.

Membuat objek ```Manager``` dan ```Programmer```

Menetapkan nilai ```nama```, ```gajiPokok```, ```tunjangan``` (untuk manajer), dan ```bonus``` (untuk programmer).

Memanggil metode ```cetakInfo()``` untuk mencetak informasi lengkap dari objek-objek tersebut. 

```
public class Main {
    public static void main(String[] args) {
        // Membuat dan mengatur objek Manager
        Manager manager = new Manager();
        manager.setNama("Andi");
        manager.setGajiPokok(10000000);
        manager.setTunjangan(3000000);
        manager.cetakInfo();
        manager.cetakTunjangan();

        System.out.println();

        // Membuat dan mengatur objek Programmer
        Programmer programmer = new Programmer();
        programmer.setNama("Budi");
        programmer.setGajiPokok(8000000);
        programmer.setBonus(1500000);
        programmer.cetakInfo();
        programmer.cetakBonus();
    }
}
```
# Output
<img src=output1.png>

# Kesimpulan:

**Inheritance** (Pewarisan): Kelas Manager dan Programmer mewarisi atribut dan metode dari kelas Pegawai.

**Enkapsulasi:** Atribut-atribut pada tiap kelas disimpan dalam mode private untuk menjaga keamanan data, dan kita menggunakan metode setter dan getter untuk mengaksesnya.

**Polymorphism** (Polimorfisme): Metode cetakInfo() di-override oleh kelas Manager dan Programmer untuk menyesuaikan dengan kebutuhan masing-masing subclass.
