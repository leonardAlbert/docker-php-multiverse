FROM nginx:alpine

ENV TIMEZONE America/Sao_Paulo

RUN echo "http://dl-cdn.alpinelinux.org/alpine/edge/main"  >> /etc/apk/repositories

RUN apk update && \
    apk upgrade && \
    apk add --update tzdata && \
    cp /usr/share/zoneinfo/${TIMEZONE} /etc/localtime && \
    echo "${TIMEZONE}" > /etc/timezone && \
    apk upgrade && \
    apk add --update tzdata

RUN apk --no-cache \
    add curl \
    # supervisor \
    --repository http://dl-cdn.alpinelinux.org/alpine/edge/testing/
