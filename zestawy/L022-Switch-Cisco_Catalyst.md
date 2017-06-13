# Switch Cisco Catalyst

>Tematyka:  
>Konfigurowanie przełączników nie rutujących Cisco Catalyst segmentu EDGE: konfigurowanie usług przełączników, Spanning Tree Protocol, EtherChannel

## Wprowadzenie i interfejsy

```shell
Switch# configure terminal
Switch(config)# 

Switch(config)# interface vlan1
Switch (config-if)# ip address 192.168.123.199 255.255.255.0
Switch (config-if)# no shutdown

Switch# show ip interface brief
Switch# show ip interface vlan 1

Switch(config)# do show ip interface brief
Switch(config)# do show ip interface vlan 1
```

## Telnet

- Port: 23
- Terminale virtulane `VTY`, najczęściej jest ich 16.

```shell
Switch(config)# line vty 0 15
Switch(config-line)# password haslo
Switch(config-line)# login
Switch(config-line)# transport input telnet
```
> Gdzie kolejne wpisy to:
> - Aktywowanie trybu konfiguracji linii (zakres 0-15)
> - Ustanowienie lokalnego hasła
> - Ustanowienie nakazu uŜywania lokalnego hasła przy logowaniu
> - Zezwolenie na ruch telnet z wykorzystaniem wybranych linii

Usuwanie:

```shell
Switch#show run
…
aaa new-model
…
Switch(config)#no aaa new-model
```

### Hasło

CLI (exec) wymaga hasla jesli laczymy sie przez telnet/ssh.

```shell
Switch(config)# enable password haslo
Switch(config)# no enable password
Switch# show running-config
```

## SSH

- Port: 22

```shell
Switch(config)# ip domain-name domena
Switch(config)# hostname Mojhost
Mojhost#

Switch(config)# crypto key generate rsa
// Następnie podaj wielkość klucza (360-2048 bitów)
Switch# show ip ssh
```

Przełącz tryb autoryzacji uŜytkowników z opcji "serwera AAA radius" (co jest
domyślne) na wykorzystanie lokalne systemu kont:

```shell
Switch(config)# aaa new-model
Uwaga: powyŜsza komenda uniemoŜliwia uŜycie komendy:
Switch(config-line)# login
// niemożliwa jest już autoryzacja przy pomocy hasła przypisanego do linii
```

Definiowanie użytkowników z loginem i hasłem
```shell
Switch(config)# username nazwa priv 15 password 0 haslo
```
> Gdzie kod 0 oznacza hasło zadane jawnie tekstem (wartość 7 oznaczałaby hasło szyfrowane), zaś 15 to wartość priorytetu przypisanego temu uŜytkownikowi (najwyŜszy).

Włączanie użytkowania SSH:

```shell
Switch(config)#line vty 0 15
Switch(config-line)#transport input ssh
```
Blokowanie nieszyfrowanego telnet:

```shell
Switch(config)#line vty 0 15
Switch(config-line)#no transport input telnet
// lub (w niektórych wersjach CatOS):
Switch(config-line)#transport input none
Switch(config-line)#transport input ssh
```
