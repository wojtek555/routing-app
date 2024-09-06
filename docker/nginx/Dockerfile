#
# Nginx web server
#
# Supports brotli compression.
#

FROM fholzer/nginx-brotli:v1.26.2

HEALTHCHECK --interval=30s --timeout=10s --retries=3 CMD wget \
    --no-verbose --tries=1 --spider http://localhost:5555/status || exit 1

COPY docker/nginx/tools /tools
COPY docker/nginx/nginx.conf /etc/nginx/nginx.conf
COPY docker/nginx/snippets /etc/nginx/snippets
COPY docker/nginx/conf.d /etc/nginx/conf.d
COPY dist /app

EXPOSE 5555
