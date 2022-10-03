FROM ubuntu:20.04

USER root 

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt install curl -y && apt install telnet -y &&  apt install apache2 -y

EXPOSE 80

WORKDIR /var/www/html/

COPY . .

ENTRYPOINT ["apache2ctl"]

CMD ["-DFOREGROUND"]


