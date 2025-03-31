FROM alpine:3.21.3

RUN apk add --no-cache nginx

RUN adduser -S -D -H -G user user || true

RUN mkdir -p /var/www/html /var/log/nginx /var/lib/nginx /var/lib/nginx/tmp /run/nginx \
    && chown -R user:user /var/www/html /var/log/nginx /var/lib/nginx /etc/nginx /run/nginx

COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 8080

USER user

CMD ["nginx", "-g", "daemon off;"]