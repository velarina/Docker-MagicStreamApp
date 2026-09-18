#using a light weight Alphine Linux Image with Go 1.24.2 installed
#this is will allow to run go within the relevant Docker container
FROM golang:1.24.2-alpine

#set for app is the working dirrectory inside the container
WORKDIR /app

COPY go.mod go.sum ./
RUN go mod download

COPY . .

#listen to port 8080, but we are mapping the container port to the host port
EXPOSE 8080

#running the go components
CMD ["go", "run", "main.go"]