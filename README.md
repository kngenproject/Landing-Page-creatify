# 🎯 Creatify - Landing Page & Authentication System

Aplikasi web **Creatify** adalah platform untuk membuat dan mengelola undangan digital. Project ini telah diperbaiki dan disempurnakan agar semua fungsi berfungsi dengan baik sesuai konteks.

## ✨ Fitur Utama

### 1. **Landing Page (index.html)**
- Login dengan email & password menggunakan Firebase Authentication
- Validasi form yang komprehensif
- Error handling yang user-friendly
- Redirect otomatis ke dashboard setelah login berhasil
- Navigasi ke halaman register, lupa password, dan generator undangan
- Responsive design untuk mobile & desktop

**Fitur Login:**
- ✅ Validasi email & password
- ✅ Menampilkan error message yang jelas
- ✅ Spinner loading indicator
- ✅ Enter key untuk submit
- ✅ Auto-focus pada input email
- ✅ Proteksi password dengan tipe `password` input

### 2. **Register (register.html)**
- Form pendaftaran akun baru
- Validasi nama, email, dan password
- Password strength indicator dengan 3 level
- Konfirmasi password yang cocok
- Update profile dengan nama lengkap
- Redirect ke login setelah berhasil

**Fitur Registrasi:**
- ✅ Validasi nama minimal 3 karakter
- ✅ Validasi email format
- ✅ Password strength visual feedback
- ✅ Pengecekan duplikasi email
- ✅ Auto-logout setelah registrasi untuk keamanan

### 3. **Forgot Password (forgot-password.html)**
- Input email untuk reset password
- Mengirim link reset ke email terdaftar
- Validasi email format
- Error handling untuk email yang tidak ditemukan
- Info box yang menjelaskan proses reset

**Fitur Reset Password:**
- ✅ Validasi email
- ✅ Firebase sendPasswordResetEmail
- ✅ Pesan informasi tentang email reset
- ✅ Auto-redirect ke login setelah sukses

### 4. **Generator Undangan (generator.html)**
- Form untuk membuat undangan digital baru
- Preview undangan sebelum disimpan
- Pilihan tema warna
- Simpan data ke localStorage
- Akses tanpa login (gratis & mudah)

**Fitur Generator:**
- ✅ Form dengan validasi
- ✅ Live preview
- ✅ Edit & simpan ke localStorage
- ✅ Minimal date validation (tidak boleh tanggal lampau)
- ✅ Responsive grid layout

### 5. **Dashboard (dashboard.html)**
- Menampilkan daftar undangan yang sudah dibuat
- Edit, bagikan, dan hapus undangan
- User info & logout button
- Empty state jika belum ada undangan
- Loading state saat fetch data

**Fitur Dashboard:**
- ✅ Auth check (redirect jika belum login)
- ✅ Display user name
- ✅ CRUD operations (Create, Read, Update, Delete)
- ✅ Konfirmasi sebelum delete
- ✅ Responsive card grid

---

## 🔧 Technical Stack

- **Frontend:** HTML5, CSS3, JavaScript (ES6+)
- **Authentication:** Firebase Authentication
- **Storage:** localStorage untuk undangan
- **UI Framework:** Custom CSS (responsive)
- **Fonts:** Google Fonts (Cormorant Garamond, Nunito)
- **Icons:** Unicode Emojis

---

## 📁 File Structure

```
/outputs/
├── index.html              # Login landing page
├── register.html           # Pendaftaran akun
├── forgot-password.html    # Reset password
├── generator.html          # Pembuat undangan
├── dashboard.html          # Dashboard user
└── README.md              # Dokumentasi ini
```

---

## 🚀 Cara Menggunakan

### **1. Setup Awal**
1. Copy semua file HTML ke server/host Anda
2. Pastikan Firebase sudah dikonfigurasi dengan benar (sudah ada di code)
3. Akses `index.html` sebagai entry point

### **2. Login Flow**
```
index.html (Login)
    ↓
Dashboard → Create/Manage Undangan
    ↓
Logout → kembali ke index.html
```

### **3. Register Flow**
```
index.html (Klik "Daftar akun baru")
    ↓
register.html (Form pendaftaran)
    ↓
Verifikasi email & password
    ↓
Auto-redirect ke index.html (login)
```

### **4. Forgot Password Flow**
```
index.html (Klik "Lupa password?")
    ↓
forgot-password.html (Input email)
    ↓
Firebase kirim reset link ke email
    ↓
User cek email & reset password
    ↓
Auto-redirect ke index.html (login dengan password baru)
```

### **5. Generator (Tanpa Login)**
```
index.html (Klik "Buat Undangan Sekarang")
    ↓
generator.html (Isi form undangan)
    ↓
Preview undangan
    ↓
Simpan ke localStorage
    ↓
Klik "Lanjutkan ke Login" → redirect ke login
    ↓
Setelah login → Dashboard menampilkan undangan
```

---

## 🔐 Security Features

✅ **Password Security**
- Password hidden di input
- Minimum 6 karakter requirement
- Password strength indicator
- Confirmation matching

✅ **Email Validation**
- Format validation dengan regex
- Duplicate email checking via Firebase
- Email verification (Firebase built-in)

✅ **Authentication**
- Firebase Authentication
- Auto-logout on invalid session
- Redirect protection (non-logged users)

