# 📘 MODUL BLOCKCHAIN
### Program Studi Sistem Informasi — Semester 7
**Dosen Pengampu:** Erfian Junianto, S.T., M.Kom., CDMP  
**SKS:** 3 (2 teori, 1 praktikum)

---

## Pertemuan 1 — Pengantar Blockchain

### Tujuan Pembelajaran:
Mahasiswa memahami konsep dasar, sejarah, dan karakteristik utama blockchain sebagai teknologi desentralisasi.

### Materi Pokok:
- Sejarah munculnya blockchain (Bitcoin oleh Satoshi Nakamoto, 2008)
- Konsep **Distributed Ledger Technology (DLT)**
- Perbedaan sistem **terpusat**, **terdesentralisasi**, dan **terdistribusi**
- Struktur dasar jaringan peer-to-peer (P2P)
- Manfaat dan tantangan teknologi blockchain dalam sistem informasi

### Penjelasan:
Blockchain adalah sistem pencatatan digital yang terdistribusi dan aman. Setiap transaksi disimpan dalam blok, dan setiap blok saling terhubung membentuk rantai. Tidak ada satu pihak yang memiliki kendali penuh atas data — inilah yang membuatnya transparan dan tahan manipulasi.

### Contoh Kasus:
Transaksi Bitcoin antar pengguna tanpa melalui bank menggunakan alamat publik dan privat key.

### Latihan:
Jelaskan perbedaan antara *centralized* dan *decentralized network* disertai ilustrasi.

---

## Pertemuan 2 — Struktur Blok dan Fungsi Hash

### Tujuan:
Mahasiswa memahami struktur blok blockchain dan peran hash dalam menjamin keamanan data.

### Materi Pokok:
- Elemen dasar blok: `Block Header`, `Block Body`, `Previous Hash`, `Nonce`, `Timestamp`
- Fungsi hash (SHA-256)
- Mekanisme rantai blok
- Integritas data dengan hash chaining

### Penjelasan:
Setiap blok berisi hash unik hasil dari data dalam blok tersebut. Jika ada perubahan sedikit saja pada data, hash akan berubah drastis. Inilah yang menjamin keutuhan dan keaslian data di blockchain.

### Contoh:
Gunakan **SHA-256 generator** online untuk melihat perubahan hash akibat satu huruf yang diubah.

### Latihan:
Buat simulasi sederhana di Python atau PHP untuk menghasilkan hash dari input teks.

---

## Pertemuan 3 — Algoritma Konsensus

### Tujuan:
Mahasiswa mampu menjelaskan dan membedakan berbagai mekanisme konsensus dalam blockchain.

### Materi Pokok:
- Konsep **konsensus** dalam jaringan terdistribusi
- Algoritma:  
  - Proof of Work (PoW)  
  - Proof of Stake (PoS)  
  - Delegated Proof of Stake (DPoS)  
  - Proof of Authority (PoA)
- Keamanan dan efisiensi energi

### Penjelasan:
Konsensus adalah cara jaringan menyetujui data transaksi tanpa otoritas pusat. Misalnya, PoW mengharuskan node menyelesaikan teka-teki kriptografi untuk menambang blok baru.

### Contoh:
Perbandingan PoW (Bitcoin) dan PoS (Ethereum 2.0) dalam hal kecepatan dan konsumsi energi.

### Latihan:
Buat tabel perbandingan antar algoritma konsensus berdasarkan kelebihan dan kekurangan.

---

## Pertemuan 4 — Transaksi dan Node

### Tujuan:
Mahasiswa memahami bagaimana transaksi diproses, divalidasi, dan disimpan di blockchain.

### Materi Pokok:
- Komponen transaksi
- Jenis node: Full Node, Light Node, Miner Node
- Validasi transaksi dan propagasi blok
- Mempool dan mekanisme broadcast

