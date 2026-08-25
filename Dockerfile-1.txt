# Use a recent Xray-core image (XHTTP transport requires v1.8.4+)
FROM teddysun/xray:latest

# Copy your server config into the image
COPY config.json /etc/xray/config.json

# Railway routes external traffic to this port (must match config.json "port")
EXPOSE 8080

# Start Xray with the config
CMD ["xray", "-config", "/etc/xray/config.json"]
