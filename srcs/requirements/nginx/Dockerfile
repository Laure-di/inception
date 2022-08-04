FROM	debian:buster

RUN		sudo apt-get update

RUN		sudo apt-get -y install nginx
# https://ubuntu.com/tutorials/install-and-configure-nginx#2-installing-nginx

RUN		sudo apt-geti -y instal openssl
# https://installati.one/debian/10/openssl/
# https://manpages.ubuntu.com/manpages/trusty/en/man8/apt-get.8.html
# https://fr.wikipedia.org/wiki/OpenSSL

#Create Certificate Signing Request (CSR) with openssl
# https://www.thesslstore.com/knowledgebase/ssl-generate/csr-generation-guide-for-nginx-openssl
# https://www.openssl.org/docs/man1.0.2/man1/openssl-req.html
############ FlAGS ###############
# new :  this option generates a new certificate request. It will prompt the user for the releva#		nt field values. The actual fields prompted for and their maximum and minimum sizes are	#		specified in the configuration file and any requested extensions. If the -key option is	#		not used it will generate a new RSA private key using information specified in the confi#		guration file.
# newkey arg : this option creates a new certificate request and a new private key. The argument#			takes one of several forms. rsa:nbits, where nbits is the number of bits, generates #			an RSA key nbits in size. If nbits is omitted, i.e. -newkey rsa specified, the defau#			lt key size, specified in the configuration file is used. All other algorithms suppo#			rt the -newkey alg:file form, where file may be an algorithm parameter file, created#			by the genpkey -genparam command or and X.509 certificate for a key with approriate##			algorithm. param:file generates a key using the parameter file or certificate file,##			the algorithm is determined by the parameters. algname:file use algorithm algname a##			nd parameter file file: the two algorithms must match or an error occurs. algname ju#			st uses algorithm algname, and parameters, if neccessary should be specified via -pk#			eyopt parameter. dsa:filename generates a DSA key using the parameters in the file f#			ilename. ec:filename generates EC key (usable both with ECDSA or ECDH algorithms), g#			ost2001:filename generates GOST R 34.10-2001 key (requires ccgost engine configured #			in the configuration file). If just gost2001 is specified a parameter set should be #			specified by -pkeyopt paramset:X
#
# nodes : if this option is specified then if a private key is created it will not be encrypted.
#
# keyout filename :  this gives the filename to write the newly created private key to. If this	#					option is not specified then the filename present in the configuration file #					is used.
# out filename : This specifies the output filename to write to or standard output by default.
# https://www.digicert.com/kb/ssl-support/openssl-quick-reference-guide.html
# https://medium.com/@munteanu210/how-to-install-an-ssl-certificate-on-nginx-b1dd39a4628d
################################
RUN openssl req -new -newkey rsa:2048 -nodes -keyout server.key -out server.csr

CMD ["nginx"]
