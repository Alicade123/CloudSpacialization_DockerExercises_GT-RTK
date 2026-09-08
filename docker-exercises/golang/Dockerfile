#Build
FROM golang:1.26-alpine AS build

WORKDIR /app

RUN go mod init myapp

COPY . .

RUN CGO_ENABLED=0 GOOS=linux go build -o server .

#CGO_ENABLED=0 turns off C-library dependencies (making it completely self-sufficient).
#GOOS=linux ensures it compiles for Linux, since Docker containers run on Linux.

#Runner
FROM scratch

COPY --from=build /app/server /server

EXPOSE 6000

CMD ["/server"]