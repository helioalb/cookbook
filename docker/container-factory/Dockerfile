FROM ubuntu

RUN apt-get update && apt-get install -y apache2

ADD mysite/ /var/www/html

COPY mysite/ /var/www/html/mysite

EXPOSE 80

CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
