FROM debian
RUN apt-get update && apt-get -y upgrade && apt -y install nginx && apt-get clean && \
    cd /var/www/ && rm -rf ./* && \
    mkdir -p rolagg.com/img && \
    chmod -R 754 /var/www/rolagg.com/ && \
    useradd Roman && groupadd Galitsyn && usermod -aG Galitsyn Roman && \
    chown -R Roman:Galitsyn /var/www/rolagg.com/ && \
    sed -i 's/\/var\/www\/html/\/var\/www\/rolagg.com/g' /etc/nginx/sites-enabled/default && \
    sed -i 's/user www-data/user Roman/g' /etc/nginx/nginx.conf
ADD index.html /var/www/rolagg.com/
ADD img.jpg /var/www/rolagg.com/img/
CMD ["nginx", "-g", "daemon off;"]