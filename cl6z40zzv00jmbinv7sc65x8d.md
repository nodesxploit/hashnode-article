## Stride - Multichain Liquid Staking & Setup Validator (Bahasa Indonesia 🇮🇩)

## 1. Apa itu Stride?

**Stride** adalah blockchain *("zona")* yang menyediakan likuiditas untuk aset yang akan anda stake. Dengan menggunakan **Stride**, anda dapat memperoleh pengembalian staking dan *DeFi* di ekosistem Cosmos melalui Jaringan *Interchain IBC* yang tentunya sangat aman!

Bersamaan dengan itu kami sangat mengapresiasi peluncuran testnet publik yang sangat sukses dengan lebih dari **2.500++ Node Validator** yang terdaftar hingga saat ini di **PoolParty**, mereka mengumumkan rencana peluncuran mainnetnya pada bulan Agustus akhir bulan ini. Untuk *liquid staking* saat ini hanya mendukung *stATOM*, akan tetapi harapan **Stride ** nantinya ingin bertujuan untuk menyediakan *liquid staking* untuk semua chain di ekosistem Cosmos tanpa terkecuali. Adapun proses untuk menambahkan chain baru itu sederhana, siapa pun dapat mengusulkan untuk bergabung dengan chain baru melalui pemungutan suara atau kalian lebih familiar dengan *(vote)*, yang jika diterima, secara otomatis akan dimasukkan ke dalam chain baru nantinya.

Saat peluncuran nanti, **Stride** akan memprioritaskan chain *Cosmos* utama yaitu : *ATOM* dan chain *Cosmos* lainnya yang mempunya volume yang tinggi. Setelah peluncuran, **Stride** berencana untuk memperluas jangkauan mereka dengan cepat di seluruh ekosistem *Cosmos*.

**Melansir dari Team Stride :**

> Situasi DeFi yang saat ini berada di ekosistem Cosmos itu tidak efisien. User dipaksa untuk memilih antara mempertaruhkan token mereka untuk mendapatkan keuntungan atau berpartisipasi dalam Ekosistem *Cosmos DeFi*, yang membuat diri mereka lebih **"berisiko"** untuk mendapatkan lebih banyak keuntungan. Ini seharusnya tidak menjadi masalah yang berarti.

**Apakah Stride akan mendukung semua token khususnya di jaringan *Cosmos*??**

Yep! **Stride** berencana untuk mendukung semua token yang sesuai dengan *IBC V3* sebagai *("st"-Token)* kedepannya.

Berikut adalah chain dan token yang **Stride** rencanakan untuk ditambahkan tahun ini antara lain:

> Cosmos Hub ( stATOM ), Juno ( stJUNO ), Secret ( stSCRT ), Osmosis ( stOSMO ), Kava ( stKAVA ), Oasis ( stROSE ), Axelar ( stAXL ), Akash ( stAKT ), Evmos ( stEVMOS ), Suntik ( stINJ ), Regen ( stREGEN ), Sommelier ( stSOMM ), Band ( stBAND ), dYdX ( stDYDX ), Terra V2 ( stLUNA ), Stargaze ( stSTARS ), Kujira ( stKUJI ), Umee ( stUMEE ), E-Para ( stNGM ), Kripto. Org ( stCRO ), Comdex ( stCMDX ), Sifchain ( STEROWAN ), Crescent Network ( stCRE ), MediBloc ( stMED ), Persistence ( stXPRT ), Iris ( stIRIS ), AssetMantle ( stMNTL ), Sentinel ( stDVPN ), BitSong ( stDVPN ) ( stCHEQ ), Chihuahua ( stHUAHUA ), KiChain ( stXKI ), Ixo ( stIXO ), Microtick ( stTICK ), Fetch. Ai ( stFET ), Konstellation ( stDARC ), Desmos ( stDSM ), Bitcanna ( stBCNA ), Lum Network ( stLUM ), Bostrom ( stBOOT ), Likecoin ( stLIKE ), Dig Chain ( stDIG ), RiZON ( stATOLO ), OmniFlix ( stFLIX ), Decentr ( stDEC ), Vidulum ( stVDL ), Modified Carbon ( stACB ), Shentu, ( stCT ) dan masih banyak lagi nantinya.

