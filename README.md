# DNS- LINUX
---------------------
## Primero tendremos que instalar el bind9 en nuestra máquina virtual
`sudo apt install bind9`

---------------------
 ## Cambiaremos la configuración de named.conf.local
`zone "asircastelao.int" {
	type master;
	file "/var/lib/bind/db.asircastelao.int";
	allow-query {
		any;
		};
	};
``
##
