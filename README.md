# DNS- LINUX
---------------------
## Primero tendremos que instalar el bind9 en nuestra máquina virtual
`sudo apt install bind9`

---------------------
 ## Ahora configuraremos nuestros archivos primero named.conf
- `include "/etc/bind/named.conf.options";`
- `include "/etc/bind/named.conf.local";`
- `include "/etc/bind/named.conf.default-zones"`



