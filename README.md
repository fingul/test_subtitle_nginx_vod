# NGINX VOD - SUBTITLE TEST example

# BUILD

> docker build -t test-nginx-vod-module .

# RUN

> docker run -p 3030:80 -v $PWD/videos:/opt/static/videos -v $PWD/nginx.conf:/usr/local/nginx/conf/nginx.conf test-nginx-vod-module

# HLS (WORKING)
- MASTER : http://localhost:3030/hls/devito,360p.mp4,.en_US.vtt,.urlset/master.m3u8
- INDEX : http://localhost:3030/hls/devito.en_US.vtt/index.m3u8
- SEGMENT : http://localhost:3030/hls/devito.en_US.vtt/seg-1.vtt

# MSS (WORKING - via rxplayer)

- MANIFEST : http://localhost:3030/mss/devito,360p.mp4,.en_US.vtt,.urlset/manifest

# DASH SUB - vod_dash_subtitle_format webvtt (WORKING)

- MANIFEST : http://localhost:3030/dash/devito,360p.mp4,.en_US.vtt,.urlset/manifest.mpd
- SEGMENT : http://localhost:3030/dash/devito,360p.mp4,.en_US.vtt,.urlset/sub-f2.vtt

# DASH SUB - vod_dash_subtitle_format smpte-tt (WORKING)

- MANIFEST : http://localhost:3030/dashs/devito,360p.mp4,.en_US.vtt,.urlset/manifest.mpd


