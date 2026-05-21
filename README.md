
# Generator SPPD

Aplikasi web untuk membuat Surat Perintah Perjalanan Dinas (SPPD) otomatis dalam format PDF.

## Fitur

✅ **Form Input Interaktif** - Form yang user-friendly untuk mengisi data SPPD  
✅ **Field Merah Otomatis** - Field tertentu ditampilkan dengan warna merah di PDF sesuai format resmi  
✅ **Preview PDF** - Lihat preview sebelum download  
✅ **Download PDF** - Export langsung ke file PDF  
✅ **Template Profesional** - Format sesuai dengan template SPPD SD Negeri 1 Kucur  
✅ **Responsive Design** - Bisa diakses dari mobile dan desktop  

## Tech Stack

- **Backend**: Node.js + Express
- **PDF Generation**: PDFKit
- **Frontend**: HTML5 + CSS3 + Vanilla JavaScript

## Instalasi

### Requirements
- Node.js v14+ 
- npm atau yarn

### Langkah-langkah

1. **Clone repository**
```bash
git clone https://github.com/tarbiyahumm/surat.git
cd surat
```

2. **Install dependencies**
```bash
npm install
```

3. **Jalankan server**
```bash
npm start
```
Atau untuk development dengan auto-reload:
```bash
npm run dev
```

4. **Akses aplikasi**
```
http://localhost:3000
```

## Struktur File

```
📁 surat/
├── 📁 src/
│   └── pdfGenerator.js        # Generator PDF dengan pdfkit
├── 📁 public/
│   ├── index.html             # Halaman utama
│   ├── styles.css             # Styling
│   └── script.js              # JavaScript frontend
├── server.js                  # Express server
├── package.json               # Dependencies
└── README.md                  # Dokumentasi
```

## API Endpoints

### POST `/api/generate-sppd`
Generate dan download PDF SPPD

**Request Body:**
```json
{
  "noSurat": "800/01.35.07.101.433.010/20256",
  "pejabatPemberiPerintah": "Kepala Sekolah",
  "namaPegawai": "John Doe",
  "nip": "1234567890123456",
  "pangkat": "Guru",
  "jabatan": "Guru Kelas",
  "maksudPerjalanan": "Mengikuti Pelatihan",
  "alatAngkut": "Kendaraan Dinas",
  "tempatBerangkat": "SD Negeri 1 Kucur",
  "tujuan": "Kota Surabaya",
  "lamaPerjalanan": "5 hari",
  "tglBerangkat": "24 Juli 2025",
  "tglKembali": "28 Juli 2025",
  "namaPengikut": "-",
  "pembiayaan": "Dana BOS Kinerja 2026",
  "keterangan": "-",
  "kotaPenerbit": "Malang",
  "tglPenerbit": "4 Juli 2026",
  "pejabatTtd": "Kepala Sekolah",
  "namaPejabatTtd": "HIKMATULLAH, M.Pd I",
  "nipPejabatTtd": "1985031620100101011"
}
```

**Response:** PDF file

### POST `/api/preview-sppd`
Preview PDF di browser

**Request Body:** Sama seperti `/api/generate-sppd`

**Response:** PDF inline untuk preview

## Field yang Ditampilkan Merah di PDF

Sesuai template resmi, field berikut akan ditampilkan dengan warna merah:
- Nama Pegawai (Nomor 2)
- Pangkat (Nomor 3.a)
- Jabatan (Nomor 3.b)
- Maksud Perjalanan Dinas (Nomor 4)
- Alat Angkut (Nomor 5)
- Tempat Berangkat (Nomor 6.a)
- Tujuan (Nomor 6.b)
- Lamanya Perjalanan Dinas (Nomor 7.a)
- Tanggal Berangkat (Nomor 7.b)
- Tanggal Harus Kembali (Nomor 7.c)
- Pembiayaan Anggaran (Nomor 9)

## Cara Penggunaan

1. **Buka aplikasi** di `http://localhost:3000`
2. **Isi formulir** dengan data SPPD yang diperlukan
3. **Preview** (opsional) untuk melihat hasil sebelum download
4. **Download** untuk mendapatkan file PDF

## Validasi

Aplikasi akan memvalidasi bahwa semua field yang wajib diisi sudah terisi sebelum generate PDF.

## Customization

### Mengubah Header/Footer
Edit file `src/pdfGenerator.js` di fungsi `drawHeader()` untuk mengubah informasi sekolah.

### Mengubah Styling PDF
Modifikasi `src/pdfGenerator.js` untuk mengubah font, ukuran, warna, dan layout.

### Mengubah Styling Form
Edit `public/styles.css` untuk mengubah tampilan form.

## Troubleshooting

### PDF tidak ter-generate
- Pastikan semua field wajib sudah terisi
- Cek console browser untuk error message
- Restart server

### Aplikasi tidak bisa diakses
- Pastikan port 3000 tidak digunakan aplikasi lain
- Ubah port di `server.js` atau set environment variable `PORT`

## Lisensi

MIT

## Support

Untuk pertanyaan atau issue, hubungi admin repository.

---

**Made with ❤️ for SD Negeri 1 Kucur**
