# DNS- LINUX
---------------------
## Primero tendremos que instalar el bind9 en nuestra máquina virtual
`sudo apt install bind9`

---------------------
 ## Ahora configuraremos nuestros archivos primero named.conf
- `include "/etc/bind/named.conf.options";`
- `include "/etc/bind/named.conf.local";`
- `include "/etc/bind/named.conf.default-zones"`

---------------------

## Ahora configuraremos named.conf.default-zones
// prime the server with knowledge of the root servers
- `zone "." {
	type hint;
	file "/usr/share/dns/root.hints";
};``

// be authoritative for the localhost forward and reverse zones, and for
// broadcast zones as per RFC 1912

- `zone "localhost" {
	type master;
	file "/etc/bind/db.local";
};``

- `zone "127.in-addr.arpa" {
	type master;
	file "/etc/bind/db.127";
};``

- `zone "0.in-addr.arpa" {
	type master;
	file "/etc/bind/db.0";
};``

- `zone "255.in-addr.arpa" {
	type master;
	file "/etc/bind/db.255";
};``
