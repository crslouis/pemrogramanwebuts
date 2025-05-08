# 💬 Aplikasi Chat Real-Time dengan WebSocket

Aplikasi ini adalah **Chat App sederhana berbasis web** yang dibangun menggunakan teknologi **WebSocket** untuk mendukung komunikasi real-time antara client dan server. Proyek ini cocok sebagai dasar pemahaman protokol WebSocket dalam aplikasi nyata seperti chat, dashboard monitoring, dan lainnya.

---

## 👨‍🎓 Identitas

| Nama                  | NIM       | Kelas     |
| --------------------- | --------- | --------- |
| Carlos Louis Fernando | 312310458 | TI.23.A.5 |

---

## 📖 Penjelasan Proyek

Aplikasi chat ini memungkinkan dua atau lebih pengguna untuk bertukar pesan secara real-time melalui browser.

### Fitur:

* UI bergaya dark mode yang modern.
* Indikator status **Online**.
* Pesan pengguna ditampilkan secara langsung saat dikirim.
* Kolom input dan tombol kirim yang interaktif.

Contoh tampilan:

**Screenshot 1**:
![Screenshot 2025-04-29 133204](https://github.com/user-attachments/assets/8bbca1cd-c5bb-47e9-8bf0-b8a2ddab000b)


**Screenshot 2**:
![Screenshot 2025-04-29 133213](https://github.com/user-attachments/assets/6ecb9603-52ef-4ec2-b1a1-9f502811dcf8)

**Screenshot 3**:
![Screenshot 2025-04-29 133322](https://github.com/user-attachments/assets/8f1231fa-9ecd-4549-a39c-4afd8c2678e6)
Berikut adalah tampilan akhir dari aplikasi Chat App real-time yang dibangun menggunakan WebSocket:


Gambar di atas menunjukkan dua jendela browser yang sedang aktif berkomunikasi secara real-time melalui WebSocket. Penjelasan elemen:

🔹 Pesan Masuk dan Keluar: Pesan dari pengguna sendiri muncul dengan gaya bubble biru terang di sisi kanan, sedangkan pesan dari pengguna lain ditampilkan dengan bubble ungu di sisi kiri.

🟢 Indikator Status: Menampilkan status Online di kanan atas setiap jendela chat.

💬 Real-Time Interaction: Setiap pesan langsung muncul secara instan di kedua jendela tanpa perlu refresh atau reload.

---

## 🔌 Memahami WebSocket

WebSocket adalah protokol komunikasi yang menyediakan saluran komunikasi dua arah yang persisten antara client dan server. Tidak seperti HTTP yang bersifat stateless, WebSocket memungkinkan komunikasi real-time tanpa perlu membangun koneksi berulang.

📖 Artikel lengkap:
[Memahami WebSocket di Medium](https://medium.com/@carloslouis9999/memahami-websocket-protokol-komunikasi-real-time-yang-efisien-5163ec4b9485)

### Ringkasan Artikel:

* Apa itu WebSocket?
* Perbedaannya dengan HTTP
* Proses handshake
* Kelebihan WebSocket
* Contoh penggunaannya (seperti chat)

---

## 📦 Teknologi yang Digunakan

* HTML, CSS, JavaScript
* Node.js
* WebSocket API
* `ws` library (Node.js)
* Socket.IO *(jika digunakan untuk real-time communication abstraction)*

---

## 🧾 Bukti Orisinalitas

Artikel dicek menggunakan Turnitin:

* ✅ **Tingkat Kemiripan**: **5%** (sangat rendah)
* 📝 **Judul File**: `Pemrograman web.pdf`
* 📅 **Tanggal Upload**: 29 April 2025
* 📸 **Screenshot Bukti**:
  ![Screenshot Turnitin](https://github.com/user-attachments/assets/3c95d033-08b3-4276-b08f-449a3cbc0365)

---

## 🚀 Contoh Kode WebSocket

### Client (JavaScript)

```javascript
const socket = new WebSocket('ws://localhost:8080');

socket.onopen = () => {
  console.log('Terhubung ke server!');
  socket.send('Hello Server!');
};

socket.onmessage = (event) => {
  console.log('Dari server:', event.data);
};

function kirimPesan(pesan) {
  socket.send(pesan);
}
```

### Server (Node.js dengan `ws`)

```javascript
const WebSocket = require('ws');
const wss = new WebSocket.Server({ port: 8080 });

wss.on('connection', ws => {
  console.log('Client terhubung');

  ws.on('message', message => {
    console.log('Pesan dari client:', message);

    // Broadcast ke semua client
    wss.clients.forEach(client => {
      if (client.readyState === WebSocket.OPEN) {
        client.send(message);
      }
    });
  });

  ws.send('Selamat datang di chat!');
});
```

---

🛠️ *Silakan modifikasi dan kembangkan aplikasi ini sesuai kebutuhan pembelajaran Anda.*
