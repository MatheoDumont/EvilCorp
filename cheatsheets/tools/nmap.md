# NMAP

NMAP pour Network Mapper.
Scanner sur une/des machines les ports ouverts et les services associés.  
  
## Commandes
  
| Commandes | Description |
|---	|---	|
|```nmap -s[scan type] @ip``` | Ce pattern est présent pour à peu près toutes les commandes nmap : <br>un type de scan *scan type* sur une *@ip*. |
|```sudo nmap -O @ip ``` | Scan pour découvrir l'os de la machine *@ip*. |
|```sudo nmap -sS @ip``` 	|  [TCP Sync Scan](https://nmap.org/book/synscan.html) : <br> Commence un TCP handshake mais l'interrompt avec un RST. <br> Scan peu intrusif.|
|```sudo nmap -sV @ip``` | Pour découvrir versions des services. |
|```sudo nmap -sn @iprange``` | Découvre les interfaces ouvertes sur les réseaux spécifiés avec *@iprange* de la forme ```x.y.z.w/[0-32]``` ou ```x.y.z.w - a.b.c.d```, équivalent à *netdiscover*. |
|```sudo nmap -p [x-y] @ip``` | Scan les compris dans ```[x, y]``` sur *@ip*. |
|```nmap -F @ip``` | Découvre les 100 port les plus utilisés sur *@ip*. |
|```sudo nmap -A @ip ```| *A* pour aggressive, scan plus complet, avec scan d'os, version scan et autre.|
|```sudo nmap -s [0-9] ... ```| ```--version-intensity```, default=7, Intensité de scan. |

## Nmap et Firewall , IDS




