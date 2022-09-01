## Welcome to Stride! - Official Documentation Translation (Bahasa Indonesia)


![logo_stride.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662020826454/DP28yvrSk.png align="center")

### Multichain Liquid Staking

[Twitter](https://twitter.com/stride_zone) | [Discord](http://stride.zone/discord) | [Website](https://stride.zone/)

Apa itu Stride?
Stride adalah blockchain ("zona") yang menyediakan likuiditas untuk aset yang dipertaruhkan. Dengan menggunakan Stride, Anda dapat memperoleh hasil staking dan DeFi di seluruh ekosistem Cosmos IBC. Baca postingan blog "Meet Stride" kami untuk mempelajari lebih lanjut tentang mengapa kami membangun Stride.

Dengan suksesnya peluncuran testnet publik kami, kami dengan senang hati mengumumkan rencana Stride untuk peluncuran mainnet kami pada bulan Juli. Di testnet PoolParty, kami mendukung stATOM liquid staking, tetapi visi Stride jauh lebih luas: kami bertujuan untuk menyediakan liquid staking untuk semua chain di ekosistem Cosmos. Proses untuk onboarding chain baru itu sederhana; siapa pun dapat mengusulkan onboarding chain baru melalui pemungutan suara tata kelola, yang secara otomatis akan onboarding chain baru jika lolos.

Saat peluncuran, kami memprioritaskan chain Cosmos terbesar: kami akan meluncurkan dengan ATOM dan 1-2 chain Cosmos volume tinggi lainnya. Setelah peluncuran, kami berencana untuk memperluas jangkauan kami dengan cepat di seluruh ekosistem Cosmos. Rantai dan token yang kami rencanakan untuk onboard akhir tahun ini adalah:

Cosmos Hub (stATOM), Juno (stJUNO), Secret (stSCRT), Osmosis (stOSMO), Kava (stKAVA), Oasis (stROSE), Axelar (stAXL), Akash (stAKT), Evmos (stEVMOS), Injective (stINJ), Regen (stREGEN), Sommelier (stSOMM), Band (stBAND), dYdX (stDYDX), Terra V2 (stLUNA), Stargaze (stSTARS), Kujira (stKUJI), Umee (stUMEE), E-Money (stNGM), Crypto. Org (stCRO), Comdex (stCMDX), Sifchain (stEROWAN), Crescent Network (stCRE), MediBloc (stMED), Persistence (stXPRT), Iris (stIRIS), AssetMantle (stMNTL), Sentinel (stDVPN), BitSong (stBTSG), Cheqd (stCHEQ), Chihuahua (stHUAHUA), KiChain (stXKI), Ixo (stIXO), Microtick (stTICK), Fetch. Ai (stFET), Konstellation (stDARC), Desmos (stDSM), Bitcanna (stBCNA), Lum Network (stLUM), Bostrom (stBOOT), Likecoin (stLIKE), Dig Chain (stDIG), RiZON (stATOLO), OmniFlix (stFLIX), Decentr (stDEC), Vidulum (stVDL), Altered Carbon (stACB), Shentu (stCTK), dan lain-lain.

Lebih banyak token akan diluncurkan di ekosistem kosmos selama beberapa bulan dan tahun mendatang. Stride berencana untuk mendukung semua token yang kompatibel dengan IBCv3 sebagai "st"-Token.

Stride dibangun menggunakan Cosmos SDK dan Tendermint dan dibuat dengan Ignite. Stride memungkinkan pengguna untuk mempertaruhkan token appchain asli Cosmos SDK yang kompatibel dengan IBC. Di bawah tenda, Stride memanfaatkan protokol Komunikasi Antar-Blockchain, Akun Interchain, dan Kueri Interchain.

### Bagaimana cara kerja Multichain Liquid Staking?

![bb.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662021005806/vpl1l-d4e.png align="center")

### Memulai sebagai Pengembang

Menginstal Stride
Untuk menginstal versi terbaru dari Stride blockchain node binary, jalankan perintah berikut pada mesin anda:

```
git clone https://github.com/Stride-Labs/stride
```
Uji instalasi Anda dengan menavigasi ke direktori stride dan mengeksekusi:

```
ignite chain serve
```
Perintah serve menginstal dependensi, membangun, menginisialisasi, dan memulai blockchain Anda dalam mode pengembangan. Anda akan melihat log yang dicetak ke shell Anda.

Jika Anda memiliki masalah dengan instalasi, silakan hubungi tim kami di Discord.

Anda dapat mempelajari lebih lanjut tentang proses penginstalan di sini atau merujuk pada sumber daya bermanfaat ini:

Starport
Tutorial
Dokumen Starport
Dokumen Cosmos SDK
Obrolan Pengembang

### Membangun di Stride

Pengembang yang ingin mengembangkan Stride dapat dengan mudah memutar 3 node Stride, 3 node Gaia, 1 relayer Hermes, dan 1 relayer interchain-queries. Node Gaia mensimulasikan zona Cosmos Hub (Gaia) di node pengembangan lokal, dan relayer memungkinkan zona Stride untuk berinteraksi dengan contoh Gaia tersebut.

Cara tercepat untuk mengembangkan Stride adalah mode pengembangan lokal.

Mengatur mode pengembangan lokal
Instal dependensi submodul git yang diperlukan (gaia, hermes, interchain-queries).


```
git submodule update --init
``` 

Membangun eksekusi, menginisialisasi state, dan memulai jaringan dengan

```
make init-local build=sghi
``` 
Anda dapat secara opsional meneruskan argumen build untuk menentukan biner mana yang akan dibangun ulang

s Ini akan membangun ulang biner Stride (default)
g Ini akan membangun ulang biner Gaia
h Ini akan membangun ulang biner Hermes
i Ini akan membangun ulang biner ICQ
Contoh: make init-local build=sg, ini akan:

Membangun kembali biner Stride dan Gaia
Mulai 1 Stride dan 1 node Gaia di latar belakang
Memulai Hermes dan ICQ Relayers
Anda dapat secara opsional melewatkan cache=true untuk mengembalikan state dari backup daripada menginisialisasi ulang.

Untuk menurunkan rantai, jalankan:

```
make stop

``` 
Membuat perubahan pada repositori ini
Komit untuk kode perancah
Cara termudah untuk mengembangkan aplikasi cosmos-sdk adalah dengan menggunakan ignite cli untuk scaffold code. Ignite (dikembangkan oleh tim inti cosmos di Tendermint) memungkinkan untuk membuat scaffold chain baru, menjalankan relayer, membangun file proto terkait cosmos, menambahkan pesan/query, menambahkan struktur data baru dan banyak lagi. Kekurangan dari membuat ribuan baris kode menggunakan ignite adalah sulit untuk membedakan perubahan mana yang dibuat oleh ignite cli dan perubahan mana yang dibuat secara manual oleh pengembang. Untuk membuatnya lebih mudah untuk meninjau kode yang ditulis menggunakan ignite dan untuk membuatnya lebih mudah untuk menelusuri kembali langkah-langkah kita jika ada sesuatu yang rusak nantinya, tambahkan commit untuk setiap perintah ignite langsung setelah mengeksekusinya.

Misalnya, menambahkan tipe pesan baru dan memperbarui logika pesan itu akan menjadi dua commit.

```
// add the new data type
>>> ignite scaffold list loan amount fee collateral deadline state borrower lender
>>> git add . && git commit -m 'ignite scaffold list loan amount fee collateral deadline state borrower lender'
// make some updates to the keeper method in your code editor
>>> git add . && git commit -m 'update loan list keeper method'
```
Contoh PR yang menggunakan strategi ini dapat ditemukan di sini. Perhatikan, mudah untuk membedakan antara perubahan yang dibuat oleh ignite dan yang dibuat secara manual dengan meninjau komit. Misalnya, dalam commit fd3e254bc0, mudah untuk melihat bahwa beberapa baris diubah secara manual meskipun hampir ~300k LOC telah di-scaffold.

Format tinjauan kode
Membuka pull request (PR) akan secara otomatis membuat bidang Ringkasan dan Rencana pengujian dalam deskripsi. Dalam ringkasan, tambahkan ringkasan tingkat tinggi tentang apa yang diperlukan oleh perubahan. Untuk pull request yang menggunakan kode ignite scaffold, sertakan perintah scaffold ignite yang dijalankan.

Ringkasan
Tambahkan ringkasan dari pull request di sini (Contoh: Pull request ini menambahkan fitur XYZ ke modul x/ABC dan unit test terkait).

Test plan
Tambahkan rencana pengujian di sini (Contoh: Uji fitur XYZ dengan mengeksekusi unit test D dan E, dengan *sh scripts/tests/tests/unit-test-D.sh dan sh scripts/tests/unit-test-E.sh*)

Konfigurasi
Blockchain Anda dalam pengembangan dapat dikonfigurasi dengan config.yml. Untuk mempelajari lebih lanjut, lihat dokumen Starport.

Rilis
Untuk merilis versi baru blockchain Anda, buat dan dorong tag baru dengan awalan v. Draf rilis baru dengan target yang dikonfigurasi akan dibuat.

```
git tag v0.1
git push origin v0.1
``` 
Setelah draf rilis dibuat, buat perubahan akhir Anda dari halaman rilis dan publikasikan.

### Arsitektur Teknis Stride

Pengguna mempertaruhkan token mereka di Stride dari rantai Cosmos mana pun. Hadiah terakumulasi secara real time. Tidak ada minimum. Mereka akan menerima token yang dipertaruhkan segera ketika mereka mencairkan saham. Token yang dipertaruhkan ini dapat diperdagangkan secara bebas, dan dapat ditukarkan dengan Stride kapan saja untuk menerima token asli Anda ditambah hadiah staking.


![ss.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662021447124/WSulvcY4m.png align="center")

Di bagian belakang, Stride tanpa izin mempertaruhkan token ini pada rantai host dan menambah imbalan pengguna. Stride memungkinkan pengguna menggunakan aset yang dipertaruhkan untuk menambah hasil mereka. Terus mendapatkan hasil staking, dan dapatkan hasil tambahan dengan meminjamkan, LPing, dan banyak lagi. Mereka dapat mengatur toleransi risiko mereka sendiri di Cosmos DeFi.

![as.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662021483347/Eyxh6RTDb.png align="center")

Pengguna selalu dapat menebus dari Stride. Ketika mereka memilih "redeeem" di situs web Stride, Stride akan memulai unbonding di zona host. Setelah periode unbonding berlalu, pengguna akan menerima token asli di dompet mereka.

![miro3.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662021538218/hUsQu99sk.png align="center")

### Stride's Testnet: PoolParty!

Ini berisi instruksi bagaimana cara terhubung ke testnet Stride, PoolParty!

Kami telah mencoba untuk membuat instruksi sesederhana mungkin, tetapi jika Anda memiliki pertanyaan, jangan ragu untuk menghubungi kami melalui email, Twitter, atau di Discord kami.

Persyaratan untuk testnet ini cukup minimal. Anda harus memiliki mesin 4 CPU RAM 32 GB. Kami hanya menguji build ini pada mesin OSX dan Linux, tetapi kami berharap dapat segera mendukung Windows.

### Instalasi 
Jalankan perintah berikut untuk menginstal PoolParty

```
bash -c "$(curl -sSL install.poolparty.stridelabs.co)"
``` 
### Menjalankan Perintah Stride

Silahkan tambahkan repo dengan biner Stride anda (default ke $HOME/go/bin) ke file .bashrc atau .zshrc anda. Kemudian, anda dapat menjalankan strided secara otomatis.

Sebagai contoh, jalankan strided q saldo bank stride159atdlc3ksl50g0659w5tq42wwer334ajl7xnq untuk melihat saldo alamat Stride.

Contoh praktis lainnya, jika Anda menjalankan

```
strided keys list
``` 
Anda bisa melihat kunci lokal Anda. Jika Anda ingin membuat akun baru, silakan jalankan

```
strided keys add <YOUR_WALLET_NAME>
``` 
Jika Anda sudah memiliki dompet dan ingin memulihkannya

```
strided keys add <YOUR_WALLET_NAME> --recover
``` 
Jika Anda menjalankan > strided q help, Anda akan melihat daftar opsi potensial. Beberapa aliran yang berguna adalah

```
strided tx stakeibc liquid-stake
strided tx stakeibc redeem-stake
``` 

### Menjadi Validator

Jika Anda ingin mengubah node Anda menjadi validator, silakan jalankan

```
strided tx staking create-validator \
    --chain-id "<CHAIN_ID>" \
    --commission-rate 0.05 \
    --commission-max-rate 0.2 \
    --commission-max-change-rate 0.1 \
    --min-self-delegation "1000000" \
    --amount 1000000ustrd \
    --pubkey $(strided tendermint show-validator) \
    --moniker "<YOUR_MONIKER>" \
    --gas="auto" \
    --from <YOUR_WALLET_NAME>
``` 
Anda dapat menentukan nilai komisi Anda sendiri atau menambahkan deskripsi validator Anda, seperti --identitas, --situs web, dll.

### Block Explorer

Untuk saat ini, kami menjadi tuan rumah penjelajah blok Ping.Pub di sini. Kami sedang bekerja untuk mengintegrasikan penjelajah blok yang lebih kuat, nantikan saja.

### FAQ?

Di mana saya bisa mendapatkan beberapa token?
Untuk mendapatkan token, kirim pesan  `$faucet {{ADDRESS}}` di Discord. Sebagai contoh, saya akan mengetik `$faucet stride159atdlc3ksl50g0659w5tq42wwer334ajl7xnq`.
Tolong jangan spam ini

Apakah ada variabel yang harus saya ketahui?
Jika `strided` lokal Anda meminta salah satu dari ini, harap diketahui:

```
CHAIN_ID = STRIDE-1
KEYRING_BACKEND = test
HOST_ZONE = GAIA 
STRIDE_CURRENCY = ustrd (1,000,000 ustrd = 1 STRD)
GAIA_CURRENCY = uatom (1,000,000 uatom = 1 ATOM)
GAIA_CURRENCY_ON_STRIDE = ibc/27394FB092D2ECCD56123C74F36E4C1F926001CEADA9CA97EA622B25F41E5EB2
``` 
Bagaimana saya bisa meluncurkan kembali Node saya?

Ketika Anda pertama kali menginstal testnet, Anda seharusnya melihat dua perintah sh yang tercetak di bagian akhir. Ini berisi instruksi untuk bagaimana menghubungkan ke testnet Anda.

Jika Anda menggunakan preset, Anda seharusnya dapat menjalankan perintah berikut untuk meluncurkan kembali node Anda.

`strided start`
atau
`sh $HOME/.stride/poolparty/launch_poolparty.sh`

Mengapa simpul saya memerlukan nama panggilan?

Nama panggilan node Anda adalah bagaimana orang lain dapat melihatnya di block explorer. Misalnya, jika Anda menjadi validator, Anda akan muncul sebagai nama panggilan node Anda.

Saya mengalami masalah perizinan saat membangun, apa yang harus saya lakukan?

Jika Anda mengalami kesalahan izin dengan rasa

```
mkdir: {{path}}: Permission Denied
``` 
Jika demikian, Anda harus menjalankan `chmod +rw {{path}}` untuk memperbaiki perizinannya.

### 
Saya mengalami error building, apa itu?
Silahkan DM kami logfile anda, yang terletak di `$HOME/.stride/install.log`, dan kami dapat membantu anda melakukan debug.

Satu hal yang perlu diperiksa, Stride membutuhkan versi `go 1.18`. Silakan instal ini di sini.

### Bagaimana cara melepaskan validator yang dipenjara?

Jika validator Anda tidak menandatangani blok, maka dia akan dipenjara. Validator yang di-jailed akan terperangkap selama 10 menit dan hanya setelah periode ini anda dapat menggunakan perintah untuk unjail

```
strided tx slashing unjail --chain-id <CHAIN_ID> --dari YOUR_WALLET_NAME
```
### Berkontribusi

Pull request dipersilakan. Untuk perubahan besar, silakan buka isu terlebih dahulu untuk mendiskusikan apa yang ingin Anda ubah. Kami juga menyambut semua diskusi di #engineering atau #pertanyaan di Discord kami.












