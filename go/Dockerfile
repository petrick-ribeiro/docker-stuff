# Multistage build

FROM golang AS build

WORKDIR /app
ADD . /app/
RUN go build -o test

FROM alpine

WORKDIR /app
COPY --from=build /app/test /app/

ENTRYPOINT [ "./test" ]
