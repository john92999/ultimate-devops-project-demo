FROM golang:1.22-alpine AS builder
WORKDIR /usr/src/app
COPY . .
RUN go mod download
RUN go build -o product-catalog .
FROM alpine as runner
ENV PRODUCT_CATALOG_PORT 8088
WORKDIR /usr/src/app
COPY --from=builder /go/bin/product-catalog ./
COPY ./products ./products
ENTRYPOINT ["./product-catalog"]