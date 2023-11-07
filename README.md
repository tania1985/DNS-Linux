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
`

----------------------
## Ahora cambiaremos named.conf.options 
`options {
	directory "/var/cache/bind";

	forwarders {
	 	8.8.8.8;
		1.1.1.1;
	 };
	 forward only;

	listen-on { any; };
	listen-on-v6 { any; };

	allow-query {
		any;
	};
};`
