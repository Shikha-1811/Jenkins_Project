From ubuntu:latest
LABEL author="Shikha" project="Dockerized Static Website"
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && \
    apt-get install apache2 unzip -y && \
    apt-get clean

WORKDIR /var/www/html

#Copy and extract website
ADD aqua-nova.tar.gz /var/www/html/

# Expose port 80
EXPOSE 80

#Start apaceh2
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]


