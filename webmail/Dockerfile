FROM debian:buster

RUN apt-get update \
    && apt-get install -y \
    apache2 apache2-utils libapache2-mod-php \
    php php-cli php-curl php-xml php-imap \
    nano 

RUN apt-get upgrade -y

COPY email1.sh .
COPY email2.sh .
#RUN ./email2.sh

CMD tail -F /dev/null