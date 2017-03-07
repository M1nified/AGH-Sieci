# Terminal access server

## Łączenie

- Wpięcie się do sieci laboratoryjnej
- Połączenie przez telnet z terminal access serverem (ip na żółto) na odpwiednim porcie:
    - JetStream	- port = numer gniazda
    - CISCO 	- port = 2000 + numer gniazda
## Port zablokowany
Jeśli port terminal access servera, z którym chcemy się połączyć jest zablokowany łączymy się telnetem na porcie 23 i killujemy zajętą linię.

```shell
kill line <numer gniazda>
```

Alternatywnie dla JetStream jest dostępny interfejs www.

# Ogólnie

## Interfejs VLAN
- Domyślnie gniazda są przypisane do VLAN1.

# Polecenia

- `enable`
- `ping`
- `show ip interface brief`
- `show ip interface vlan 1`
- `show vlan`
- `configure terminal`

## Tryb konfiguracji Switch(conf)

- `do <polecenie>`   
    `Switch(config)# do show ip interface brief`
- `interface vlan<numer>`   
- `ip address <adres interfejsu> <maska>`
- `[no ]shutdown`
- `interface fa|gig <identyfikator portu>`   
    `interface fa 0|1/<numer portu fast ethernet>`   
    `interface gig 0|1/<numer portu gigabit ethernet>`   
    `interface fa 0/1`
    - `[no ]shutdown`
    - `switchport nonegotiation`
    - `switchport mode access`
    - `switchport acess vlan 20`

# Światłowody

## Jednowodowe

- żółte (lab)
- jedna wiązka światła

## Wielowodowe

- pomarańczowe (lab)
- wiązki światła pod różnym kątem, wiele jednocześnie, więc większa przepustowość

## Wtyczki

- lc
    - mniejsze

