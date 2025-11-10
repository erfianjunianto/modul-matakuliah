
# 📘 MATERI PERKULIAHAN BLOCKCHAIN
### Program Studi Sistem Informasi — Semester 7  
**Dosen Pengampu:** Erfian Junianto, S.T., M.Kom., CDMP  
**SKS:** 3 (2 teori, 1 praktikum)

---

## 🧩 Pertemuan 1 — Konsep Dasar dan Sejarah Blockchain

### Tujuan Pembelajaran:
Mahasiswa memahami konsep dasar, sejarah, dan karakteristik utama blockchain sebagai teknologi desentralisasi.

### Materi Pokok:
- Sejarah munculnya blockchain (Bitcoin oleh Satoshi Nakamoto, 2008)  
- Konsep **Distributed Ledger Technology (DLT)**  
- Perbedaan sistem **terpusat**, **terdesentralisasi**, dan **terdistribusi**  
- Struktur dasar jaringan peer-to-peer (P2P)  
- Manfaat dan tantangan blockchain dalam sistem informasi  

### Penjelasan:
Blockchain merupakan sistem pencatatan digital yang transparan dan terdistribusi, di mana setiap transaksi disimpan dalam blok dan dihubungkan secara kriptografis. Teknologi ini mengubah paradigma kepercayaan dari otoritas pusat menjadi konsensus jaringan.

### Contoh Kasus:
Transaksi Bitcoin antara dua pengguna tanpa bank sebagai perantara.

### Latihan:
Jelaskan dengan diagram perbedaan antara *centralized network* dan *decentralized network*.

---

## 🧱 Pertemuan 2 — Struktur Blok dan Mekanisme Hashing

### Tujuan:
Mahasiswa memahami struktur blok pada blockchain serta bagaimana fungsi hash menjaga integritas data.

### Materi Pokok:
- Komponen blok: `Header`, `Body`, `Previous Hash`, `Nonce`, `Timestamp`  
- Fungsi hash (SHA-256)  
- Konsep hash chaining  
- Integritas data dan immutability  

### Penjelasan:
Hashing memastikan setiap blok memiliki identitas unik. Jika data dalam blok diubah, hash juga berubah, menyebabkan inkonsistensi pada rantai blok. Inilah dasar keamanan blockchain.

### Contoh:
Gunakan SHA-256 online generator untuk melihat perubahan hash akibat modifikasi data kecil.

### Latihan:
Buat program sederhana (PHP/Python) untuk menghasilkan hash dari input teks.

---

## 🔐 Pertemuan 3 — Algoritma Konsensus dalam Blockchain

### Tujuan:
Mahasiswa dapat membedakan berbagai jenis mekanisme konsensus dan fungsinya dalam menjaga validitas jaringan blockchain.

### Materi Pokok:
- Prinsip konsensus dalam sistem terdistribusi  
- Proof of Work (PoW)  
- Proof of Stake (PoS)  
- Delegated Proof of Stake (DPoS)  
- Proof of Authority (PoA)  

### Penjelasan:
Konsensus adalah mekanisme bagaimana semua node sepakat terhadap status buku besar. PoW mengandalkan daya komputasi, sementara PoS mengandalkan kepemilikan token sebagai bukti partisipasi.

### Contoh:
Perbandingan PoW (Bitcoin) dengan PoS (Ethereum 2.0) dalam hal efisiensi dan keamanan.

### Latihan:
Buat tabel perbandingan kelebihan dan kekurangan antar algoritma konsensus.

---

## 🔁 Pertemuan 4 — Transaksi, Node, dan Validasi Jaringan

### Tujuan:
Mahasiswa memahami mekanisme transaksi di blockchain dan peran node dalam menjaga validitas jaringan.

### Materi Pokok:
- Struktur transaksi blockchain  
- Jenis node: Full Node, Light Node, Miner Node  
- Proses validasi dan broadcast transaksi  
- Mempool dan block propagation  

### Penjelasan:
Transaksi baru disiarkan ke seluruh node di jaringan. Node memverifikasi validitas transaksi sebelum dimasukkan ke dalam blok baru oleh miner. Semua node kemudian memperbarui salinan buku besar masing-masing.

