# A - Podstawy konfigurowania Cisco IOS

## Bootowanie

### Karetka `rommon`

Uruchomienie systemu z pierwszego dostępnego obrazu w pamięci FLASH, polecenie:

```shell
rommon> reset
```

z innego obrazu:

```shell
dir flash:
boot flash:/plik_obrazu_IOS.bin
boot disk0:/plik_obrazu_IOS.bin
boot slot0:/plik_obrazu_IOS.bin
boot usb:/plik_obrazu_IOS.bin
```

gdzie `slot0` lub `disk0` to gniazda kart pamięci (jeśli są obecne w ruterze)

- `slot0` - linear FLASH
- `disk0` - ATA FLASH z FAT

### Karetka `CLI`

Przejście to trybu uprzywilejowanego `exec`

```shell
Router> enable
Router#
```

Przejście do trybu konfiguracji

```shell
Router# configure terminal
Router(config)#
```
