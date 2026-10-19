# Essenca
PWA persiapan sertifikasi Chartered Accountant (CA): rangkuman modul, latihan soal dengan koreksi otomatis, jadwal belajar harian.

## Setup
1. Firebase Console > proyek **Essenca** > Authentication > aktifkan **Email/Password**.
2. Project settings > Your apps > Web app > salin `firebaseConfig`, tempel ke `FIREBASE_CONFIG` di `index.html`.
3. Firestore Database > Rules, ganti dengan:
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /users/{uid} {
      allow read, write: if request.auth != null && request.auth.uid == uid;
    }
  }
}
```
4. Authentication > Settings > Authorized domains: tambahkan `USERNAME.github.io`.
5. Upload semua file ke GitHub, aktifkan Settings > Pages (branch main, root).

Tanpa konfigurasi Firebase, aplikasi berjalan dalam mode lokal (data di perangkat).
Materi & soal adalah ringkasan latihan; cocokkan dengan silabus resmi CA.
