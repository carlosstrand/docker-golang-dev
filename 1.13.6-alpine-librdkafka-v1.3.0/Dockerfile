FROM golang:1.13.6-alpine

WORKDIR /app

RUN apk update && apk upgrade && apk add git bash build-base sudo pkgconfig

RUN git clone https://github.com/edenhill/librdkafka.git --branch "v1.3.0" --single-branch \
    && cd librdkafka && ./configure --prefix /usr \
    && make \
    && make install

RUN go get github.com/cespare/reflex