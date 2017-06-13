# UDP

## Struktura nagłówka

| +	  | Bity 0 – 15	 | 16 – 31        |
| --- | ---          | ---            |
| 0	  | Port nadawcy |	Port odbiorcy |
| 32  |	Długość	Suma | kontrolna      |
| 64  | Dane                          |
 
## IPv4

| +   |	Bity 0 – 7 | 8 – 15 | 16 – 23 | 24 – 31 |
| --- | ---        | ---    | ---     | ---     |
| 0   |	Adres źródłowy
| 32  |	Adres docelowy
| 64  |	Zera	| Protokół |	Długość UDP
| 96  |	Port źródłowy	| | Port docelowy
| 128 |	Długość	| | Suma kontrolna
| 160 |	Dane |
 
## IPv6

| +   |	Bity 0 – 7 | 8 – 15 | 16 – 23 | 24 – 31 |
| --- | ---        | ---    | ---     | ---     |
| 0   |	Adres źródłowy
| 32  |
| 64  |
| 96  |
| 128 |	Adres docelowy
| 160 |
| 192 |
| 224 |
| 256 |	Długość UDP
| 288 |	Zera	| | | Następny nagłówek
| 320 |	Port źródłowy | | Port docelowy
| 352 |	Długość	| | Suma kontrolna
| 384 | Dane |