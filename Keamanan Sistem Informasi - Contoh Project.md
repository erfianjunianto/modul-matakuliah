# 📘 Modul Project — Keamanan Sistem Informasi (Implementasi dengan PHP)

---

## 🧩 **Judul Modul**

**Penerapan Keamanan Sistem Informasi Menggunakan PHP**

---

## 🎯 **Tujuan Pembelajaran**

Setelah mempelajari modul ini, mahasiswa diharapkan mampu:

1. Memahami konsep dasar keamanan aplikasi web.
2. Menerapkan teknik validasi input dan pencegahan serangan *SQL Injection*.
3. Mengimplementasikan enkripsi dan verifikasi password secara aman.
4. Menggunakan *session* dan *header security* untuk melindungi sistem dari serangan umum.

---

## 📖 **Deskripsi Singkat**

Modul ini menjelaskan praktik penerapan keamanan dalam aplikasi berbasis PHP dan MySQL. Mahasiswa akan mempelajari bagaimana melindungi data pengguna dari serangan seperti SQL Injection, XSS, serta menerapkan autentikasi dengan password hashing.

---

## ⚙️ **Lingkungan Pengembangan**

* Bahasa Pemrograman: PHP 8+
* Database: MySQL / MariaDB
* Web Server: Apache / Nginx
* Tools: XAMPP / Laragon / Localhost environment

---

## 🧱 **Struktur Folder Proyek**

```
secure_app/
│
├── config/
│   └── db.php
│
├── register.php
├── login.php
├── dashboard.php
├── logout.php
└── README.md
```

---

## 📁 **1. Koneksi Database Aman (`config/db.php`)**

```php
<?php
$host = 'localhost';
$dbname = 'secure_db';
$username = 'root';
$password = '';

try {
    $pdo = new PDO("mysql:host=$host;dbname=$dbname;charset=utf8mb4", $username, $password);
    $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
} catch (PDOException $e) {
    die("Koneksi gagal: " . $e->getMessage());
}
?>
```

**Penjelasan:**

* Menggunakan **PDO (PHP Data Object)** agar lebih aman dan fleksibel.
* `setAttribute()` digunakan untuk menampilkan error dengan format *exception*.

---

## 👤 **2. Registrasi Aman (`register.php`)**

```php
<?php
require_once "config/db.php";

if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $email = filter_var($_POST['email'], FILTER_SANITIZE_EMAIL);
    $password = $_POST['password'];

    // Hash password dengan bcrypt
    $hashedPassword = password_hash($password, PASSWORD_BCRYPT);

    $sql = "INSERT INTO users (email, password) VALUES (:email, :password)";
    $stmt = $pdo->prepare($sql);
    $stmt->bindParam(':email', $email);
    $stmt->bindParam(':password', $hashedPassword);

    if ($stmt->execute()) {
        echo "Registrasi berhasil! Silakan login.";
    } else {
        echo "Terjadi kesalahan. Coba lagi.";
    }
}
?>

<form method="POST">
    Email: <input type="email" name="email" required><br>
    Password: <input type="password" name="password" required><br>
    <button type="submit">Daftar</button>
</form>
```

**Penjelasan:**

* Input disaring menggunakan `filter_var()`.
* Password dienkripsi menggunakan **bcrypt** sebelum disimpan.
* Menggunakan **prepared statement** untuk mencegah *SQL Injection*.

---

## 🔑 **3. Login Aman (`login.php`)**

```php
<?php
session_start();
require_once "config/db.php";

if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $email = htmlspecialchars($_POST['email']);
    $password = $_POST['password'];

    $sql = "SELECT * FROM users WHERE email = :email";
    $stmt = $pdo->prepare($sql);
    $stmt->bindParam(':email', $email);
    $stmt->execute();
    $user = $stmt->fetch(PDO::FETCH_ASSOC);

    if ($user && password_verify($password, $user['password'])) {
        session_regenerate_id(true);
        $_SESSION['user'] = $user['email'];
        header("Location: dashboard.php");
        exit;
    } else {
        echo "Email atau password salah!";
    }
}
?>

<form method="POST">
    Email: <input type="email" name="email" required><br>
    Password: <input type="password" name="password" required><br>
    <button type="submit">Login</button>
</form>
```

**Penjelasan:**

* `password_verify()` digunakan untuk mencocokkan password input dengan hash yang tersimpan.
* `session_regenerate_id(true)` digunakan untuk mencegah *session fixation*.

---

## 🧭 **4. Dashboard Aman (`dashboard.php`)**

```php
<?php
session_start();

if (!isset($_SESSION['user'])) {
    header("Location: login.php");
    exit;
}

header("X-Frame-Options: DENY");
header("X-Content-Type-Options: nosniff");
header("X-XSS-Protection: 1; mode=block");

echo "<h2>Selamat datang, " . htmlspecialchars($_SESSION['user']) . "</h2>";
echo "<a href='logout.php'>Logout</a>";
?>
```

**Penjelasan:**

* Menambahkan header keamanan seperti:

  * `X-Frame-Options: DENY` → mencegah *clickjacking*.
  * `X-XSS-Protection` → melindungi dari *Cross-Site Scripting*.
* Melindungi output dengan `htmlspecialchars()`.

---

## 🚪 **5. Logout (`logout.php`)**

```php
<?php
session_start();
session_unset();
session_destroy();
header("Location: login.php");
exit;
?>
```

**Penjelasan:**

* `session_unset()` menghapus semua variabel session.
* `session_destroy()` menghapus session secara permanen.

---

## 🧰 **6. Database SQL**

Gunakan script SQL berikut untuk membuat tabel user.

```sql
CREATE DATABASE secure_db;
USE secure_db;

CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    email VARCHAR(100) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL
);
```

---

## 🧪 **7. Uji Coba**

1. Jalankan `register.php` → buat akun baru.
2. Jalankan `login.php` → login dengan akun tersebut.
3. Coba akses `dashboard.php` tanpa login → harus diarahkan ke `login.php`.
4. Klik Logout → harus menghapus session dan kembali ke halaman login.

---

## 📋 **Evaluasi dan Pertanyaan**

1. Jelaskan perbedaan antara `password_hash()` dan `md5()` dalam hal keamanan.
2. Mengapa prepared statement lebih aman dibandingkan query biasa?
3. Bagaimana cara menambahkan fitur *rate limiting* untuk mencegah *brute force attack*?

---

## 📚 **Referensi**

1. PHP Manual: [https://www.php.net/manual/en/](https://www.php.net/manual/en/)
2. OWASP Top 10 Security Risks — [https://owasp.org/Top10/](https://owasp.org/Top10/)
3. RFC 2196: *Site Security Handbook*
4. Stallings, W. (2023). *Cryptography and Network Security: Principles and Practice*. Pearson.
