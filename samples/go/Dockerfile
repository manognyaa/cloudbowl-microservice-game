FROM golang:1.13-alpine AS build
WORKDIR /src/app
COPY . .
RUN go mod download
RUN go build -o /bin/app

FROM alpine:3.17.3
COPY --from=build /bin/app /bin/app
ENTRYPOINT ["/bin/app"]
