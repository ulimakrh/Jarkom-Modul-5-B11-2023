# Jarkom-Modul-5-B11-2023

| No | Nama | NRP |
| -------- | -------- | -------- |
| 1 | Muhammad Rafif Tri Risqullah | 5025211009 |
| 2 | Ulima Kaltsum Rizky Hibatullah | 5025211232 |

## Topologi
![image](https://github.com/ulimakrh/Jarkom-Modul-5-B11-2023/assets/114993076/c10f1b51-521c-440a-a861-60da05ba1a47)

## Rute
![WhatsApp Image 2023-12-20 at 20 23 20_ea2481ca](https://github.com/ulimakrh/Jarkom-Modul-5-B11-2023/assets/114993076/63ae22ec-cd33-482e-93b9-69f2b64d6b96)
![image](https://github.com/ulimakrh/Jarkom-Modul-5-B11-2023/assets/114993076/dcc47286-c1f4-4aa7-82c4-7675b20bd66f)
![image](https://github.com/ulimakrh/Jarkom-Modul-5-B11-2023/assets/114993076/84be8c0b-5edc-406e-9dbc-58a81058bd04)

## Subnetting
#### Aura
```
auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
	address 10.14.0.1
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.14.0.5
	netmask 255.255.255.252
```
#### Hieter
```
auto eth0
iface eth0 inet static
	address 10.14.0.2
	netmask 255.255.255.252
        up echo nameserver 192.168.122.1 > /etc/resolv.conf

auto eth1
iface eth1 inet static
	address 10.14.8.1
	netmask 255.255.248.0

auto eth2
iface eth2 inet static
	address 10.14.4.1
	netmask 255.255.252.0
```
#### Sein
```
auto eth0
iface eth0 inet static
	address 10.14.4.2
        gateway 10.14.4.1
	netmask 255.255.252.0
        up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
#### Frieren
```auto eth0
iface eth0 inet static
	address 10.14.0.6
	netmask 255.255.255.252

auto eth1
iface eth1 inet static
	address 10.14.0.9
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.14.0.13
	netmask 255.255.255.252
```
#### Stark
```auto eth0
iface eth0 inet static
	address 10.14.0.10
        gateway 10.14.0.9
	netmask 255.255.255.252
        up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
#### Himmel
```
auto eth0
iface eth0 inet static
	address 10.14.0.14
	netmask 255.255.255.252
        up echo nameserver 192.168.122.1 > /etc/resolv.conf

auto eth1
iface eth1 inet static
	address 10.14.2.1
	netmask 255.255.254.0

auto eth2
iface eth2 inet static
	address 10.14.0.129
	netmask 255.255.255.128
```
#### Fern
```
auto eth0
iface eth0 inet static
	address 10.14.0.130
	netmask 255.255.255.128

auto eth1
iface eth1 inet static
	address 10.14.0.17
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.14.0.21
	netmask 255.255.255.252
```
#### Richter
```
auto eth0
iface eth0 inet static
	address 10.14.0.18
        gateway 10.14.0.17
	netmask 255.255.255.252
        up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
#### Revolte
```
auto eth0
iface eth0 inet static
	address 10.14.0.22
        gateway 10.14.0.21
	netmask 255.255.255.252
        up echo nameserver 192.168.122.1 > /etc/resolv.conf
```
#### Client (GrobeForest, TurkRegion, LaubHills, SchwerMountains)
```
auto eth0
iface eth0 inet dhcp
```
## Routing
#### Aura
```
# Routing Ke Frieren
# route add -net <NID subnet> netmask <netmask> gw <IP gateway>
# A5
route add -net 10.14.0.8 netmask 255.255.255.252 gw 10.14.0.6
# A6
route add -net 10.14.0.12 netmask 255.255.255.252 gw 10.14.0.6
# A7
route add -net 10.14.2.0 netmask 255.255.254.0 gw 10.14.0.6
# A8
route add -net 10.14.0.128 netmask 255.255.255.128 gw 10.14.0.6
# A9
route add -net 10.14.0.16 netmask 255.255.255.252 gw 10.14.0.6
# A10
route add -net 10.14.0.20 netmask 255.255.255.252 gw 10.14.0.6


# Routing ke Heiter
# A2
route add -net 10.14.8.0 netmask 255.255.248.0 gw 10.14.0.2
# A3
route add -net 10.14.4.0 netmask 255.255.252.0 gw 10.14.0.2

```
#### Fern
```
# Backrouting
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.14.0.129
```
#### Frieren
```
# Ke Himmel
# Backrouting
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.14.0.5
# A7
route add -net 10.14.2.0 netmask 255.255.254.0 gw 10.14.0.14
# A8
route add -net 10.14.0.128 netmask 255.255.255.128 gw 10.14.0.14
# A9
route add -net 10.14.0.16 netmask 255.255.255.252 gw 10.14.0.14
# A10
route add -net 10.14.0.20 netmask 255.255.255.252 gw 10.14.0.14
```
#### Heiter
```
# Backrouting
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.14.0.1
```
#### Himmel
```
# Backrouting
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.14.0.13
# A9
route add -net 10.14.0.16 netmask 255.255.255.252 gw 10.14.0.130
# A10
route add -net 10.14.0.20 netmask 255.255.255.252 gw 10.14.0.130
```
#### Test Routing menggunakan PING
![image](https://github.com/ulimakrh/Jarkom-Modul-5-B11-2023/assets/114993076/3a226389-fb19-40f1-8238-e800293ad8eb)

## DHCP
#### Konfigurasi DHCP Server (Revolte)
```

apt-get update -y

apt-get install isc-dhcp-server -y

echo "
INTERFACES=\"eth0\"
" > /etc/default/isc-dhcp-server

echo "

default-lease-time 28800;
max-lease-time 57600;

ddns-update-style none;


subnet 10.14.0.20 netmask 255.255.255.252 {
    option routers 10.14.0.21;
    option broadcast-address 10.14.0.23;
    option domain-name-servers 192.168.122.1;
}

# Turk Region
subnet 10.14.8.0 netmask 255.255.248.0 {
    range 10.14.8.0 10.14.15.254;
    option routers 10.14.8.1;
    option broadcast-address 10.14.15.255;
    option domain-name-servers 192.168.122.1;
}

# Grobe Forest
subnet 10.14.4.0 netmask 255.255.252.0 {
    range 10.14.4.1 10.14.7.254;
    option routers 10.14.4.1;
    option broadcast-address 10.14.7.255;
    option domain-name-servers 192.168.122.1;
}

# LaubHilss
subnet 10.14.2.0 netmask 255.255.254.0 {
    range 10.14.2.0 10.14.3.254;
    option routers 10.14.2.1;
    option broadcast-address 10.14.3.255;
    option domain-name-servers 192.168.122.1;
}

# SchwerMountain
subnet 10.14.0.128 netmask 255.255.255.128 {
    range 10.14.0.129 10.14.0.254;
    option routers 10.14.0.129;
    option broadcast-address 10.14.0.255;
    option domain-name-servers 192.168.122.1;
}

" > /etc/dhcp/dhcpd.conf

rm /var/run/dhcpd.pid

service isc-dhcp-server restart
service isc-dhcp-server status
```
#### Konfigurasi DHCP Relay (Himmel & Heiter)
```

apt-get update

apt-get install isc-dhcp-relay -y

echo '
SERVERS="10.14.0.22"
INTERFACES="eth0 eth1 eth2"
OPTIONS=""
' > /etc/default/isc-dhcp-relay

echo '
net.ipv4.ip_forward=1
' > /etc/sysctl.conf

service isc-dhcp-relay restart
```

## Soal 1
`Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi Aura menggunakan iptables, tetapi tidak ingin menggunakan MASQUERADE.`
Lakukan command berikut pada Aura untuk mengganti IP dari source packet yang akan keluar melalui interface eth0 Aura menuju keluar NAT. `command $(/sbin/ip -4 a show eth0 | /bin/grep -Po 'inet \K[0-9.]*')` digunakan untuk mendapatkan IP eth0 dari router Aura.

```
iptables -t nat -A POSTROUTING -o eth0 -j SNAT --to-source $(/sbin/ip -4 a show eth0 | /bin/grep -Po 'inet \K[0-9.]*')
```
Test PING google.com

![image](https://github.com/ulimakrh/Jarkom-Modul-5-B11-2023/assets/114993076/bf738ca7-0314-4501-a193-8db6dff65af5)

## Soal 2
`Kalian diminta untuk melakukan drop semua TCP dan UDP kecuali port 8080 pada TCP.`
Konfigurasi tambahan pada Client
```
iptables -F
iptables -A INPUT -p tcp --dport 8080 -j ACCEPT
iptables -A INPUT -p tcp -j DROP
iptables -A INPUT -p udp -j DROP
```

## Soal 3
`Kepala Suku North Area meminta kalian untuk membatasi DHCP dan DNS Server hanya dapat dilakukan ping oleh maksimal 3 device secara bersamaan, selebihnya akan di drop.`
Konfigurasi tambahan pada DHCP Server dan DNS Server sehingga hanya akan bisa melakukan PING tiap detiknya oleh maksimal 3 node.
```
iptables -F
iptables -A INPUT -p icmp --icmp-type echo-request -m limit --limit 3/second -j ACCEPT 
iptables -A INPUT -p icmp --icmp-type echo-request -j DROP
```

## Soal 4
`Lakukan pembatasan sehingga koneksi SSH pada Web Server hanya dapat dilakukan oleh masyarakat yang berada pada GrobeForest.`
Buat sebuah file .sh di kedua web server (Sein & Stark) yang akan menyimpan script untuk menambahkan iptables rules sebagai berikut:
```
iptables -A INPUT -p tcp --dport 22 -m iprange --src-range 10.14.4.1-10.14.7.254  -j ACCEPT
iptables -A OUTPUT -p tcp --sport 22 -m iprange --dst-range 10.14.4.1-10.14.7.254 -j ACCEPT
iptables -A INPUT -p tcp --dport 22 -j DROP
iptables -A OUTPUT -p tcp --sport 22 -j DROP
```
Pada baris ke-3 dan ke-4, dilakukan DROP terhadap semua request INPUT yang diarahkan ke port 22 (TCP) dan OUTPUT yang berasal dari port 22 (TCP), yaitu port default SSH.
Kemudian ditambahkan rules pada baris ke-1 dan ke-2 untuk menerima request serupa hanya bila range ip tujuan merupakan bagian dari subnet warga GrobeForest untuk INPUT dan range ip asal merupakan bagian dari subnet warga GrobeForest untuk OUTPUT.

## Soal 5
`Selain itu, akses menuju WebServer hanya diperbolehkan saat jam kerja yaitu Senin-Jumat pada pukul 08.00-16.00.`
Pada file .sh di kedua web server (Sein & Stark), tambahkan script untuk menambahkan iptables rules di atas script untuk nomor 4 seperti sebagai berikut:
```
iptables -A INPUT -m time --weekdays Sat,Sun -j DROP
iptables -A INPUT -p all -m time --timestart 16:00 --timestop 23:59:59 -j DROP
iptables -A INPUT -p all -m time --timestart 00:00 --timestop 08:00 -j DROP
```
Baris ke-2 dan ke-3 akan melakukan DROP terhadap semua request INPUT di luar dari range waktu yang diinginkan (08:00 - 16:00), yakni sebelum jam 8 pagi (00:00 - 08:00) dan sesudah jam 4 sore (16:00 - 23:59:59).
Baris ke-1 melakukan DROP terhadap semua request INPUT di luar hari kerja (Senin - Jumat), yakni pada hari Sabtu dan Minggu.

## Soal 6
`Lalu, karena ternyata terdapat beberapa waktu di mana network administrator dari WebServer tidak bisa stand by, sehingga perlu ditambahkan rule bahwa akses pada hari Senin - Kamis pada jam 12.00 - 13.00 dilarang (istirahat maksi cuy) dan akses di hari Jumat pada jam 11.00 - 13.00 juga dilarang (maklum, Jumatan rek).`
Tambahkan script di atas nomor sebelumnya untuk menambahkan iptables rules sebagai berikut:
```
iptables -A INPUT -m time --timestart 12:00 --timestop 13:00 --weekdays Mon,Tue,Wed,Thu -j DROP
iptables -A INPUT -m time --timestart 11:00 --timestop 13:00 --weekdays Fri -j DROP
```
Maka, baris ke-1 melakukan DROP terhadap semua request INPUT di hari Senin - Kamis pada jam makan siang (12:00 - 13:00) dan baris ke-2 melakukan DROP terhadap semua request INPUT di hari Jumat pada jam jumatan (11:00 - 13:00).
