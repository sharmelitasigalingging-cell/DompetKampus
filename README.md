# 💳 DompetKampus — Expense Tracker App

> **UTS Project | Pemrograman Mobile (React Native)**
> Nama: **Sharmelita Arini Teresia Sigalingging**

---

## 📜 Deskripsi Proyek

**DompetKampus** adalah aplikasi pencatat keuangan pribadi sederhana yang dibangun menggunakan **React Native + Expo**. Aplikasi ini memungkinkan pengguna mencatat transaksi pemasukan dan pengeluaran harian, menampilkan riwayat transaksi, serta menghitung saldo secara otomatis dan real-time.

---

## ✅ Fitur yang Diimplementasikan

| No | Fitur | Status |
|----|-------|--------|
| 1 | **Header Saldo** — Saldo otomatis berubah saat transaksi ditambahkan | ✅ |
| 2 | **Form Input** — Input deskripsi & nominal transaksi | ✅ |
| 3 | **2 Tombol** — "Pemasukan" (Hijau) & "Pengeluaran" (Merah) | ✅ |
| 4 | **FlatList** — Riwayat transaksi dengan pesan empty state | ✅ |
| 5 | **Conditional Styling** — Nominal hijau (masuk) / merah (keluar) | ✅ |
| 6 | **State Management** — `useState` array of objects | ✅ |

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

### Conditional Styling
```js
color: item.tipe === 'masuk' ? '#16a34a' : '#dc2626'
```

### Tambah Transaksi
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

## 📸 Screenshot Aplikasi Berjalan

### Tampilan di HP Android via Expo Go

<p align="center">
  <img src="./https://github.com/sharmelitasigalingging-cell/DompetKampus/blob/main/ss%20hp.jpeg://github.com/user-attachments/assets/ec1ad393-1a2a-43ea-8b90-f288be87903e" />
" width="300" alt="DompetKampus di Expo Go"/>
</p>

### Tampilan di Expo Snack (Browser)

<p align="center">
  <img src="./screenshots/expo_snack.PNG" width="700" alt="DompetKampus di Expo Snack"/>
</p>

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

## 🛠️ Tech Stack

- **React Native** — Framework UI
- **Expo** — Development environment & build tool
- **useState Hook** — State management
- **FlatList** — Optimized list rendering

---

## 📁 Struktur Project

```
DompetKampus/
├── App.js          ← Kode utama aplikasi
├── package.json
├── screenshots/
│   ├── hp_screenshot.jpeg
│   └── expo_snack.PNG
└── README.md
```

---

<p align="center">
  Made with ❤️ by <b>Sharmelita Arini Teresia Sigalingging</b>
</p>
