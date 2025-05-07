# Memahami WebSocket: Protokol Komunikasi Real-Time yang Efisien

Artikel ini membahas tentang **WebSocket**, sebuah protokol komunikasi yang memungkinkan interaksi real-time antara client dan server. Cocok untuk aplikasi seperti chat, dashboard monitoring, notifikasi, dan lainnya.

📖 Baca artikelnya di Medium:  
[Memahami WebSocket](https://medium.com/@carloslouis9999/memahami-websocket-protokol-komunikasi-real-time-yang-efisien-5163ec4b9485)

---

# 👨‍🎓 Identitas

| Nama                  | NIM        | Kelas     |
|-----------------------|------------|-----------|
| Carlos Louis Fernando | 312310458  | TI.23.A.5 |


## 🔍 Ringkasan Artikel

- **Apa itu WebSocket?**
- **Perbedaan dengan HTTP**
- **Proses Handshake**
- **Kelebihan WebSocket**
- **Contoh Penggunaan**

## 📊 Bukti Orisinalitas

Artikel ini telah dicek menggunakan Turnitin dengan hasil sebagai berikut:

- ✅ **Tingkat Kemiripan**: **5%** (sangat rendah)
- 📝 **Judul File**: `Pemrograman web.pdf`  
- 📅 **Tanggal Upload**: 29 April 2025  
- 📈 **Screenshot**:  
![Screenshot 2025-05-07 214124](https://github.com/user-attachments/assets/3c95d033-08b3-4276-b08f-449a3cbc0365)



## 📦 Teknologi Terkait

- JavaScript WebSocket API
- Node.js + ws
- Socket.IO

## 🚀 Contoh Kode

**Client (JavaScript)**

```javascript
const socket = new WebSocket('ws://localhost:8080');

socket.onopen = () => {
  socket.send('Hello Server!');
};

socket.onmessage = (event) => {
  console.log('Dari server:', event.data);
};
