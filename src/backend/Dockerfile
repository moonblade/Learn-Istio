# Build stage
FROM golang:1.17-alpine AS build

# Set the working directory
WORKDIR /app

# Copy the Go mod and sum files
COPY go.mod go.sum ./

# Download the Go modules
RUN go mod download

# Copy the source code into the container
COPY . .

# Build the Go binary
RUN go build -o counter .

# Run stage
FROM alpine:latest

# Install necessary packages
RUN apk update && apk add --no-cache ca-certificates tzdata

# Set the timezone to your local timezone
ENV TZ=America/New_York

# Copy the Go binary from the build stage into the container
COPY --from=build /app/counter /app/counter

# Expose the port your Go application listens on
EXPOSE 8080

# Set the working directory
WORKDIR /app

# Start the Go binary
CMD ["./counter"]
