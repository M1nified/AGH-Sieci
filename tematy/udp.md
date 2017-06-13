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
| 160 |	Dane
 
