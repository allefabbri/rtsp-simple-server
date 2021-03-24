# Run container with

docker run --rm -it --network=host aler9/rtsp-simple-server
docker run --rm -it -e RTSP_PROTOCOLS=tcp -p 8554:8554 -p 1935:1935 aler9/rtsp-simple-server

# Publish stream with

ffmpeg -re -stream_loop -1 -i .\sample.mkv -c copy -f rtsp rtsp://localhost:8554/mystream

# Enjoy

vlc rtsp://localhost:8554/mystream
