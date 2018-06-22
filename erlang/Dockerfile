FROM alpine:3.7

RUN apk add -U curl \
 && curl https://s3.amazonaws.com/rebar3/rebar3 > /usr/local/bin/rebar3 \
 && chmod +x /usr/local/bin/rebar3


FROM erlang:20-alpine

RUN apk add -U inotify-tools

COPY          rebar.config          /root/.config/rebar3/
COPY --from=0 /usr/local/bin/rebar3 /usr/local/bin/

EXPOSE 8080