# 💳 Dompet Kampus — Expense Tracker App

<p align="center">
  <img src="https://img.shields.io/badge/React_Native-20232A?style=for-the-badge&logo=react&logoColor=61DAFB"/>
  <img src="https://img.shields.io/badge/Expo-000020?style=for-the-badge&logo=expo&logoColor=white"/>
  <img src="https://img.shields.io/badge/Status-Running-brightgreen?style=for-the-badge"/>
</p>

> **UTS Project — Pemrograman Mobile (React Native)**
> 👤 Nama: **Sharmelita Arini Teresia Sigalingging**

---

## 📜 Deskripsi Proyek

**Dompet Kampus** adalah aplikasi pencatat keuangan pribadi sederhana berbasis **React Native + Expo**. Pengguna dapat mencatat transaksi pemasukan dan pengeluaran, melihat riwayat transaksi, serta memantau saldo secara otomatis dan real-time.

---

## ✅ Fitur yang Diimplementasikan

| No | Fitur | Keterangan | Status |
|----|-------|------------|--------|
| 1 | **Header Saldo** | Saldo berubah otomatis (Pemasukan - Pengeluaran) | ✅ |
| 2 | **Ringkasan** | Total pemasukan & pengeluaran tampil di header | ✅ |
| 3 | **Form Input** | Input deskripsi & nominal transaksi | ✅ |
| 4 | **2 Tombol** | Pemasukan (Hijau) & Pengeluaran (Merah) | ✅ |
| 5 | **FlatList** | Riwayat transaksi + pesan jika kosong | ✅ |
| 6 | **Conditional Styling** | Nominal hijau (masuk) / merah (keluar) | ✅ |
| 7 | **State Management** | `useState` array of objects | ✅ |

---

## 📸 Screenshot Aplikasi Berjalan

### 📱 Tampilan di HP Android (Expo Go)

<p align="center">
  <img src="./screenshots/ss_hp.jpeg" width="320" alt="Dompet Kampus di HP via Expo Go"/>
</p>

<p align="center"><i>Aplikasi berjalan di perangkat Android via Expo Go — Saldo Rp 40.000</i></p>

---

### 💻 Tampilan di Expo Snack (Browser)

<p align="center">
  <img src="./screenshots/uts_praktek.PNG" width="700" alt="Dompet Kampus di Expo Snack"/>
</p>

<p align="center"><i>Aplikasi berjalan di Expo Snack — Saldo Rp 146.000, tanpa error</i></p>

---

## 🧠 Logika Utama

### State Array Transaksi
```js
const [transaksi, setTransaksi] = useState([
  { id: '1', ket: 'Uang Saku', nominal: 100000, tipe: 'masuk' },
  { id: '2', ket: 'Beli Cilok', nominal: 10000, tipe: 'keluar' },
]);
```

### Hitung Saldo dengan `reduce()`
```js
const saldo = transaksi.reduce((total, item) => {
  return item.tipe === 'masuk'
    ? total + item.nominal
    : total - item.nominal;
}, 0);
```

### Conditional Styling (Hijau/Merah)
```js
color: item.tipe === 'masuk' ? '#16a34a' : '#dc2626'
```

### Fungsi Tambah Transaksi
```js
const tambahTransaksi = (tipe) => {
  if (!deskripsi.trim() || !nominal) return;
  setTransaksi([...transaksi, {
    id: Date.now().toString(),
    ket: deskripsi,
    nominal: parseInt(nominal),
    tipe: tipe,
  }]);
  setDeskripsi('');
  setNominal('');
};
```

---

## 🚀 Cara Menjalankan

```bash
# 1. Clone repository
git clone https://github.com/USERNAME/DompetKampus.git
cd DompetKampus

# 2. Install dependencies
npm install

# 3. Jalankan Expo
npx expo start
```

Scan QR code menggunakan aplikasi **Expo Go** di HP Android/iOS.

---

## 📁 Struktur Project

```
DompetKampus/
├── App.js
├── package.json
├── screenshots/
│   ├── ss_hp.jpeg        ← Screenshot HP via Expo Go
│   └── uts_praktek.PNG   ← Screenshot Expo Snack
└── README.md
```

---

## 🛠️ Tech Stack

- **React Native** — Framework UI Mobile
- **Expo** — Development & Build Tool
- **useState Hook** — State Management
- **FlatList** — Optimized List Rendering

---

<p align="center">
  Made with ❤️ by <b>Sharmelita Arini Teresia Sigalingging</b><br/>
  UTS Pemrograman Mobile — 2026
</p>
