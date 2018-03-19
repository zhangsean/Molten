FROM php:alpine
RUN echo "http://mirrors.aliyun.com/alpine/v3.7/main/" > /etc/apk/repositories \
 && echo "http://mirrors.aliyun.com/alpine/v3.7/community/" >> /etc/apk/repositories \
 && apk add --no-cache autoconf make g++ linux-headers \
 && wget https://github.com/chuan-yun/Molten/archive/master.zip \
 && unzip master.zip \
 && cd Molten-master \
 && phpize \
 && ./configure --enable-zipkin-header=yes \
 && make && make install \
 && cd .. \
 && rm -rf master.zip Molten-master \
 && echo "extension=molten.so" > /usr/local/etc/php/conf.d/molten.ini \
 && php -i | grep molten
