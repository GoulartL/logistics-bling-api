FROM nginx:alpine

LABEL maintainer="AGL Sistemas <contato@aglsistemas.com.br>"

RUN apk update

COPY default.conf /etc/nginx/conf.d/default.conf
COPY upstream.conf /etc/nginx/conf.d/upstream.conf