**Apakah biaya transaksi di jaringan Stride mahal??**

Tentu saja tidak dengan biaya transaksi yang cukup rendah bahkan tergolong sangat rendah dibandingkan dengan chain *Cosmos* yang lain.
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660857596650/KkrBj5eLu.png align="left")

**Lalu, Bagaimana cara kerja Stride *PoolParty*?**

**Stride** dibangun menggunakan *Cosmos SDK* dan *Tendermint* dan dibangun dengan* Ignite* sebagai *DeFi*. **Stride** memungkinkan pengguna untuk berbagi token secara mandiri melalui *Cosmos SDK* yang tentunya sesuai dengan Protokol/Jaringan IBC. **Stride** sendiri memanfaatkan protokol komunikasi dengan skema seperti ini* (Antar-Rantai --> Blok-ke-Blok --> Akun Antar-Rantai --> Kueri Antar-Rantai)*.


**Selanjutnya, bagaimana cara kerja dari *Multichain Liquid Staking*?**

Berikut adalah skema bagaimana cara Multichain Liquid Staking Bekerja 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660858908659/V9Q7ncZgV.png align="left")

## 2. Perisapan menjalankan Validator
![111.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660865134044/ahplVKVsq.png align="left")

Seperti kebanyakan hardware *Cosmos SDK* pada umumnya, berikut adalah spesifikasi "minimal" untuk menjalankan stride validator.

### Spesifikasi minimal yang dibutuhkan
 - 4x CPUs; lebih cepat clock speed, lebih baik.
 - 8GB RAM
 - 100GB penyimpanan (SSD atau NVME)
 - Permanen koneksi internet (trafik yang dibutuhkan untuk testnet; 10Mbps itu sudah cukup banyak - akan tetapi untuk produksi blok setidaknya 100Mbps)

### Spesifikasi yang disarankan
 - 4x CPUs; lebih cepat clock speed, lebih baik.
 - 32GB RAM
 - 200GB penyimpanan (SSD atau NVME)
 - Permanen koneksi internet (trafik yang dibutuhkan untuk testnet; 10Mbps itu sudah cukup banyak - akan tetapi untuk produksi blok setidaknya 100Mbps)

### Persiapan Menjalankan *Stride *Fullnode*

### Opsi ke 1 (otomatis)
Pengguna dapat menjalankan *stride fullnode* dalam hitungan menit dengan menggunakan skrip otomatis dibawah. jangan lupa masukkan nama validatormu!

```
wget -O stride.sh https://raw.githubusercontent.com/nodesxploit/testnet/main/stride/stride.sh && chmod +x stride.sh && ./stride.sh
```

### Opsi ke 2 (manual)
Pengguna dapat menjalankan fullnode secara manual dengan cara mengikuti langkah-langkah di bawah ini

### Pengaturan Variabel
Di sini pengguna harus memasukkan nama moniker (validator) yang nantinya akan terlihat di explorer

```
NODENAME=<MONIKER>
```
Simpan lalu impor variabel ke sistem

```
STRIDE_PORT=16
echo "export NODENAME=$NODENAME" >> $HOME/.bash_profile
if [ ! $WALLET ]; then
	echo "export WALLET=wallet" >> $HOME/.bash_profile
fi
echo "export STRIDE_CHAIN_ID=STRIDE-TESTNET-2" >> $HOME/.bash_profile
echo "export STRIDE_PORT=${STRIDE_PORT}" >> $HOME/.bash_profile
source $HOME/.bash_profile
```

## Perbarui paket

```
sudo apt update && sudo apt upgrade -y
```

## Menginstall dependensi

```
sudo apt install curl build-essential git wget jq make gcc tmux chrony -y
```

## Menginstall Go!

```
if ! [ -x "$(command -v go)" ]; then
  ver="1.18.2"
  cd $HOME
  wget "https://golang.org/dl/go$ver.linux-amd64.tar.gz"
  sudo rm -rf /usr/local/go
  sudo tar -C /usr/local -xzf "go$ver.linux-amd64.tar.gz"
  rm "go$ver.linux-amd64.tar.gz"
  echo "export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin" >> ~/.bash_profile
  source ~/.bash_profile
fi
```

## Unduh Binari

