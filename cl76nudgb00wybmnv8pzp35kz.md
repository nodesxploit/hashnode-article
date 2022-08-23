## BlockPi - Panduan Instalasi HyperNode

 ### HyperNode

HyperNode adalah node layanan RPC terdesentralisasi utama yang memproses permintaan RPC dan mengirim tanggapan kepada pengguna melalui Gateway. HyperNode biasanya dijalankan dengan node penuh dari blockchain target (target permintaan RPC). HyperNode adalah peran pertama yang terdesentralisasi dalam jaringan BlockPI. Mulai dari tahap fase testnet #1, operator pihak ketiga dapat bergabung dan menjalankan HyperNode. 

### Official Link

- [Panduan Instalasi Klaytn Endpoint Node](https://testnet-docs.blockpi.io/guide-for-operators/target-rpc-node/klaytn-endpoint-node-installation)

- [Panduan Instalasi  Polygon Endpoint Node](https://testnet-docs.blockpi.io/guide-for-operators/target-rpc-node/polygon-endpoint-node-installation)

### 1. Spesifikasi Hardware 

- Ubuntu 20.04 

- CPU: 6 cores
 
- RAM: 32GB
    
- 4TB+ SSD

### 2. Instalasi Manual
Jalankan 1/1 perintah dibawah ini untuk instalasi ken

```
version=v1.9.1
wget https://packages.klaytn.net/klaytn/$version/ken-$version-0-linux-amd64.tar.gz
tar zxf ken-$version-0-linux-amd64.tar.gz
mv ken-linux-amd64/bin/ken /usr/local/bin/ken
rm -rf ken-linux-amd64 ken-$version-0-linux-amd64.tar.gz
ken version
``` 
Download snapshot klaytn
> proses ini bisa memakan waktu yang lama (5-10 Jam) tergantung dengan kecepatan koneksi  internet VM kalian. 

```
mkdir -p ~/node/full/klaytn/
wget https://s3.ap-northeast-2.amazonaws.com/klaytn-chaindata/cypress/klaytn-cypress-chaindata-20220823010812.tar.gz
``` 
Setelah download selesai, lakukan ekstrak dokumen di folder **`/node/full/klaytn/`**
> Untuk mempercepat proses unzipping gunakan tools **`pigz`**  dan untuk monitoring proses unzip bisa menggunakan **`pv`**

```
sudo apt install pigz 
sudo apt install pv
pigz -dc klaytn-cypress-chaindata-20220823010812.tar.gz | pv | tar xf -
``` 
Jalankan Hypernode dengan systemd

```
cat > /etc/systemd/system/klaytn.service << EOF
[Unit]
Description=daemon
After=network-online.target

[Service]
User=root
ExecStart=/usr/local/bin/ken --cypress --datadir /node/full/klaytn/ --syncmode full --gcmode full --multichannel --srvtype fasthttp --txpool.exec-slots.all 4096 --txpool.nonexec-slots.all 4096 --txpool.exec-slots.account 4096 --txpool.nonexec-slots.account 4096 --rpc --rpcaddr "localhost" --rpc.concurrencylimit 60000 --rpcapi "debug,klay,eth,personal,rpc,txpool,web3,net" --rpccorsdomain "*" --rpcvhosts "*" --ws --wsaddr "localhost" --wsapi "klay,eth,personal,rpc,txpool,web3" --wsorigins all --metrics --prometheus --port 31270 --rpcport 31271 --wsport 31272 --subport 31274 --prometheusport 31275
Restart=on-failure
RestartSec=5

[Install]
WantedBy=multi-user.target
EOF
``` 
Aktifkan otomatisasi perintah ketika OS dinyalakan dan mulai layanan klaytn
```
sudo systemctl daemon-reload
sudo systemctl enable klaytn
sudo systemctl start klaytn
```

Untuk mengecek log bisa menggunakan perintah dibawah ini
```
journalctl -u klaytn.service -f
```
Cek status Klaytn, jika sudah `false` berarti chain sudah sync/terhubung

```
curl --data '{"method":"eth_syncing","params":[],"id":1,"jsonrpc":"2.0"}' -H "Content-Type: application/json" -X POST http://127.0.0.1:31271/
``` 
Setelah chain sukses terhubung saatnya masuk ke proses instalasi Klaytn HyperNode
> Jalankan perintah dibawah ini 1/1

```
mkdir ~/HyperNodeKlaytn
cd ~/HyperNodeKlaytn
version=`wget -qO- -t1 -T2 "https://api.github.com/repos/BlockPILabs/testnets/releases/latest" | grep "tag_name" | head -n 1 | awk -F ":" '{print $2}' | sed 's/\"//g;s/,//g;s/ //g'`
wget https://github.com/BlockPILabs/testnets/releases/download/${version}/HyperNode
wget https://github.com/BlockPILabs/testnets/releases/download/${version}/config.yml
chmod +x ./HyperNode
mv ./HyperNode /usr/local/bin/
``` 
Inisialisasi Node
> Lakukan inisialisasi Node dan setup password! ingat jangan lupa passwordnya ya, jika lupa password`key` yang di generate nantinya tidak dapat di decrypt.

```
HyperNode init
``` 
> **Perlu diingat!! simpan `public address`, `secret key` dan `password.txt` di tempat yang aman!**

Buat file passwd.txt dan atur {passwd} sesuai password yang di input sebelumnya.

```
echo '{passwd}' > ~/HyperNodeKlaytn/passwd.txt
``` 
Selanjutnya, konfigurasi `config.yml` 

```
api:
    listen: :8899
beacon:
    - 15.235.11.42:9090
chain:
    name: klaytn
    network: "8217"
checksignature: true
fee:
    baseurl: https://raw.githubusercontent.com/BlockPILabs/FeeConfig
    tag: main
gws:
    - 0x7C7E6404C636c7721Fb748fC36395F1af5bF707b
hub:
    pkey: 0xe8e11b380e252e56dfb6b408265c9071ea9bb13f
log:
    app:
        cout: true
        level: error
    bclient:
        cout: true
        level: error
    challenge:
        cout: true
        level: error
    rpc:
        cout: true
        level: error
    slb:
        cout: true
        level: error
logger:
    maxage: "1"
    rotationtime: "1"
name: "MONIKER"       >> Ubah `MONIKER` dengan nama node kalian
node:
    addr: http://127.0.0.1:31271
provider: "ERC-20 ADDRESS"    >> Ubah `ERC-20 ADDRESS` dengan alamat publik address kalian
rpc:
    addr: 0.0.0.0:8060
    grpc: 0.0.0.0:8090
    istlsenabled: false
logger:
    maxage: "2"
    rotationtime: "1"
snapshot:
    packedttl: "1"
    path: ./snapshot
``` 
Jalankan HyperNode dengan **systemd**
> jika ingin merubah nama key dari yang sebelumnya UTC-xxxx menjadi `key` bisa menggunakan command `mv` contoh `mv UTC-xxx key`

```
[Unit]
Description=daemon
After=network-online.target

[Service]
User=root
WorkingDirectory=/root/HyperNodeKlaytn
ExecStart=/usr/local/bin/HyperNode --datadir /root/HyperNodeKlaytn --keystore_path keystore/key --password_path passwd.txt
LimitNOFILE=200000

[Install]
WantedBy=multi-user.target
``` 
Aktifkan otomatisasi perintah ketika OS dinyalakan dan mulai HyperNode!
```
sudo systemctl enable HyperNodeKlaytn
sudo systemctl start HyperNodeKlaytn
```

Untuk mengecek log bisa menggunakan perintah dibawah ini

```
journalctl -u HyperNodeKlaytn.service -f
```

Selamat!! Instalasi telah selesai, jika kalian mengikuti dengan seksama seharusnya node kalian sudah aktif sekarang, untuk mengecek kalian bisa mengunjungi link dibawah ini [https://testnet.explorer.blockpi.io/](https://testnet.explorer.blockpi.io/)


> ### Regards : NodeX | WannaCry? 🔥











