FROM alpine:3

ARG POCKETBASE_VERSION=0.7.10
# Install the dependencies
RUN apk add --no-cache \
  ca-certificates \
  unzip \
  wget \
  zip \
  zlib-dev

WORKDIR /tmp
# Download Pocketbase and install it for AMD64
RUN wget -O /tmp/pocketbase.zip https://github.com/pocketbase/pocketbase/releases/download/v${POCKETBASE_VERSION}/pocketbase_${POCKETBASE_VERSION}_linux_amd64.zip && \
  unzip /tmp/pocketbase.zip -d /usr/local/bin/ && \
  chmod +x /usr/local/bin/pocketbase && \
  rm -rf /tmp/pocketbase.zip

# Notify Docker that the container wants to expose a port.
EXPOSE 8090

# Start Pocketbase
CMD [ "/usr/local/bin/pocketbase", "serve" ]