✅ **Data Protection**
- localStorage untuk undangan saja
- Tidak menyimpan password
- Tidak ada hardcoded sensitive data (kecuali Firebase config yang sudah public)

---

## 🎨 Design Features

### **Color Palette**
```
Primary: #b89a6a (Warm Gold)
Secondary: #d4b896 (Light Brown)
Background: #f5f0e8 (Cream)
Text: #2c2118 (Dark Brown)
Accent: Error (#c95a5a), Success (#15803d)
```

### **Typography**
- **Heading:** Cormorant Garamond (serif)
- **Body:** Nunito (sans-serif)

### **Animation**
- Fade-up entrance animations
- Smooth transitions
- Spinner loading indicator

### **Responsive Design**
- Mobile-first approach
- Breakpoint: 768px & 480px
- Grid layout yang adaptif
- Optimal padding/margin untuk setiap ukuran

---

## 🔗 Navigation Map

```
┌─────────────────────────────────────────┐
│        CREATIFY PLATFORM FLOW           │
├─────────────────────────────────────────┤
│                                         │
│  Landing (index.html)                   │
│  ├─ [Masuk ke Dashboard]                │
│  ├─ [Daftar akun baru] → register.html │
│  ├─ [Lupa password?] → forgot-pwd.html │
│  └─ [Buat Undangan] → generator.html   │
│                                         │
│  Register (register.html)               │
│  └─ Kembali ke login                    │
│                                         │
│  Forgot Password (forgot-pwd.html)      │
│  └─ Kembali ke login                    │
│                                         │
│  Generator (generator.html)             │
│  ├─ Buat form undangan                  │
│  ├─ Preview                             │
│  └─ Lanjutkan ke Login                  │
│                                         │
│  Dashboard (dashboard.html)             │
│  ├─ Tampilkan undangan                  │
│  ├─ [Edit] [Share] [Delete]             │
│  ├─ [Buat Undangan Baru]                │
│  └─ [Logout] → kembali ke Login         │
│                                         │
└─────────────────────────────────────────┘
```

---

## 📱 Responsiveness Checklist

✅ Mobile (< 480px)
- ✅ Stack button vertically
- ✅ Full-width inputs
- ✅ Smaller padding
- ✅ Readable font sizes

✅ Tablet (480px - 768px)
- ✅ 2-column grid
- ✅ Optimized spacing
- ✅ Touch-friendly buttons

✅ Desktop (> 768px)
- ✅ 3+ column grid
- ✅ Full layout optimization
- ✅ Hover states

---

## 🐛 Troubleshooting

### **"Firebase not initialized" error**
→ Pastikan semua file HTML menggunakan Firebase config yang sama

### **Email tidak diterima**
→ Check folder spam, dan pastikan email address valid

### **Data undangan tidak tersimpan**
→ Pastikan localStorage enabled di browser

### **Login gagal terus**
→ Cek apakah email sudah terdaftar dan password benar

### **404 Page**
→ Tambahkan `public/404.html` untuk custom error page

---

## 📊 Firebase Configuration

```javascript
const firebaseConfig = {
  apiKey:            "AIzaSyDSiWxxT-qgM_tStgaw7D8AuNaDgI3mkcY",
  authDomain:        "creatify.my.id",
  projectId:         "landing-page-creatify",
  storageBucket:     "landing-page-creatify.firebasestorage.app",
  messagingSenderId: "142614580975",
  appId:             "1:142614580975:web:368ba820dbfc5f69ca151a"
};
```

⚠️ **Catatan:** Config ini sudah public karena Firebase rules keamanan, tapi tetap gunakan rules yang ketat di Firebase Console.

---

## 🎓 Best Practices Implemented

✅ **Semantic HTML**
- Form elements yang proper
- Input types yang tepat (email, password, date, time)
- Labels terasosiasi dengan input

✅ **Accessibility**
- Color contrast yang cukup
- Font sizes yang readable
- Focus states yang jelas
- Autocomplete attributes

✅ **Performance**
- CSS inline (single file)
- Minimal external dependencies
- LocalStorage caching
- Optimized animations

✅ **UX/UI**
- Clear error messages
- Success feedback
- Loading states
- Empty states
- Confirmation dialogs

✅ **Code Quality**
- Modular JavaScript
- Consistent naming
- Comments & documentation
- Error handling

---

## 🔮 Future Enhancements

Fitur yang bisa ditambahkan:
- 📸 Image upload untuk undangan
- 🎨 Lebih banyak template design
- 📧 Email sending untuk undangan
- 📊 Analytics & statistics
- 💳 Payment integration
- 🔔 Notification system
- 👥 Guest management
- 📱 Mobile app version

---

## 📞 Support & Contact

Untuk pertanyaan atau bug report:
- 📧 Email: support@creatify.my.id
- 🐛 GitHub Issues: [repository]
- 💬 Live Chat: [website]

---

## 📄 License

Project ini menggunakan Firebase yang memiliki Terms of Service sendiri.
Custom code dilisensikan di bawah MIT License.

---

## 🙏 Credits

Dibuat dengan ❤️ untuk mempermudah pembuatan undangan digital.

**Version:** 2.0 (Updated)
**Last Updated:** 2025
**Status:** ✅ Production Ready

---

**Selamat menggunakan Creatify! 🎉**
