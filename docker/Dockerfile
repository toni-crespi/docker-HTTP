# Utilitzem la imatge base d'Ubuntu
FROM ubuntu:22.04

# Evitem preguntes durant la instal·lació (Timezone, etc.)
ENV DEBIAN_FRONTEND=noninteractive

# Actualitzem i instal·lem Apache
RUN apt-get update && \
    apt-get install -y apache2 && \
    apt-get clean

# Activem el mòdul necessari (opcional però recomanat)
RUN a2enmod rewrite

# Exposar el port 80
EXPOSE 80

# Comanda per arrencar Apache en primer pla (foreground)
# Si no ho fem així, el contenidor s'atura immediatament
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
