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

## DHCP

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
