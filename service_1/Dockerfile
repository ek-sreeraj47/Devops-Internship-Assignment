# Use an official Go runtime as the build environment
FROM golang:1.24.4-alpine AS builder

# Set working directory inside container
WORKDIR /app

# Copy go.mod and go.sum if available
COPY go.mod ./

# Download dependencies (if using Go modules)
RUN go mod download || true

# Copy the full source code
COPY . .

# Build the Go app
RUN go build -o service1

# Use a minimal base image for the final container
FROM alpine:latest

# Set working directory
WORKDIR /app

# Copy the binary from the builder
COPY --from=builder /app/service1 .

# Expose the port the app runs on
EXPOSE 8001

# Run the binary
CMD ["./service1"]

