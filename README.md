# Pi-Mjpeg-Streaming-Server
Stream the Raspberry Pi libcamera2 as an MJPEG stream via http

## Setup

1. Clone repository via `git clone https://github.com/MarcelBruckner/Pi-Mjpeg-Streaming-Server.git`
2. `cd Pi-Mjpeg-Streaming-Server`
3. Edit `server.service` and adjust the `/PATH/TO/server.py`. This has to be the absolute path to the `server.py` file. While in the repository folder, run `pwd` to quickly get the absolute path.
4. Enable the service:
   ```bash
   sudo ln -s $PWD/server.service /etc/systemd/system/
   
   sudo systemctl daemon-reload
   sudo systemctl enable --now server.service
   ```

## Access

Access the stream via `http://IP:8000`
