# Jarkom-Modul-5-B11-2023

| No | Nama | NRP |
| -------- | -------- | -------- |
| 1 | Muhammad Rafif Tri Risqullah | 5025211009 |
| 2 | Ulima Kaltsum Rizky Hibatullah | 5025211232 |

## Topologi
![image](https://github.com/ulimakrh/Jarkom-Modul-5-B11-2023/assets/114993076/c10f1b51-521c-440a-a861-60da05ba1a47)

## Rute

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
