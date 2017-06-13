# Security Appliance - NOKIA CheckPoint IP350 / IP560

> Należy połączyć gniazdo konsoli i port RS232 stacji konfigurującej. W zależności od modelu urządzenia należy użyć kabla RJ45 Cisco Rollover lub DB9-DB9. Parametry połączenia konsoli: 9600 kbps, 8 bitów danych, brak kontroli parzystości, 1 bit stopu

- NOKIA IP 560: admin/administrator, admin/password
- NOKIA IP 350: admin/, admin/Cisco-123456

```shell
NokiaIP560[admin]#clish
NokiaIP560:11>
```

Wbudowany klient DHCP, ale mozna konfigurowac interfejs.

```shell
Nokia:11> add interface eth-s4p3c0 address 192.168.123.145/24
```
> gdzie eth-s4p3 oznacza trzecie gniazdo RJ45 w slocie numer 4

```shell
Nokia:11>add interface eth1c0 address 192.168.123.145/24
```
> gdzie eth1c0 oznacza pierwsze gniazdo RJ45 w chassis

- add
- set
- delete

```shell
NokiaIP560:11>set interface eth1c0 enable
NokiaIP560:11>show interfaces
NokiaIP560:11>exit
NokiaIP560[admin]#reboot
```