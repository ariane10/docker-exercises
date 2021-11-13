FROM nginx:1.19.3

COPY html/index.html /usr/share/nginx/html/

EXPOSE 8080

HEALTHCHECK --interval=45s --timeout=5s --start-period=25s --retries=2 CMD curl --fail http://localhost:8080/ || exit 1


