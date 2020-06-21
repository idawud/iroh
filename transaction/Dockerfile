# build stage
FROM golang:1.14-alpine AS build-env
ADD . /src
RUN cd /src && go build -o transaction

# final stage
FROM alpine
WORKDIR /app
COPY --from=build-env /src/transaction /app/
ENTRYPOINT ./transaction