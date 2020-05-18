FROM ubuntu
MAINTAINER moufida
ARG DEBIAN_FRONTEND=noninteractive
ENV DEBIAN_FRONTEND=noninteractive
ENV sudo date --set="1971-01-02 23:31:59.990"  && date --rfc-3339=ns
ENV TZ=Europe/Paris
RUN apt-get update \
    && apt-get install -y nginx git
RUN rm -Rf /var/www/html/*
RUN git clone https://github.com/diranetafen/static-website-example.git /var/www/html/ \ 
    && sed -i 's/80 default_server/8080 default_server/g' /etc/nginx/sites-enabled/default 
EXPOSE 8080
ENTRYPOINT ["/usr/sbin/nginx","-g","daemon off;"]