### Contoh:
Simulasi transaksi antara dua alamat Ethereum menggunakan Ganache.

### Latihan:
Gunakan Remix IDE dan Ganache untuk memverifikasi transaksi antar akun lokal.

---

## ⚙️ Pertemuan 5 — Platform Blockchain Populer: Bitcoin, Ethereum, dan Hyperledger

### Tujuan:
Mahasiswa mengenal dan membedakan beberapa platform blockchain utama beserta ekosistemnya.

### Materi Pokok:
- Bitcoin dan mekanisme transaksi UTXO  
- Ethereum dan konsep akun  
- Hyperledger Fabric (blockchain privat)  
- Binance Smart Chain, Cardano, Solana  

### Penjelasan:
Setiap platform memiliki tujuan dan arsitektur berbeda. Bitcoin digunakan untuk transaksi keuangan, sedangkan Ethereum memungkinkan *smart contract*. Hyperledger banyak digunakan untuk sistem enterprise.

### Contoh:
Perbandingan Ethereum (publik) dan Hyperledger (privat) dalam penerapan bisnis.

### Latihan:
Tulis laporan singkat mengenai kelebihan dan kekurangan Hyperledger untuk perusahaan logistik.

---

## 💻 Pertemuan 6 — Pengenalan Smart Contract dan Bahasa Solidity

### Tujuan:
Mahasiswa memahami konsep *smart contract* dan mampu membuat kontrak sederhana menggunakan Solidity di Remix IDE.

### Materi Pokok:
- Pengertian *smart contract*  
- Struktur dasar kontrak Solidity  
- Variabel, fungsi, dan event  
- Kompilasi dan testing di Remix IDE  

### Penjelasan:
Smart contract adalah perjanjian digital yang berjalan otomatis ketika kondisi tertentu terpenuhi. Ia menghilangkan kebutuhan perantara dalam transaksi.