### Penjelasan:
Setiap transaksi baru disiarkan ke seluruh node. Node memverifikasi validitas transaksi, lalu transaksi valid dimasukkan ke dalam blok baru oleh miner.

### Contoh:
Simulasi transaksi antara dua alamat Ethereum di Ganache (local blockchain).

### Latihan:
Gunakan **Remix IDE + Ganache** untuk membuat dan memverifikasi transaksi sederhana.

---

## Pertemuan 5 — Platform Blockchain Populer

### Tujuan:
Mahasiswa mengenal berbagai platform blockchain dan karakteristiknya.

### Materi Pokok:
- Bitcoin Blockchain
- Ethereum Blockchain
- Hyperledger Fabric
- Binance Smart Chain
- Cardano & Solana overview

### Penjelasan:
Setiap platform memiliki arsitektur, algoritma konsensus, dan kegunaan yang berbeda. Ethereum berfokus pada *smart contract*, sedangkan Hyperledger digunakan dalam lingkungan korporat.

### Contoh:
Perbandingan antara Ethereum (publik) dan Hyperledger (private blockchain).

### Latihan:
Tulis laporan singkat tentang kelebihan dan kekurangan Ethereum dan Hyperledger dalam konteks bisnis.

---

## Pertemuan 6 — Pengenalan Smart Contract

### Tujuan:
Mahasiswa mampu membuat *smart contract* sederhana menggunakan Solidity di Remix IDE.

### Materi Pokok:
- Konsep Smart Contract
- Bahasa pemrograman Solidity
- Struktur dasar program (pragma, contract, function)
- Kompilasi dan testing di Remix IDE

### Penjelasan:
Smart contract adalah program otomatis yang berjalan di blockchain. Kontrak ini mengeksekusi transaksi berdasarkan kondisi yang telah disepakati tanpa perantara.

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

Buat kontrak untuk menyimpan dan mengambil data nama pengguna.

---

## Pertemuan 7 — Deployment Smart Contract

### Tujuan:

Mahasiswa dapat melakukan *deploy* dan pengujian smart contract pada jaringan lokal.

### Materi Pokok:

* Ganache (Private Blockchain)
* Penggunaan MetaMask
* Deployment di test network
* Interaksi dengan contract via Remix atau Web3.js

### Penjelasan:

Ganache digunakan untuk membuat jaringan blockchain lokal. Mahasiswa dapat menguji *smart contract* tanpa biaya gas riil.

### Contoh:

Deploy kontrak `SimpleStorage` di Ganache dan uji fungsi `set()` dan `get()`.

### Latihan:

Buat kontrak sederhana untuk mencatat daftar peserta menggunakan array.

---

## Pertemuan 8 — UTS

Evaluasi pemahaman konsep dasar blockchain, struktur blok, hash, konsensus, dan smart contract melalui ujian teori dan studi kasus.

---

## Pertemuan 9 — Desain Sistem Berbasis Blockchain

### Tujuan:

Mahasiswa mampu merancang arsitektur sistem informasi yang memanfaatkan blockchain.

### Materi Pokok:

* Identifikasi kebutuhan sistem
* Desain arsitektur dan komponen
* Integrasi blockchain dalam sistem informasi
* Diagram data flow blockchain

### Penjelasan:

Sebelum mengimplementasikan blockchain, penting untuk menentukan di mana blockchain dibutuhkan (misalnya untuk transparansi, audit trail, atau kepercayaan).

### Contoh:

Desain sistem sertifikat digital berbasis blockchain untuk universitas.

### Latihan:

Gambarlah diagram arsitektur sistem blockchain sesuai studi kasus pilihan Anda.

---

## Pertemuan 10 — Integrasi Blockchain dengan Aplikasi Lain

### Tujuan:

Mahasiswa mampu mengintegrasikan blockchain dengan aplikasi web menggunakan Web3.js.

### Materi Pokok:

* Web3.js dan JSON-RPC API
* Komunikasi antara frontend dan smart contract
* Membaca dan menulis data ke blockchain
* Konsep *gas fee* dan akun MetaMask

