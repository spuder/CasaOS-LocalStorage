
# Use the official Golang image as a parent image
FROM golang:1.21-bookworm

# Set the working directory inside the container
WORKDIR /workspace

# Install goreleaser
RUN go install github.com/goreleaser/goreleaser@latest

# Install additional packages
RUN apt-get update && apt-get install -y --no-install-recommends \
    upx \
    gcc \
    libc6-dev-amd64-cross \
    gcc-aarch64-linux-gnu \
    libc6-dev-arm64-cross \
    gcc-arm-linux-gnueabihf \
    libc6-dev-armhf-cross \
    && rm -rf /var/lib/apt/lists/*

# Copy the local package files to the container's workspace
COPY . .