```
cd $HOME
git clone https://github.com/Stride-Labs/stride.git
cd stride
git checkout 3cb77a79f74e0b797df5611674c3fbd000dfeaa1
make build
sudo cp $HOME/stride/build/strided /usr/local/bin
```

## Konfigurasi Aplikasi

```
strided config chain-id $STRIDE_CHAIN_ID
strided config keyring-backend test
strided config node tcp://localhost:${STRIDE_PORT}657
```

## Inisiai Aplikasi

```
strided init $NODENAME --chain-id $STRIDE_CHAIN_ID
```

## Unduh genesis dan addrbook

```
wget -qO $HOME/.stride/config/genesis.json "https://raw.githubusercontent.com/Stride-Labs/testnet/main/poolparty/genesis.json"
```

## Atur Seed dan Peers

```
SEEDS="c0b278cbfb15674e1949e7e5ae51627cb2a2d0a9@seedv2.poolparty.stridenet.co:26656"
PEERS="6a9c9871d115c97acc56cb47aa96ccac1728d42d@51.75.135.47:16656,02073421dfeb1fc9426698250db8db68a60b3865@35.184.123.9:26656,efb44e5336800b589053a13f2ee94d3d1cfe19d8@65.108.62.95:12656,11cf69772d08210baa7eff2728efb190cc8103db@46.146.231.96:26656,0c5521e59c227726888504e3f857beb5973d113c@65.108.76.44:11523,e981b87ff961e991f0915301e50f408b33bfdd60@143.198.43.17:16656,c9975b81d7f3afdf5179651c76a013baf70d13ce@62.171.172.182:16656,d7b72c668e32bf1e5efa7d196047188d5a6f1db8@65.108.231.252:46656,73f15ad99a0ac6e60cda2b691bc5b71cd7f221bc@141.95.124.151:20086,f4e9b46abb91c1cf328e28cc195964958ff621b9@65.108.45.200:26959,f6e804d1d509db730de171cf1d0553d701c5140f@142.132.235.215:16656,830a6dcc085dbe37ba0d6c15ac2b10c95d5ba5c3@158.247.231.2:26656,03a532495fc6a2ec20f29318aeb6c9a54286312a@89.163.221.56:26656,ae03ae125b456b4d8df8658917910ec259e14f8b@149.102.131.174:16656,1c06803eb8dda04473f2a5d8419f26126d6d1b09@89.58.45.204:26656,be60859ea3cc6e4d37d50c81c1841355b6885109@86.48.2.79:26656,05313ff7326221035692e5c43198d13ee9079cc7@116.203.47.199:26656,fdcbb0a1d58e4bb934606abaa0e7eb9fc8ef3227@159.223.231.90:16656,c95397b6cc5282a1525bef49bcdd3119847f324e@149.102.139.103:26656,4aed611d0f9758d2362c7d28f067eb6ecd833927@147.182.250.27:16656,dfdc971008bbc3910bcd71855d229e19b8534dbf@159.223.203.149:16656,bb3daec1234c4cbd18b26b13ab9c1db8fbd17f83@38.242.146.249:16656,89fc167903c6f8afd519cbc8cc1542ac6467f911@135.181.133.248:11656,3e17bda1c34f025b8397b5baeaef5000c4c21ddd@213.239.213.179:26656,3e8741d3ae96e08439e7da308ebf1e6651acb02a@167.71.77.205:16656,a3afae256ad780f873f85a0c377da5c8e9c28cb2@54.219.207.30:26656,1aa3c20fd33fd1ece537e695fd67c49efe9e806d@34.125.11.162:26656,4e26c5b8206c116192ceb7f6b5efa176312198ad@185.205.244.117:26656"
sed -i -e "s/^seeds *=.*/seeds = \"$SEEDS\"/; s/^persistent_peers *=.*/persistent_peers = \"$PEERS\"/" $HOME/.stride/config/config.toml
```

## Atur kustom port

