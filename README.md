# Sistem Hunter – cara dapat APK

## Cara 1: tanpa install apa pun (GitHub Actions)
1. Buat akun GitHub (gratis), lalu buat repository baru.
2. Upload SELURUH isi folder ini (termasuk folder .github) ke repository.
3. Buka tab **Actions** -> **Build APK** -> **Run workflow**.
4. Tunggu sekitar 5-8 menit. Buka run yang selesai, unduh **sistem-hunter-apk** di bagian Artifacts.
5. Ekstrak zip-nya, kirim app-debug.apk ke HP, lalu install (izinkan "Install dari sumber tidak dikenal").

## Cara 2: build di komputer sendiri
Syarat: Node.js 18+, JDK 17, Android Studio (SDK).
    npm install
    npx cap add android
    npx cap sync android
    cd android && ./gradlew assembleDebug
APK ada di android/app/build/outputs/apk/debug/app-debug.apk

## Catatan
- Ini APK debug, cukup untuk dipakai pribadi. Untuk Google Play perlu APK/AAB release yang ditandatangani keystore.
- Edit tampilan di www/index.html, lalu jalankan `npx cap sync android` dan build ulang.
- Data (profil, latihan, XP) tersimpan di penyimpanan aplikasi di HP.
