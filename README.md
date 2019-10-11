# Recipes
Various recipes for things

## OpenVPN server

This is the configuration that is running with client visibility between
linux, windows and android

	apt-get install openvpn
	cd /etc/openvpn
	mkdir clients
	make-cadir easy-rsa
	cd easy-rsa
	ln -s openssl-1.0.0.cnf openssl.cnf

Edit vars file, set KEY_COUNTRY, etc

	. vars
	./clean-all
	./build-ca
	./build-key-server server
	./build-dh
	./build-key client

Copy openvpn/server.conf file into /etc/openvpn

