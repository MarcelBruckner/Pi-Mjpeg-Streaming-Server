# Pi-Mjpeg-Streaming-Server
Stream the Raspberry Pi libcamera2 as an MJPEG stream via http

## Setup

```bash
# Install git
sudo apt install git

# Clone repository
git clone https://github.com/MarcelBruckner/Pi-Mjpeg-Streaming-Server.git
cd Pi-Mjpeg-Streaming-Server

# If you clone the repository in /home/pi then you can skip this step
# If you clone it to another path adjust `ExecStart=/usr/bin/python3 YOUR/PATH/Pi-Mjpeg-Streaming-Server/server.py`
nano server.service

# Install libcamera dependencies
sudo apt install -y python3-picamera2 --no-install-recommends

# Make the service available to systemd
sudo ln -s $PWD/server.service /etc/systemd/system/
sudo systemctl daemon-reload

# Enable and start the service
sudo systemctl enable --now server.service
```

## Access

Access the stream via `http://IP:8000`
