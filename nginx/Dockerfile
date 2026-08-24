FROM nginx:1.27-alpine

ENV UPSTREAM_HOST=app

COPY nginx/templates/default.conf.template /etc/nginx/templates/default.conf.template
COPY static/ /usr/share/nginx/html/static/