```
sed -i.bak -e "s%^proxy_app = \"tcp://127.0.0.1:26658\"%proxy_app = \"tcp://127.0.0.1:${STRIDE_PORT}658\"%; s%^laddr = \"tcp://127.0.0.1:26657\"%laddr = \"tcp://127.0.0.1:${STRIDE_PORT}657\"%; s%^pprof_laddr = \"localhost:6060\"%pprof_laddr = \"localhost:${STRIDE_PORT}060\"%; s%^laddr = \"tcp://0.0.0.0:26656\"%laddr = \"tcp://0.0.0.0:${STRIDE_PORT}656\"%; s%^prometheus_listen_addr = \":26660\"%prometheus_listen_addr = \":${STRIDE_PORT}660\"%" $HOME/.stride/config/config.toml
sed -i.bak -e "s%^address = \"tcp://0.0.0.0:1317\"%address = \"tcp://0.0.0.0:${STRIDE_PORT}317\"%; s%^address = \":8080\"%address = \":${STRIDE_PORT}080\"%; s%^address = \"0.0.0.0:9090\"%address = \"0.0.0.0:${STRIDE_PORT}090\"%; s%^address = \"0.0.0.0:9091\"%address = \"0.0.0.0:${STRIDE_PORT}091\"%" $HOME/.stride/config/app.toml
```

## Pemangkasan konfigurasi

```
pruning="custom"
pruning_keep_recent="100"
pruning_keep_every="0"
pruning_interval="50"
sed -i -e "s/^pruning *=.*/pruning = \"$pruning\"/" $HOME/.stride/config/app.toml
sed -i -e "s/^pruning-keep-recent *=.*/pruning-keep-recent = \"$pruning_keep_recent\"/" $HOME/.stride/config/app.toml
sed -i -e "s/^pruning-keep-every *=.*/pruning-keep-every = \"$pruning_keep_every\"/" $HOME/.stride/config/app.toml
sed -i -e "s/^pruning-interval *=.*/pruning-interval = \"$pruning_interval\"/" $HOME/.stride/config/app.toml
```

## Tetapkan harga gas minimum dan komitmen batas waktu

```
sed -i -e "s/^minimum-gas-prices *=.*/minimum-gas-prices = \"0ustrd\"/" $HOME/.stride/config/app.toml
```

## Aktifkan prometheus

```
sed -i -e "s/prometheus = false/prometheus = true/" $HOME/.stride/config/config.toml
```

## Pengaturan Ulang

```
strided tendermint unsafe-reset-all --home $HOME/.stride
```

## Membuat Servis

```
sudo tee /etc/systemd/system/strided.service > /dev/null <<EOF
[Unit]
Description=stride
After=network-online.target

[Service]
User=$USER
ExecStart=$(which strided) start --home $HOME/.stride
Restart=on-failure
RestartSec=3
LimitNOFILE=65535

[Install]
WantedBy=multi-user.target
EOF
```

## Daftar dan mulai jalankan servis

```
sudo systemctl daemon-reload
sudo systemctl enable strided
sudo systemctl restart strided && sudo journalctl -u strided -f -o cat
```

## Pasca Pemasangan

Ketika instalasi selesai, silakan muat variabel ke dalam sistem

```
source $HOME/.bash_profile
```

Selanjutnya Anda harus memastikan validator Anda menyinkronkan blok. Anda dapat menggunakan perintah di bawah ini untuk memeriksa status sinkronisasi.

```
strided status 2>&1 | jq .SyncInfo
```

### Membuat dompet
Untuk membuat wallet baru, anda dapat menggunakan perintah di bawah ini. Jangan lupa untuk menyimpan mnemonic.

```
strided keys add $WALLET
```

(OPSIONAL) Untuk memulihkan dompet Anda menggunakan seed phrase

```
strided keys add $WALLET --recover
```

Untuk mendapatkan daftar wallet saat ini

```
strided keys list
```

### Menyimpan informasi dompet
Tambahkan dompet dan alamat valoper ke dalam variabel 

```
STRIDE_WALLET_ADDRESS=$(strided keys show $WALLET -a)
STRIDE_VALOPER_ADDRESS=$(strided keys show $WALLET --bech val -a)
echo 'export STRIDE_WALLET_ADDRESS='${STRIDE_WALLET_ADDRESS} >> $HOME/.bash_profile
echo 'export STRIDE_VALOPER_ADDRESS='${STRIDE_VALOPER_ADDRESS} >> $HOME/.bash_profile
source $HOME/.bash_profile
```

