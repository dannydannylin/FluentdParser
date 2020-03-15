FROM fluent/fluentd:v1.4-1
MAINTAINER YOUR_NAME <...@...>

USER root

RUN apk add --no-cache --update --virtual .build-deps \
        sudo build-base ruby-dev \
 # cutomize following instruction as you wish
 && sudo gem install fluent-plugin-elasticsearch \
 && sudo gem install fluent-plugin-grep \
 && sudo gem install fluent-plugin-dict-map \
 && sudo gem install fluent-plugin-parser_cef \
 && sudo gem install fluent-plugin-kvp-filter \
 && sudo gem install fluent-plugin-rewrite-tag-filter \
 && sudo gem install fluent-plugin-multi-format-parser \
 && sudo gem sources --clear-all \
 && apk del .build-deps \
 && rm -rf /home/fluent/.gem/ruby/2.5.0/cache/*.gem

COPY entrypoint.sh /bin/
USER root
