## This is a note about some commands



### Examples
```
# convert to mp4
ffmpeg -i  a.flv -c:v libx264 -strict -2 a.mp4

# h264 to mpeg4
ffmpeg -i input.mp4 -vcodec mpeg4 output.mp4
# mpeg4 to h264
ffmpeg -i input.mp4 -vcodec h264 output.mp4

# get audio only
#ffmpeg -i a.mp4 -f wav -ar 16000 a.wav
ffmpeg -i a.mp4 -acodec aac -vn output.aac

# get video only
ffmpeg -i input.mp4 -vcodec copy -an output.mp4
# cut video
ffmpeg -ss 00:00:15 -t 00:00:05 -i input.mp4 -vcodec copy -acodec copy output.mp4
```
