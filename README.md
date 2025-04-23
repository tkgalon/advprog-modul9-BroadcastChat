# advprog-modul9-BroadcastChat

Nama: Muhammad Zaid Ats Tsabit <br>
NPM: 2306224410 <br>
Kelas: Advprog-B
<hr>

## Experiment 2.1: Original code, and how it run
![experiment 2.1 commit1](/media/commit1.jpeg)
Pada tahap ini, saya menjalankan satu server dan tiga client untuk chat berbasis WebSocket. Server dijalankan di port 2000, dan masing-masing client berhasil terhubung dan mengirimkan pesan. Ketika satu client mengirim pesan, pesan tersebut berhasil dikirim ke seluruh client lainnya, menandakan bahwa broadcast udah berjalan dengan baik. Disini proses komunikasinya bersifat asynchronous sehingga semua client dapat mengirim dan menerima pesan secara real-time tanpa blocking. Eksperimen ini menunjukkan bahwa dengan menggunakan tokio_websockets dan channel broadcast dari tokio, kita dapat dengan mudah membuat aplikasi chat sederhana yang bersifat real-time.

## Experiment 2.2: Modifying port
![experiment 2.2 commit2](/media/commit2.jpeg)
Sekarang kita mencoba mengubah port, port yang digunakan untuk koneksi WebSocket diubah dari 2000 menjadi 8080 pada kedua sisi, yaitu server dan client. Perubahan dilakukan pada bagian TcpListener::bind di server dan URI ClientBuilder::from_uri di client. Setelah port diubah, program masih dapat berjalan dengan baik dan komunikasi antar client tetap berlangsung secara real-time. Hal ini menunjukkan bahwa port hanyalah endpoint komunikasi, selama kedua pihak terhubung ke alamat dan protokol yang sama, koneksi tetap berhasil. WebSocket tetap digunakan sebagai protokolnya dan tidak ada perubahan pada mekanisme pengiriman pesan karena semua logika komunikasi tetap berada dalam layer aplikasi.

## Experiment 2.3: Small changes, add IP and Port
![experiment 2.3 commit3](/media/commit3.jpeg)
Pada eksperimen ini, saya menambahkan informasi alamat IP dan port pengirim pada setiap pesan yang diterima oleh client. Perubahan ini dilakukan di sisi server, yaitu dengan memodifikasi bcast_tx.send(...) agar menyisipkan data addr, yang merepresentasikan alamat dan port client pengirim pesan. Dengan begitu, setiap client yang menerima pesan dapat mengetahui asal pesan tersebut meskipun belum ada identitas atau username yang diimplementasikan. Di sisi client, tampilan output juga diperjelas dengan prefix "Zaid's Computer - From server:" untuk membedakan dengan input sendiri. Eksperimen ini membantu kita dalam memahami bagaimana informasi tambahan seperti alamat socket bisa digunakan untuk menambahkan konteks ke dalam komunikasi sederhana.