### Contoh Kode:
```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract SimpleStorage {
    uint public data;

    function set(uint x) public {
        data = x;
    }

    function get() public view returns (uint) {
        return data;
    }
}
````

### Latihan:

Buat smart contract yang menyimpan nama dan alamat pengguna.

---

## 🚀 Pertemuan 7 — Deployment Smart Contract di Jaringan Lokal

### Tujuan:

Mahasiswa mampu melakukan *deploy* dan menguji smart contract di jaringan lokal (Ganache).

### Materi Pokok:

* Konfigurasi Ganache
* Penggunaan MetaMask
* Deployment ke jaringan test (Ropsten/Testnet)
* Interaksi dengan kontrak menggunakan Web3.js

### Penjelasan:

Ganache memungkinkan mahasiswa menjalankan jaringan blockchain lokal untuk menguji smart contract tanpa biaya gas nyata.

### Contoh:

Deploy kontrak `SimpleStorage` ke Ganache dan uji fungsi `set()` dan `get()` melalui Remix.

### Latihan:

Buat kontrak untuk mencatat data peserta kuliah menggunakan array.

---

## 🧠 Pertemuan 8 — Ujian Tengah Semester (UTS)

Evaluasi pemahaman konsep dasar blockchain, struktur blok, hash, algoritma konsensus, transaksi, dan smart contract.

---

## 🧩 Pertemuan 9 — Desain Sistem Informasi Berbasis Blockchain

### Tujuan:

Mahasiswa mampu merancang arsitektur sistem informasi dengan integrasi blockchain.

### Materi Pokok:

* Analisis kebutuhan sistem
* Desain arsitektur blockchain
* Diagram alur data dan transaksi
* Integrasi dengan sistem informasi

### Penjelasan:

Tidak semua sistem membutuhkan blockchain. Mahasiswa harus mampu menganalisis masalah dan menentukan posisi blockchain dalam solusi.

### Contoh:

Sistem sertifikat digital berbasis blockchain di universitas.

### Latihan:

Desain diagram arsitektur sistem blockchain untuk kasus peminjaman aset kampus.

---

## 🌐 Pertemuan 10 — Integrasi Blockchain dengan Aplikasi Web Menggunakan Web3.js

### Tujuan:

Mahasiswa mampu menghubungkan smart contract dengan aplikasi web melalui Web3.js.

### Materi Pokok:

* Pengenalan Web3.js dan JSON-RPC
* Interaksi antara frontend dan blockchain
* Membaca dan menulis data ke kontrak
* Manajemen akun dan gas fee

### Penjelasan:

Web3.js memungkinkan aplikasi web (*dApp*) untuk berkomunikasi langsung dengan blockchain, memfasilitasi transaksi dan pembacaan data secara real-time.

### Contoh:

Integrasi smart contract `SimpleStorage` ke halaman web menggunakan JavaScript dan MetaMask.

### Latihan:

Buat form web yang dapat menulis dan membaca data dari smart contract.

---

## 🧮 Pertemuan 11 — Studi Kasus Penerapan Blockchain dalam Dunia Nyata

### Tujuan:

Mahasiswa dapat mengidentifikasi penerapan blockchain dalam berbagai sektor industri.

### Materi Pokok:

* DeFi (Decentralized Finance)
* Supply Chain Management
* E-voting dan E-health
* NFT dan Digital Identity

### Penjelasan:

Blockchain memberikan transparansi dan akuntabilitas yang tinggi, menjadikannya solusi potensial di berbagai sektor seperti keuangan, logistik, dan pemerintahan.

### Contoh:

Sistem e-voting kampus berbasis blockchain.

### Latihan:

Presentasikan studi kasus penerapan blockchain dalam bidang pilihan kelompok Anda.

---

## 🔒 Pertemuan 12 — Keamanan dan Privasi pada Blockchain

### Tujuan:

Mahasiswa memahami isu keamanan dan privasi dalam sistem blockchain serta strategi mitigasinya.

### Materi Pokok:

* Jenis serangan: 51% attack, Sybil attack, replay attack
* Kerentanan smart contract
* Praktik keamanan terbaik
* Audit dan verifikasi kontrak

### Penjelasan:

Meskipun blockchain aman secara desain, implementasi yang buruk dapat menimbulkan celah keamanan. Smart contract perlu diaudit untuk menghindari kerugian seperti *The DAO Hack* (2016).

### Latihan:

Analisis kode kontrak dan identifikasi potensi bug.

---

## ⚖️ Pertemuan 13 — Etika, Hukum, dan Regulasi Blockchain di Indonesia

### Tujuan:

Mahasiswa memahami aspek etis dan legal terkait penerapan blockchain dan aset digital.

### Materi Pokok:

* Regulasi aset kripto di Indonesia (Bappebti, OJK, BI)
* Perlindungan data pribadi (UU PDP)
* Etika penggunaan data publik di blockchain

### Penjelasan:

Blockchain yang bersifat publik menimbulkan tantangan privasi. Pengembang wajib memahami regulasi yang berlaku agar sistem tetap legal dan etis.

### Latihan:

Diskusikan strategi menjaga privasi pengguna di blockchain publik.

---

## 🧾 Pertemuan 14 — Presentasi Proyek Akhir Blockchain

### Tujuan:

Mahasiswa mampu mempresentasikan dan mendemonstrasikan proyek sistem informasi berbasis blockchain.

### Aktivitas:

* Presentasi hasil proyek
* Penilaian ide, arsitektur, dan implementasi
* Refleksi hasil belajar

### Contoh Proyek:

* Sistem sertifikat digital kampus
* E-voting mahasiswa
* Supply chain transparan

---

## 🧩 Pertemuan 15 — Ujian Akhir Semester (UAS)

Evaluasi akhir berbasis laporan proyek dan ujian teori yang mencakup desain, keamanan, dan penerapan blockchain dalam sistem informasi.

---

# 📚 Referensi

1. Antonopoulos, A. M. (2022). *Mastering Bitcoin: Programming the Open Blockchain*. O'Reilly Media.
2. Mougayar, W. (2021). *The Business Blockchain*. Wiley.
3. Ethereum Foundation Documentation — [https://ethereum.org/en/developers/docs/](https://ethereum.org/en/developers/docs/)
4. Hyperledger Foundation — [https://www.hyperledger.org/](https://www.hyperledger.org/)
5. Nakamoto, S. (2008). *Bitcoin: A Peer-to-Peer Electronic Cash System*.

---
