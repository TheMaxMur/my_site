FROM nginx:1.23.2-alpine

COPY ./files/data/nginx/default.conf /etc/nginx/conf.d/default.conf
COPY ./files/data/nginx/nginx.conf /etc/nginx/nginx.conf
COPY ./files/data/certbot/options-ssl-nginx.conf /etc/nginx/options-ssl-nginx.conf
COPY ./maxmur /app

RUN chown -R nginx:nginx /var/cache/nginx && \
    chown -R nginx:nginx /var/log/nginx && \
    chown -R nginx:nginx /etc/nginx/

USER nginx

EXPOSE 80/tcp

CMD ["/usr/sbin/nginx", "-g", "daemon off;"]
