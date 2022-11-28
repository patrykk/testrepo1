FROM nginx:latest

EXPOSE 80
EXPOSE 443
EXPOSE 9999

WORKDIR /root
#add application to the image - not use persistant volume
COPY ./app/index.html /usr/share/nginx/html/index.html

COPY ./nginx/nginx.conf /etc/nginx/conf.d/nginx.conf

ADD cert/ /etc/nginx/certs/

ENTRYPOINT ["/docker-entrypoint.sh"]
CMD ["nginx", "-g", "daemon off;"]
