#wird von Docker Hub heruntergeladen
FROM httpd

#Apache wird installiert
RUN apt-get update \
   && apt-get install -y apache2

#das index.html wird an die entsprechende stelle kopiert
COPY index.html /var/www/html/
WORKDIR /var/www/html
CMD ["apachectl", "-D", "FOREGROUND"]

#der Port 80 wird dafür bereitgestellt
EXPOSE 80