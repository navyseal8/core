FROM nginx:1.14

LABEL com.bitwarden.product="bitwarden"

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        gosu \
&& rm -rf /var/lib/apt/lists/*

COPY nginx.conf /etc/nginx
COPY proxy.conf /etc/nginx
COPY mime.types /etc/nginx
COPY security-headers.conf /etc/nginx
COPY security-headers-ssl.conf /etc/nginx
COPY entrypoint.sh /
RUN chmod +x /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]