### Penjelasan:

Aplikasi frontend dapat berinteraksi langsung dengan smart contract menggunakan library seperti Web3.js. Ini memungkinkan pembuatan aplikasi desentralisasi (*dApp*).

### Contoh:

Integrasi smart contract `SimpleStorage` dengan HTML dan JavaScript menggunakan Web3.js.

### Latihan:

Buat antarmuka web untuk menampilkan dan memperbarui nilai dari smart contract.

---

## Pertemuan 11 — Studi Kasus Penerapan Blockchain

### Tujuan:

Mahasiswa menganalisis penerapan blockchain di dunia nyata.

### Materi Pokok:

* Blockchain di bidang keuangan (DeFi)
* Blockchain untuk logistik dan supply chain
* E-voting, e-health, dan sertifikat digital
* NFT dan aset digital

### Penjelasan:

Blockchain telah digunakan untuk menciptakan sistem yang lebih transparan dan efisien, misalnya pelacakan barang dari produsen ke konsumen secara real-time.

### Contoh:

Sistem e-voting berbasis blockchain untuk pemilihan internal kampus.

### Latihan:

Presentasi kelompok studi kasus penerapan blockchain di bidang tertentu.

---

## Pertemuan 12 — Keamanan dan Privasi Blockchain

### Tujuan:

Mahasiswa memahami risiko keamanan dan privasi dalam blockchain.

### Materi Pokok:

* Serangan umum: 51% attack, Sybil attack, replay attack
* Smart contract vulnerabilities
* Praktik keamanan terbaik
* Audit dan verifikasi smart contract

### Penjelasan:

Meskipun aman secara kriptografi, blockchain tetap dapat diserang jika implementasi smart contract tidak hati-hati.

### Contoh:

Kasus *The DAO Hack (2016)* akibat bug pada smart contract Ethereum.

### Latihan:

Analisis kode smart contract dan identifikasi potensi bug.

---

## Pertemuan 13 — Etika, Hukum, dan Regulasi Blockchain

### Tujuan:

Mahasiswa memahami aspek legal dan etika penggunaan blockchain.

### Materi Pokok:

* Regulasi penggunaan aset kripto di Indonesia (Bappebti, OJK, BI)
* Perlindungan data pribadi (UU PDP)
* Etika penggunaan data publik di blockchain

### Penjelasan:

Blockchain bersifat transparan, sehingga isu privasi menjadi penting. Mahasiswa harus memahami batasan hukum dan etika saat mengembangkan solusi berbasis blockchain.

### Latihan:

Diskusikan bagaimana menjaga privasi pengguna dalam sistem blockchain publik.

---

## Pertemuan 14 — Presentasi Proyek Akhir

### Tujuan:

Mahasiswa mempresentasikan proyek sistem informasi berbasis blockchain.

### Aktivitas:

* Presentasi hasil proyek kelompok
* Penilaian ide, desain, dan implementasi
* Refleksi pembelajaran

### Contoh Proyek:

* Sistem sertifikat digital
* Manajemen supply chain transparan
* E-voting berbasis blockchain kampus

---

## Pertemuan 15 — UAS

Evaluasi akhir berbasis laporan proyek dan tes teori tentang desain dan penerapan blockchain dalam sistem informasi.

---

# Referensi

1. Antonopoulos, A. M. (2022). *Mastering Bitcoin: Programming the Open Blockchain*. O'Reilly Media.
2. Mougayar, W. (2021). *The Business Blockchain*. Wiley.
3. Ethereum Foundation Documentation — [https://ethereum.org/en/developers/docs/](https://ethereum.org/en/developers/docs/)
4. Hyperledger Foundation — [https://www.hyperledger.org/](https://www.hyperledger.org/)
5. Nakamoto, S. (2008). *Bitcoin: A Peer-to-Peer Electronic Cash System*.

---
