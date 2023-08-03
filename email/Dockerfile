#Dockerfile para SMTP e IMAP
FROM debian:latest

WORKDIR /app

RUN apt-get update \
    && apt-get install -y \
    postfix \
    dovecot-core \
    dovecot-imapd \
    iputils-ping \
    net-tools \
    telnet \
    nano

RUN apt-get upgrade -y

COPY ./imap/10-auth.conf /etc/dovecot/conf.d/10-auth.conf
COPY ./imap/10-mail.conf /etc/dovecot/conf.d/10-mail.conf
COPY ./imap/10-master.conf /etc/dovecot/conf.d/10-master.conf
COPY ./imap/dovecot.conf /etc/dovecot/dovecot.conf

COPY ./smtp/main.cf /etc/postfix/main.cf

COPY email.sh .
#RUN chmod +x email.sh
#RUN /app/email.sh

COPY ex.sh .
#RUN chmod +x ex.sh
#RUN /app/ex.sh

EXPOSE 25 110 143 993 995

CMD tail -F /dev/null