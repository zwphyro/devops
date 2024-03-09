FROM alpine:3.19.1

ARG USER=nonroot
ENV HOME /home/$USER

RUN apk add --update sudo --no-cache && \
    adduser -D $USER && \
    echo "$USER ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/$USER && \
    chmod 0440 /etc/sudoers.d/$USER

USER $USER
WORKDIR $HOME

RUN sudo apk add nginx --no-cache

CMD sudo nginx -g 'daemon off;'