### Danai dompet Anda
Untuk membuat validator, pertama-tama Anda perlu mendanai dompet Anda dengan token testnet.
Untuk mengisi ulang dompet Anda, bergabunglah dengan [Stride discord server](https://discord.gg/n6KrK77t) dan arahkan ke:

- **#token-faucet** untuk meminta tes token

Untuk meminta faucet cukup gunakan command dibawah

```
$faucet-stride:<STRIDE_WALLET_ADDRESS>
```

### Membuat validator
Sebelum membuat validator, pastikan bahwa Anda memiliki setidaknya 1 strd (1 strd sama dengan 1000000 ustrd) dan node Anda wajib sinkron ke blok terakhir

Untuk memeriksa saldo dompet Anda:

```
strided query bank balances $STRIDE_WALLET_ADDRESS
```
> Jika dompet Anda tidak menunjukkan saldo apa pun, mungkin node Anda masih melakukan sinkronisasi. Harap tunggu sampai selesai untuk menyinkronkan dan kemudian lanjutkan

Untuk membuat validator Anda, jalankan perintah di bawah ini

```
strided tx staking create-validator \
  --amount 10000000ustrd \
  --from $WALLET \
  --commission-max-change-rate "0.01" \
  --commission-max-rate "0.2" \
  --commission-rate "0.07" \
  --min-self-delegation "1" \
  --pubkey  $(strided tendermint show-validator) \
  --moniker $NODENAME \
  --chain-id $STRIDE_CHAIN_ID
```

## Operasi dengan liquid staking

### Tambahkan liquid stake

**Liquid stake** *ATOM* Anda di *Stride* untuk *stATOM*. Berikut adalah contoh cara liquid stake

```
strided tx stakeibc liquid-stake 1000 uatom --from $WALLET --chain-id $STRIDE_CHAIN_ID
```
> Catatan: jika Anda cairkan taruhan 1000 uatom, Anda mungkin hanya mendapatkan 990 (bisa lebih atau kurang) stATOM sebagai imbalannya! Ini karena cara kerja nilai tukar kami. 990 stATOM Anda masih bernilai 1000 uatom (atau lebih, saat Anda mengumpulkan hadiah staking!)

### Tebus Stake
Setelah mendapatkan beberapa reward staking, Anda dapat melepaskan token Anda. Saat ini, periode unbonding di testnet Gaia (Cosmos Hub) kami adalah sekitar 30 menit.

```
strided tx stakeibc redeem-stake 1000 GAIA <COSMOS_ADDRESS_YOU_WANT_TO_REDEEM_TO> --chain-id $STRIDE_CHAIN_ID --from $WALLET
```

### Periksa apakah token dapat diklaim
Jika Anda ingin melihat apakah token Anda siap untuk diklaim, cari `UserRedemptionRecord` Anda yang dikunci oleh `<your_stride_account>`.

```
strided q records list-user-redemption-record --limit 10000 --output json | jq --arg WALLET_ADDRESS "$STRIDE_WALLET_ADDRESS" '.UserRedemptionRecord | map(select(.sender == $WALLET_ADDRESS))'
```
Jika record Anda memiliki atribut `isClaimable=true`, maka record tersebut siap untuk diklaim!

### Klaim Token
Setelah token Anda terlepas, token tersebut dapat diklaim dengan memicu proses klaim.
 
```
wget -qO claim.sh https://raw.githubusercontent.com/nodesxploit/testnet/main/stride/tools/claim.sh && chmod +x claim.sh
./claim.sh $STRIDE_WALLET_ADDRESS
```
> Catatan: fungsi ini memicu klaim dalam antrean FIFO, yang berarti jika klaim Anda berada di urutan ke-20, Anda harus memproses klaim lain sebelum melihat token Anda muncul di akun Anda.

## Menghitung waktu sinkronisasi
Script ini akan membantu Anda memperkirakan berapa banyak waktu yang dibutuhkan untuk sepenuhnya menyinkronkan node Anda. Script ini mengukur blok rata-rata per menit yang sedang disinkronkan selama periode 5 menit dan kemudian memberi Anda hasil.

```
wget -O synctime.py https://raw.githubusercontent.com/nodesxploit/testnet/main/stride/tools/synctime.py && python3 ./synctime.py
```

### Cek kunci validator

```
[[ $(strided q staking validator $STRIDE_VALOPER_ADDRESS -oj | jq -r .consensus_pubkey.key) = $(strided status | jq -r .ValidatorInfo.PubKey.value) ]] && echo -e "\n\e[1m\e[32mTrue\e[0m\n" || echo -e "\n\e[1m\e[31mFalse\e[0m\n"
```

### Mendapatkan list validator
 
```
strided q staking validators -oj --limit=3000 | jq '.validators[] | select(.status=="BOND_STATUS_BONDED")' | jq -r '(.tokens|tonumber/pow(10; 6)|floor|tostring) + " \t " + .description.moniker' | sort -gr | nl
```

## Mendapatkan list peers mana yang sudah terhubung

```
curl -sS http://localhost:${STRIDE_PORT}657/net_info | jq -r '.result.peers[] | "\(.node_info.id)@\(.remote_ip):\(.node_info.listen_addr)"' | awk -F ':' '{print $1":"$(NF)}'
```

## Perintah yang membantu

### Manajemen Servis

Cek log

```
journalctl -fu strided -o cat
```

Mulai Servis

```
sudo systemctl start strided
```

Hentikan Servis

```
sudo systemctl stop strided
```

Mulai Ulang Serivice

```
sudo systemctl restart strided
```

### Informasi Node

Informasi Sinkronasi

```
strided status 2>&1 | jq .SyncInfo
```

Informasi Validator

```
strided status 2>&1 | jq .ValidatorInfo
```

Informasi Node

```
strided status 2>&1 | jq .NodeInfo
```

Menampilkan ID Node

```
strided tendermint show-node-id
```

### Daftar Perintah untuk pengaturan dompet

Daftar wallet

```
strided keys list
```

Memulihkan wallet

```
strided keys add $WALLET --recover
```

Menghapus wallet

```
strided keys delete $WALLET
```

Mendapatkan informasi saldo dompet

```
strided query bank balances $STRIDE_WALLET_ADDRESS
```

Mengirim dana

```
strided tx bank send $STRIDE_WALLET_ADDRESS <TO_STRIDE_WALLET_ADDRESS> 10000000ustrd
```

### Pemungutan Suara

```
strided tx gov vote 1 yes --from $WALLET --chain-id=$STRIDE_CHAIN_ID
```

### Pengintaian, Pendelegasian dan Imbalan

Delegasi

```
strided tx staking delegate $STRIDE_VALOPER_ADDRESS 10000000ustrd --from=$WALLET --chain-id=$STRIDE_CHAIN_ID --gas=auto
```

Mendelegasikan kembali dari validator ke validator lain

```
strided tx staking redelegate <srcValidatorAddress> <destValidatorAddress> 10000000ustrd --from=$WALLET --chain-id=$STRIDE_CHAIN_ID --gas=auto
```

Menarik seluruh hadiah

```
strided tx distribution withdraw-all-rewards --from=$WALLET --chain-id=$STRIDE_CHAIN_ID --gas=auto
```

Menarik seluruh hadiah dengan komisi

```
strided tx distribution withdraw-rewards $STRIDE_VALOPER_ADDRESS --from=$WALLET --commission --chain-id=$STRIDE_CHAIN_ID
```

### Manajemen Validator

Mengubah informasi validator

```
strided tx staking edit-validator \
  --moniker=$NODENAME \
  --identity=<your_keybase_id> \
  --website="<your_website>" \
  --details="<your_validator_description>" \
  --chain-id=$STRIDE_CHAIN_ID \
  --from=$WALLET
```

Unjail validator

```
strided tx slashing unjail \
  --broadcast-mode=block \
  --from=$WALLET \
  --chain-id=$STRIDE_CHAIN_ID \
  --gas=auto
```

### Hapus Node
Perintah ini akan sepenuhnya menghapus node dari server. Gunakan dengan risiko Anda sendiri!

```
sudo systemctl stop strided
sudo systemctl disable strided
sudo rm /etc/systemd/system/stride* -rf
sudo rm $(which strided) -rf
sudo rm $HOME/.stride* -rf
sudo rm $HOME/stride -rf
sed -i '/STRIDE_/d' ~/.bash_profile
```


