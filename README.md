# Jobsheet-1.1

### 1.1WirelessSensorNet

#### I. Teori Dasar

ESP-NOW adalah protokol yang dikembangkan oleh Espressif, yang memungkinkan banyak perangkat untuk berkomunikasi satu sama lain tanpa menggunakan Wi-Fi. Protokol ini mirip dengan konektivitas nirkabel 2.4GHz berdaya rendah. Pendifinisian alamat (MAC Address) pada masing-masing ESP32 diperlukan pada awal konfigurasi. Setelah konfigurasi alamat selesai dilakukan, jaringan peer-to-peer akan terbentuk dan perangkat tidak perlu melakukan handshaking kembali ketika akan berkomunikasi. Hal ini memunjukkan bahwa setelah perangkat ESP32 saling terpasang satu sama lain, koneksi akan tetap ada. Dengan kata lain, jika tiba-tiba salah satu ESP32 kehilangan daya atau diatur ulang, ketika restart, secara otomatis akan terhubung ke pasangan ESP32 yang telah terdefinisi alamatnya untuk melanjutkan komunikasi.<br />
ESP-NOW mempunyai fitur sebagai berikut.<br />
  a) Komunikasi unicast yang terenkripsi maupun tidak terenkripsi. <br />
  b) Perpaduan komunikasi data yang terenkripsi maupun yang tidak terenkripsi pada perangkat yang berada pada topologi peer-to-peer. <br />
  c) Payload (ukuran) data yang dapat dikirm mencapai 250 byte.<br />
  d) Terdapat fungsi callback yang dapat menginformasikan data berhasil terkirim maupun gagal dikirim.<br />
Selain itu, ESP-NOW mempunyai batasan sebagai berikut.<br />
  a) Jumlah maksimal perangkat yang dapat berkomunikasi dalam mode station dengan data terenkripsi adalah 10 unit (6 dalam mode SoftAP atau SoftAP+Station). <br />
  b) Untuk komunikasi tidak terenkripsi, jumlah maksimal perangkat adalah 20 unit, termasuk dengan yang terenkripsi. <br />
ESP-NOW mempunyai 2 tipe jaringan, yaitu One-Way Communication dan Two-Way Communication. One-Way Communication terbagi menjadi Point-to-Point, One-to-Many Communication dan Many-to-One Communication. Sementara Two-Way Communication terbagi menjadi Point-to-Point dan Mesh Communication.

#### II. ALAT DAN BAHAN
1) ESP32
2) Breadboard
3) Kabel jumper
4) Resistor 10K Ohm

#### III. HASIL KELUARAN

**1) Memperoleh MAC Address ESP32 Receiver**
![1](https://user-images.githubusercontent.com/121251478/210923730-e9bb5a41-027b-4b43-8279-3a181e8a782a.png)

**2) ESP-NOW One-Way Point-to-Point Communication** <br />
`MAC Address Tx : 24:0A:C4:C6:06:54`
![2](https://user-images.githubusercontent.com/121251478/210923759-fa750ccd-2396-4e88-871e-44fc03829141.png)

![3](https://user-images.githubusercontent.com/121251478/210923799-3b44ff84-2493-47ef-8b04-28130c86cd99.png)

`MAC Address Rx : 30:AE:A4:7A:8F:B8`
![4](https://user-images.githubusercontent.com/121251478/210923812-164c82ab-ce84-453b-9678-39dff3a56642.png)

![5](https://user-images.githubusercontent.com/121251478/210923856-afb79a09-270b-497e-97c7-282993c2eb7e.png)

![6](https://user-images.githubusercontent.com/121251478/210923867-5de1496c-bed6-4e85-8553-1ebe7c13a3d7.png)

**3) ESP-NOW One-Way, One-to-Many Communication** <br />
Mengirim Pesan yang Sama Ke Beberapa Board ESP32 MAC Address yang digunakan: <br />
`MAC Sender : 3C:71:BF:F1:4B:08`  <br />
`MAC Reciver 1 : 24:6F:28:02:C3:1C` <br />
`MAC Receiver 2 : 24:0A:C4:C6:06:54` <br />
`MAC Receiver 3 : 30:AE:A4:7A:8F:B8` <br />
Pada Receiver 3, Hasilnya adalah sebagai berikut.
![7](https://user-images.githubusercontent.com/121251478/210923877-2ebe7cfb-27b6-4db7-ac11-8d6d466b5f18.png)

Pada Receiver 3 saat dimatikan board receiver, Hasilnya adalah sebagai berikut.
![8](https://user-images.githubusercontent.com/121251478/210923911-54db9750-b336-4c11-a93a-bc017ca03325.png)

**4) ESP-NOW One-Way, Many-to-One Communication ** <br />
MAC Address ESP32 yang digunakan :

`MAC Sender 1 : 24:0A:C4:C5:E2:DC`

`MAC Sender 2 : 24:0A:C4:C6:06:54`

`MAC Sender 3 : 24:0A:C4:C6:0E:7C`

`MAC Receiver  : 3C:71:BF:F1:42:70`

Dari Pihak Sender akan muncul seperti dibawah.
![9](https://user-images.githubusercontent.com/121251478/210924010-bdf1e4a2-2afa-42b3-a182-826043d1ba18.png)


Dari Pihak Receiver akan muncul seperti dibawah.
![10](https://user-images.githubusercontent.com/121251478/210924060-a550c944-a883-4af9-a5f6-4d5a5cae77ec.png)


**5) ESP-NOW Two-Way Communication** <br />
Rangkaian :
![11](https://user-images.githubusercontent.com/121251478/210924075-72012cbd-7df0-4594-8404-7ee9a3522def.png)

![12](https://user-images.githubusercontent.com/121251478/210924087-2e467d6d-2982-4f87-bdf6-c8240f79474e.png)


Tampilan Serial Monitor :
![13](https://user-images.githubusercontent.com/121251478/210924103-2ad8e28e-7360-4a26-a15b-72ccc61a92f8.png)
