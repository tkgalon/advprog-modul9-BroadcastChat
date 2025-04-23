# advprog-modul9-BroadcastChat

Nama: Muhammad Zaid Ats Tsabit <br>
NPM: 2306224410 <br>
Kelas: Advprog-B
<hr>

## Experiment 2.1: Original code, and how it run
![experiment 2.1 commit1](/media/commit1.jpeg)
Pada tahap ini, saya menjalankan satu server dan tiga client untuk chat berbasis WebSocket. Server dijalankan di port 2000, dan masing-masing client berhasil terhubung dan mengirimkan pesan. Ketika satu client mengirim pesan, pesan tersebut berhasil dikirim ke seluruh client lainnya, menandakan bahwa broadcast udah berjalan dengan baik. Disini proses komunikasinya bersifat asynchronous sehingga semua client dapat mengirim dan menerima pesan secara real-time tanpa blocking. Eksperimen ini menunjukkan bahwa dengan menggunakan tokio_websockets dan channel broadcast dari tokio, kita dapat dengan mudah membuat aplikasi chat sederhana yang bersifat real-time.



