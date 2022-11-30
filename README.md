
# ZKSPARK TESTNET from Mina Protocol 

## Referensi

[Official Document](https://docs.minaprotocol.com/zkapps/tutorials/zkapp-ui-with-react)

[Wallet](https://www.aurowallet.com/)

[Faucet](https://faucet.minaprotocol.com/)

[Rules Reward](https://minaprotocol.com/blog/zkspark-cohort0?_hsenc=p2ANqtz-8smwqFrO-bZbm3_8-KWLkOJEV5_-yyWKkPzNswcOViTtGGAsJ2Ixg_W6Efo0kaIah9zr_wPl3trIgYeeJwCA40SGbKOQ&_hsmi=234896730)


### Persyaratan software/OS

| Komponen | Spesifikasi minimal |
|----------|---------------------|
|Sistem Operasi|Ubuntu 16.04|

| Komponen | Spesifikasi rekomendasi |
|----------|---------------------|
|Sistem Operasi|Ubuntu 20.04|

## Siapkan Wallet

1 . [Install Wallet](https://www.aurowallet.com/) (Berkley Network)

2 . [Mina Faucet](https://faucet.minaprotocol.com/) Claim aja semuanya buat jaga2

## 1. Open Port

```
ufw allow 22 && ufw allow 3000
ufw enable
```

## 2. Instal Node Js 16 & NPM & Git (Jika sudah bisa skip)

```
sudo apt update && sudo apt upgrade -y
```
```
sudo apt install git
```
```
sudo apt install -y curl
```
```
curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
```
```
sudo apt install -y nodejs
```

Check Versi Node Js
```
node -v
```
Check Versi NPM 
```
npm -v
```
Check Versi Git
```
git --version
```

## 3 . Install Zkapp CLI

```
git clone https://github.com/o1-labs/zkapp-cli
```
```
npm instal -g zkapp-cli@0.5.3
```

Check Version Zk Apakah Sudah Terinstall Apa Belum
```
zk --version
```

## 4 . Create Project

```
zk project zkapp --ui next
```

pilih Yes 3x dan ```Enter```, tunggu Proses Instalisasi Selesai

## 5 . Buat Repository di Github

Buat nama ```zkapp``` (wajib ikuti nama reponya)

Jalankan di VPS: 

```
cd zkapp
```
```
git remote add origin <your-repo-url>
```
`<Your-Repo-Url>` = Kirim link repository kalian yg tadi di buat

Wajib tambah `.git` di akhir contoh 

```
git remote add origin https://github.com/Zlkcyber/zkapp.git
```
Tinggal ganti `Zlkcyber` jadi `Username` GitHub kalian

```
git branch -M main
git push -u origin main
```

Masukan username github kalian dan setelah itu masukan token github kalian, cara mengambilnya follow step below :

1. Pergi ke `Settingan Profil` Github 
2. `Depelover Setting`
3. `Personal Acces Token` > Pilih yang `Token (Classic)`
4. Lalu `Generate` dan Centang Bagian `Repo`
5. Token Acces Sudah Jadi, Itu Untuk Pengganti Password Github 

## 6 . Run Contract

```
cd
cd zkapp/contracts/
npm run build
```

##  7. Download 2 File Baru 

```
cd
cd zkapp/ui/pages
```
Download 2 file dibawah menggunakan command
```
wget https://raw.githubusercontent.com/Zlkcyber/zkapp/main/zkappWorker.ts
```
```
wget https://raw.githubusercontent.com/Zlkcyber/zkapp/main/zkappWorkerClient.ts
```

## 8 . Download Css 

```
cd
cd zkapp/ui/styles
rm global.css

```
```
wget https://raw.githubusercontent.com/Zlkcyber/zkapp/main/globals.css
```

## 10 .  Running Web Buka 2 Terminal Baru (1 Perintah Masing Masing 1 Tab)

##### TAB 1
```
cd
cd zkapp/ui/
npm run dev
```

##### TAB 2

```
cd
cd zkapp/ui/
npm run ts-watch
```

1. Lalu Buka Browser Chrome http://ip-vps-kalian:3000
2. Pastikan Snarkjs Terbuka (kalau Error Abaikan Saja)
3. Lalu 2 Tab Tersebut Jika Sudah Jalan, Bisa Kalian Close Langsung Atau Kalian Bisa Menjalankan Tab Baru

## 11 . Implementing the react app

```
cd
cd zkapp/ui/pages
rm _app.page.tsx
```

Download file yang baru 
```
wget https://raw.githubusercontent.com/Zlkcyber/zkapp/main/_app.page.tsx
```

## 12 . Deploy UI ke Repository Kalian

```
cd
cd zkapp/ui/
npm run deploy
```

Jika ada Output Error Seperti Ini Abaikan Dan Tunggu Hingga Proses Selesai :

`./pages/_app.page.tsx
95:6  Warning: React Hook useEffect has a missing dependency: 'state'. Either include it or remove the dependency array. You can also do a functional update 'setState(s => ...)' if you only need 'state' in the 'setState' call.  react-hooks/exhaustive-deps
115:6  Warning: React Hook useEffect has a missing dependency: 'state'. Either include it or remove the dependency array. You can also do a functional update 'setState(s => ...)' if you only need 'state' in the 'setState' call.  react-hooks/exhaustive-deps`

1. Nanti Ketika Selesai Anda Akan di Suruh Memasukan Username Github Kalian
2. Masukan Password Github Anda, Ingat di Awal Kita Menggunakan Token Acces. Gunakan Itu Lagi Untuk Password Github (Atau Buat Token Acces Baru Lagi)

## 13 . Cek program apakah lancar

1. `https://<Your-Username>.github.io/04-zkapp-browser-ui/index.html`
2. Your-Username = Ganti Dengan Nama Github Kalian
3. Jika Sudah, Paste ke Browser
4. Jika Berjalan Dengan Baik Maka, Akan Terbuka dan Meminta Aprrove Transaksi dari Wallet Mina 

## 14. Send Beberapa Transaksi (Saran minimal 5)

1. Buka Link `https://<Your-Username>.github.io/04-zkapp-browser-ui/index.html` 
2. Connect Wallet Mina nya dan Approve
3. Refresh Web Tunggu Sampe Muncul Tombol `Send Transaksi` 
4. Tunggu Muncul Pop Up Approve Transaksi > Isi Fee 1 

## 15 . Submit Form Register

1. Link : https://fisz9c4vvzj.typeform.com/zkSparkTutorial
2. Masukan Username Discord
3. Masukan Email Kalian
4. Masukan Link Repo Yang Sudah Kalian Buat di Tahap 13 > Klik Profil Github Kalian > Klik Repository Kalian > Klik 04-zkapp-browser-ui > Masukan Linknya ke Form
5. Masukan Link Web Github Kalian (Yang Kalian Gunakan Untuk Connect Ke Wallet) 
6. kirim feedback 
7. DONE

## DONE, 

## Perintah Berguna (Bukan bagian dari tutorial)
## Delete Node

```
rm -rf 04-zkapp-browser-ui
rm -rf zkapp-cli
rm -rf .npm
npm uninstall -g zkapp-cli
sudo apt-get remove nodejs
```
