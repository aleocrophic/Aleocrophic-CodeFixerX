# Firebase Setup Guide for Aleocrophic CodeFixerX

## 🔧 Error: "The requested action is invalid"

Error ini terjadi karena Firebase Authentication belum dikonfigurasi dengan benar. Ikuti langkah-langkah berikut untuk memperbaikinya:

## 📋 Langkah 1: Firebase Console Setup

### 1. Buat/Configure Firebase Project
1. Buka [Firebase Console](https://console.firebase.google.com/)
2. Pilih project `remchat-fd4ea` atau buat project baru
3. Go to **Project Settings** (⚙️ icon)

### 2. Enable Authentication
1. Di sidebar, klik **Authentication**
2. Klik **Get Started**
3. Pilih **Google** dari sign-in providers
4. **Enable** Google Sign-In
5. Masukkan **Project email** (bisa gunakan email default)
6. Masukkan **Project public-facing name**: `Aleocrophic CodeFixerX`
7. Klik **Save**

### 3. Configure Authorized Domains
1. Di Authentication → **Sign-in method** → **Google**
2. Scroll ke bawah ke **Authorized domains**
3. Tambahkan domain berikut:
   - `localhost` (untuk development)
   - `127.0.0.1` (untuk development)
   - `your-production-domain.com` (untuk production)

### 4. Get Configuration
1. Di Project Settings → **General**
2. Scroll ke **Your apps** section
3. Klik web app icon (</>)
4. Copy **Firebase config** yang sudah ada atau buat baru

## 🌐 Langkah 2: Update Environment Variables

Buat file `.env.local` di root project:

```env
NEXT_PUBLIC_FIREBASE_API_KEY=AIzaSyBpXhfpTR7KGfW5ESH_Z-9Wc8QyJ9YHxv8
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=remchat-fd4ea.firebaseapp.com
NEXT_PUBLIC_FIREBASE_PROJECT_ID=remchat-fd4ea
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=remchat-fd4ea.firebasestorage.app
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=369353956112
NEXT_PUBLIC_FIREBASE_APP_ID=1:369353956112:web:7aff645b1724ec80bfa395
NEXT_PUBLIC_FIREBASE_MEASUREMENT_ID=G-QTHRQNXJKF
```

## 🔒 Langkah 3: Firestore Database Setup

1. Di Firebase Console, buka **Firestore Database**
2. Klik **Create database**
3. Pilih **Start in test mode** (untuk development)
4. Pilih lokasi server yang terdekat

## 🚀 Langkah 4: Restart Development Server

```bash
# Kill existing server
pkill -f "next dev"

# Restart server
npm run dev
```

## 🧪 Testing

### Test Guest Login (Recommended)
1. Klik tombol **"Guest Access"** 
2. Akan langsung masuk tanpa error
3. Cocok untuk testing dan demo

### Test Google Login
1. Klik tombol **"Google Auth"**
2. Akan muncul popup Google Sign-In
3. Jika error muncul, cek:
   - Popup blocker browser
   - Authorized domains configuration
   - API key validity

## 🛠️ Troubleshooting

### Error: "auth/unauthorized-domain"
- **Solution**: Tambahkan domain ke Authorized Domains di Firebase Console

### Error: "auth/popup-blocked" 
- **Solution**: Allow popups untuk localhost di browser settings

### Error: "auth/api-key-not-valid"
- **Solution**: Check API key di Firebase Console dan update .env.local

### Error: "auth/network-request-failed"
- **Solution**: Check internet connection dan firewall settings

## 📝 Alternative: Use Different Firebase Project

Jika project `remchat-fd4ea` tidak bisa diakses:

1. Buat Firebase project baru
2. Enable Authentication (Google Sign-In)
3. Enable Firestore Database
4. Update configuration di `src/app/page.tsx`
5. Update environment variables

## ✅ Verification

Setelah setup selesai:
1. Buka http://localhost:3000
2. Coba **Guest Access** terlebih dahulu (harus berhasil)
3. Coba **Google Auth** untuk testing penuh

## 🆘 Help

Jika masih mengalami masalah:
1. Check browser console untuk error details
2. Verify Firebase project settings
3. Ensure environment variables are correctly set
4. Try using Guest Access for immediate functionality

---

**Note**: Guest Access mode akan selalu bekerja dan memberikan akses penuh ke semua fitur kecuali cloud history.