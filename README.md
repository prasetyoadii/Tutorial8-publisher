# Tutorial 8 Publisher
Nama  : Prasetyo Adi Wijonarko
Kelas : A
NPM   : 2206830246

## Refleksi
1. How many data your publisher program will send to the message broker in one run? <br>
Program publisher akan mengirim lima pesan ke message broker dalam satu jalannya. Setiap pesan dikirim melalui pemanggilan fungsi publish_event yang berbeda-beda, masing-masing membawa informasi user_id dan user_name yang berbeda. Pesan-pesan ini merupakan UserCreatedEventMessage yang berisi detail tentang pembuatan pengguna, Isi dari pesan tersebut adalah user_id dan user_name yang berbeda di tiap fungsi call nya, yakni sebagai berikut. <br>
user_id: "1", user_name: "2206827945-Amir" <br>
user_id: "2", user_name: "2206827945-Budi" <br>
user_id: "3", user_name: "2206827945-Cica" <br>
user_id: "4", user_name: "2206827945-Dira" <br>
user_id: "5", user_name: "2206827945-Emir" <br>
Data ini penting untuk diproses dan disampaikan oleh sistem pengirim pesan ke sistem yang mungkin akan mengonsumsinya.
2. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean? <br>
URL "amqp://guest:guest@localhost:5672" digunakan dalam kedua program subscriber dan publisher untuk terhubung ke server AMQP yang sama. Ini menunjukkan bahwa keduanya saling terkoneksi dengan menggunakan informasi akun yang identik, dengan nama pengguna "guest" dan sandi "guest", pada server AMQP yang aktif di localhost menggunakan port 5672. URL tersebut berperan sebagai alamat dari message broker yang digunakan oleh kedua program. Subscriber dan publisher diatur dengan URL yang sama agar dapat berkomunikasi melalui message broker yang sama, dalam hal ini RabbitMQ. Ketika publisher mengirim pesan ke antrian (queue) di RabbitMQ, subscriber akan memasang listener untuk menerima dan memproses pesan dari antrian tersebut. Koneksi yang konsisten ke message broker yang sama memastikan bahwa komunikasi antara subscriber dan publisher berjalan dengan lancar dan efisien.
3. Running RabbitMQ as message broker.
   ![alt text](/image/RunningRabbitMQasmessagebroker.jpg)
4. Sending and Process Event
   ![alt text](/image/sendingandprocessevent1.jpg)
   ![alt text](/image/sendingandprocessevent2.jpg)
   Setelah menjalankan perintah cargo run pada program subscriber dan publisher, data yang dihasilkan oleh publisher akan dikirim ke dalam message queue. Selanjutnya, subscriber akan menerima data dari message queue tersebut dan menampilkannya pada console atau terminal sebagai bukti bahwa proses komunikasi antara publisher dan subscriber melalui message broker telah berhasil. 