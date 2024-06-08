# Use the official Golang image as the base image
FROM golang:1.16

# Set the working directory inside the container
WORKDIR /app

# Copy the Go module files
COPY go.mod .
COPY go.sum .

# Download and install dependencies
RUN go mod download

# Copy the rest of the source code
COPY . .

# Build the Go app
RUN go build -o server .

# Expose the port the server listens on
EXPOSE 8080

# Set the origin URL for CORS checks to allow requests from localhost:5000
ENV REQUEST_ORIGIN=http://localhost:5000

# Command to run the executable
CMD ["./server"]

