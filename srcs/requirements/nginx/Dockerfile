FROM	debian:buster

RUN		apt-get update

RUN		apt-get -y install nginx

RUN		apt-get -y install openssl

RUN mkdir /etc/nginx/ssl/

RUN openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout /etc/nginx/ssl/server.key -out /etc/nginx/ssl/server.csr -subj "/C=FR/ST=IDF/L=Paris/O=42School/CN=lmasson/"

COPY 

CMD ["nginx", "-g", "daemon off;"]
