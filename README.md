Berikut adalah contoh project Java sederhana yang dapat Anda gunakan sebagai awal:

Project: Aplikasi Pengelolaan Buku
Aplikasi ini memungkinkan pengguna untuk menambahkan, menghapus, dan menampilkan buku.

Kode:
*Buku.java*
```
public class Buku {
    private String judul;
    private String penulis;
    private int tahun;

    public Buku(String judul, String penulis, int tahun) {
        this.judul = judul;
        this.penulis = penulis;
        this.tahun = tahun;
    }

    public String getJudul() {
        return judul;
    }

    public String getPenulis() {
        return penulis;
    }

    public int getTahun() {
        return tahun;
    }
}
```

*BukuManager.java*
```
import java.util.ArrayList;
import java.util.List;

public class BukuManager {
    private List<Buku> bukuList;

    public BukuManager() {
        this.bukuList = new ArrayList<>();
    }

    public void tambahBuku(Buku buku) {
        bukuList.add(buku);
    }

    public void hapusBuku(String judul) {
        bukuList.removeIf(buku -> buku.getJudul().equals(judul));
    }

    public void tampilkanBuku() {
        for (Buku buku : bukuList) {
            System.out.println("Judul: " + buku.getJudul());
            System.out.println("Penulis: " + buku.getPenulis());
            System.out.println("Tahun: " + buku.getTahun());
            System.out.println();
        }
    }
}
```

*Main.java*
```
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        BukuManager bukuManager = new BukuManager();
        Scanner scanner = new Scanner(System.in);

        while (true) {
            System.out.println("1. Tambah Buku");
            System.out.println("2. Hapus Buku");
            System.out.println("3. Tampilkan Buku");
            System.out.println("4. Keluar");

            System.out.print("Pilih menu: ");
            int pilihan = scanner.nextInt();
            scanner.nextLine();

            switch (pilihan) {
                case 1:
                    System.out.print("Judul: ");
                    String judul = scanner.nextLine();
                    System.out.print("Penulis: ");
                    String penulis = scanner.nextLine();
                    System.out.print("Tahun: ");
                    int tahun = scanner.nextInt();
                    scanner.nextLine();

                    Buku buku = new Buku(judul, penulis, tahun);
                    bukuManager.tambahBuku(buku);
                    break;
                case 2:
                    System.out.print("Judul buku yang ingin dihapus: ");
                    String judulHapus = scanner.nextLine();
                    bukuManager.hapusBuku(judulHapus);
                    break;
                case 3:
                    bukuManager.tampilkanBuku();
                    break;
                case 4:
                    System.exit(0);
                    break;
                default:
                    System.out.println("Pilihan tidak valid");
            }
        }
    }
}
```

Cara Menjalankan:
1. Buat project Java baru di IDE Anda.
2. Buat kelas `Buku`, `BukuManager`, dan `Main`.
3. Salin kode di atas ke kelas yang sesuai.
4. Jalankan kelas `Main`.
5. Ikuti menu yang ditampilkan untuk menambahkan, menghapus, atau menampilkan buku.

Semoga project ini membantu Anda memahami dasar-dasar pemrograman Java!
