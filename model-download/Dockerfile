FROM alpine:latest

WORKDIR /

RUN apk update && apk add --no-cache \
    bash \
    wget

# create non-root user
RUN adduser -D app

COPY run.sh /

# change ownership & perms
RUN chown app:app /run.sh && chmod 755 /run.sh
RUN mkdir -p /models && chown app:app /models

USER app

CMD ["bash", "/run.sh"]
