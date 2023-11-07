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
	};``


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

--------------------
## Y ahora crearemos una zona que se llamará db.asircastelao.int
`$TTL 38400	; 10 hours 40 minutes
@		IN SOA	ns.asircastelao.int. some.email.address. (
				17161016   ; serial
				10800      ; refresh (3 hours)
				3600       ; retry (1 hour)
				604800     ; expire (1 week)
				38400      ; minimum (10 hours 40 minutes)
				)
@		IN NS	ns.asircastelao.int.
ns		IN A 	172.28.5.1
test	IN A	172.28.5.4
wwww    IN A    172.28.5.7
alias	IN CNAME  test
texto   IN TXT 	mensaje
`
-------------------


