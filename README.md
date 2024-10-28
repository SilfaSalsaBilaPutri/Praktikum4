# Latihan
Implementasikan java code diagram class berikut:

![Screenshot 2024-10-28 215404](https://github.com/user-attachments/assets/22cef7ad-795a-4a9d-97e9-1cd09734f520)

- Class BangunDatar
  ```
  abstract class BangunDatar {
    // Abstract methods for luas (area) and keliling (perimeter)
    abstract float luas();
    abstract float keliling();
  }
  ```
  Kelas abstrak bisa memiliki metode abstrak, yaitu metode yang hanya dideklarasikan tanpa implementasi, dan ini mengharuskan kelas turunannya untuk memberikan implementasi metode tersebut.

- Class Lingkaran
  ```
  class Lingkaran extends BangunDatar {
    int r;  // radius

    // Constructor
    public Lingkaran(int r) {
        this.r = r;
    }
    ```
    Mendefinisikan kelas bernama Lingkaran. Kelas Lingkaran mewarisi (menurunkan) kelas BangunDatar, yang merupakan kelas abstrak. Karena BangunDatar memiliki metode abstrak luas() dan keliling(), Lingkaran harus mengimplementasikan metode-metode tersebut.
  Menginisialisasi nilai r (jari-jari) ketika objek Lingkaran dibuat lalu Menetapkan nilai parameter r ke atribut r di dalam kelas, sehingga nilai jari-jari disimpan di objek Lingkaran.
    ```
    // Implement luas method
    @Override
    float luas() {
        return (float) (Math.PI * r * r);
    }

    // Implement keliling method
    @Override
    float keliling() {
        return (float) (2 * Math.PI * r);
    }
    }
    ```
    Rumus untuk luas lingkaran adalah π × r². Dalam Java, kita menggunakan Math.PI untuk nilai π. Rumus untuk keliling lingkaran adalah 2 × π × r. Kita gunakan Math.PI untuk nilai π.

- Class Segitiga
    ```
    class Segitiga extends BangunDatar {
    int alas;  // base
    int tinggi;  // height

    // Constructor
    public Segitiga(int alas, int tinggi) {
        this.alas = alas;
        this.tinggi = tinggi;
    }
    ```
    Kelas Segitiga mewarisi kelas abstrak BangunDatar. Karena BangunDatar memiliki metode abstrak luas() dan keliling(), kelas Segitiga wajib mengimplementasikan metode tersebut.
    Menginisialisasi nilai alas dan tinggi ketika objek Segitiga dibuat. Setelah itu  Menetapkan nilai parameter alas dan tinggi ke atribut kelas sehingga nilai alas dan tinggi tersimpan di dalam objek Segitiga.
    ```
    // Implement luas method
    @Override
    float luas() {
        return 0.5f * alas * tinggi;
    }

    // Implement keliling method (assuming it's an equilateral triangle)
    @Override
    float keliling() {
        return 3 * alas;  // Simplified as an equilateral triangle
    }
    }
    ```
    Rumus untuk luas segitiga adalah ½ × alas × tinggi. Dalam Java, ini dihitung sebagai 0.5f * alas * tinggi, dan hasilnya bertipe float sesuai dengan tipe return dari metode. Karena tidak ada data tambahan mengenai panjang sisi lain, metode ini mengasumsikan bahwa segitiga adalah segitiga sama sisi. Sehingga, kelilingnya adalah 3 * alas

- Class Persegi
  ```
  class Persegi extends BangunDatar {
    int sisi;  // side length

    // Constructor
    public Persegi(int sisi) {
        this.sisi = sisi;
    }
    ```
    Kelas Persegi mewarisi (menurunkan) kelas abstrak BangunDatar. Karena BangunDatar memiliki metode abstrak luas() dan keliling(), Persegi harus mengimplementasikan metode-metode tersebut.
  Constructor yang digunakan untuk menginisialisasi nilai sisi ketika objek Persegi dibuat. Menetapkan nilai parameter sisi ke atribut sisi di dalam kelas sehingga panjang sisi tersimpan di dalam objek Persegi.
    ```
    // Implement luas method
    @Override
    float luas() {
        return sisi * sisi;
    }

    // Implement keliling method
    @Override
    float keliling() {
        return 4 * sisi;
    }
    }
    ```
    Menambahkan rumus untuk luas persegi adalah sisi × sisi. Dalam Java, perhitungan ini dikembalikan sebagai nilai bertipe float. Dan menambahkan rumus untuk keliling persegi adalah 4 × sisi, karena persegi memiliki empat sisi yang sama panjang.

- Class Utama
  ```
  public class Main {
    public static void main(String[] args) {
        // Create objects for Lingkaran, Segitiga, and Persegi
        Lingkaran lingkaran = new Lingkaran(7);
        Segitiga segitiga = new Segitiga(5, 12);
        Persegi persegi = new Persegi(4);

        // Display the area and perimeter of each shape
        System.out.println("Lingkaran:");
        System.out.println("Luas: " + lingkaran.luas());
        System.out.println("Keliling: " + lingkaran.keliling());

        System.out.println("\nSegitiga:");
        System.out.println("Luas: " + segitiga.luas());
        System.out.println("Keliling: " + segitiga.keliling());

        System.out.println("\nPersegi:");
        System.out.println("Luas: " + persegi.luas());
        System.out.println("Keliling: " + persegi.keliling());
    }
    }
    ```
    Program ini menunjukkan cara menggunakan konsep pewarisan dan polimorfisme dalam OOP (Object-Oriented Programming) di Java dengan membuat kelas-kelas turunan dari kelas abstrak BangunDatar. Setiap bentuk (Lingkaran, Segitiga, Persegi) mengimplementasikan metode luas() dan keliling() sesuai dengan rumus spesifik masing-masing bentuk.

# Hasil Output
![Screenshot 2024-10-28 222620](https://github.com/user-attachments/assets/8fd3809e-0988-4d61-bc94-c5994282836a)
