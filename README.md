Michelle Dorani Shiba - 2341720113

#Tugas Praktikum 1
1. Jelaskan maksud dari langkah 4 pada praktikum tersebut! Mengapa dilakukan demikian?
> Langkah 4 ini bertujuan untuk menyederhanakan proses impor file model dalam proyek Flutter. Dengan membuat file data_layer.dart yang berisi perintah export 'plan.dart'; dan export 'task.dart';, kita dapat mengimpor kedua model tersebut hanya dengan satu baris import '../models/data_layer.dart'; di file lain. Cara ini membuat kode lebih rapi, mudah dipelihara, dan efisien — terutama saat jumlah file model bertambah. Jadi, data_layer.dart berfungsi sebagai gateway (pintu masuk) untuk semua model yang ada di folder models.
2. Mengapa perlu variabel plan di langkah 6 pada praktikum tersebut? Mengapa dibuat konstanta ?
> Langkah 6 bertujuan untuk membuat tampilan utama aplikasi menggunakan StatefulWidget agar data dapat berubah secara dinamis. File plan_screen.dart menampilkan daftar tugas dan tombol tambah tugas. Variabel plan menyimpan data sementara daftar rencana, sedangkan AppBar berisi judul “Master Plan Namaku” yang diganti dengan nama panggilan pengguna.
3. Lakukan capture hasil dari Langkah 9 berupa GIF, kemudian jelaskan apa yang telah Anda buat!
>
4. Apa kegunaan method pada Langkah 11 dan 13 dalam lifecyle state ?
> Langkah 11–13 bertujuan untuk mengatur perilaku scroll dan keyboard agar pengalaman pengguna lebih baik. Pada initState(), dibuat ScrollController dengan listener untuk menutup keyboard saat pengguna melakukan scroll. Di langkah 12, controller dan pengaturan keyboardDismissBehavior ditambahkan agar keyboard otomatis tersembunyi saat layar digulir, terutama di iOS. Terakhir, pada dispose(), controller dibersihkan ketika widget tidak digunakan lagi untuk mencegah kebocoran memori.

#Tugas Praktikum 2
1. Jelaskan mana yang dimaksud InheritedWidget pada langkah 1 tersebut! Mengapa yang digunakan InheritedNotifier?
> Pada langkah 1, InheritedWidget adalah widget khusus di Flutter yang memungkinkan data dibagikan ke seluruh widget tree tanpa perlu meneruskannya secara manual melalui konstruktor. Dalam kasus ini, PlanProvider dibuat sebagai InheritedNotifier karena tidak hanya menyimpan data, tetapi juga memantau perubahan pada data tersebut menggunakan ValueNotifier. Jadi, ketika nilai Plan berubah, semua widget yang bergantung padanya akan otomatis diperbarui. Dengan kata lain, InheritedNotifier digunakan agar data dan perubahan state dapat disebarkan secara efisien ke seluruh aplikasi.
2. Jelaskan maksud dari method di langkah 3 pada praktikum tersebut! Mengapa dilakukan demikian?
> Dua method pada langkah 3 (completedCount dan completenessMessage) berfungsi untuk menghitung dan menampilkan progres penyelesaian tugas dalam sebuah plan. completedCount menghitung jumlah tugas yang telah selesai, sedangkan completenessMessage menampilkan informasi dalam format teks seperti “2 out of 5 tasks”. Hal ini dilakukan untuk memudahkan pengguna melihat sejauh mana rencana telah diselesaikan tanpa harus menghitung secara manual.
3. Lakukan capture hasil dari Langkah 9 berupa GIF, kemudian jelaskan apa yang telah Anda buat!
> 
> Pada langkah 9, aplikasi menampilkan daftar tugas beserta indikator progres di bagian bawah layar. Setiap kali pengguna menandai tugas sebagai selesai, pesan progres akan otomatis diperbarui berkat penggunaan ValueListenableBuilder dan PlanProvider, yang mengelola state data secara reaktif.

#Tugas Praktikum 3
1. Berdasarkan Praktikum 3 yang telah Anda lakukan, jelaskan maksud dari gambar diagram berikut ini!
> Diagram tersebut menjelaskan alur perpindahan data dan tampilan antar layar (screen) pada Praktikum 3: State di Multiple Screens menggunakan konsep Navigator Push di Flutter.
> Pada bagian kiri, tampak struktur awal aplikasi dengan MaterialApp sebagai akar, diikuti PlanProvider yang menyediakan data Plan ke seluruh widget, lalu PlanCreatorScreen yang berfungsi untuk membuat rencana baru. Di dalamnya terdapat Column yang menampung TextField untuk input nama rencana dan ListView untuk menampilkan daftar tugas.
> Ketika pengguna menekan tombol untuk melanjutkan, terjadi proses Navigator.push, yaitu perpindahan ke layar baru (PlanScreen) di sebelah kanan diagram. Di layar ini, data dari PlanProvider tetap terbawa (state tetap terjaga), dan Scaffold digunakan sebagai struktur utama tampilan. Widget seperti Expanded, SafeArea, ListView, dan Text digunakan untuk menampilkan daftar tugas dan progres rencana secara lebih rapi.
> Singkatnya, diagram ini menggambarkan bagaimana state dan data Plan dipertahankan serta digunakan di dua layar berbeda — dari proses pembuatan rencana (input) hingga tampilan hasilnya — dengan bantuan Provider dan Navigator.
2. Lakukan capture hasil dari Langkah 14 berupa GIF, kemudian jelaskan apa yang telah Anda buat!
> 
> Pada tahap ini, aplikasi menunjukkan transisi dari layar pembuat rencana (PlanCreatorScreen) ke layar tampilan rencana (PlanScreen). Pengguna dapat memasukkan nama rencana, lalu setelah menekan tombol, layar berganti menampilkan daftar tugas kosong dengan judul sesuai rencana yang dibuat.
