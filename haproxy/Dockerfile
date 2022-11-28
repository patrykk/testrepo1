FROM haproxy:latest
USER root
RUN mkdir -p /etc/ssl
COPY --chown=haproxy:haproxy cert/ /etc/ssl 
USER haproxy
USER haproxy
COPY --chown=haproxy:haproxy haproxy.cfg /usr/local/etc/haproxy/haproxy.cfg
