FROM alpine:latest

RUN apk add --no-cache nginx

RUN adduser -S -D -H -G nginx nginx || true

RUN mkdir -p /var/www/html /var/log/nginx /var/lib/nginx /var/lib/nginx/tmp /run/nginx \
    && chown -R nginx:nginx /var/www/html /var/log/nginx /var/lib/nginx /etc/nginx /run/nginx

COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 8080

USER nginx

CMD ["nginx", "-g", "daemon off;"]