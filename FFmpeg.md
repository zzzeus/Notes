# Some notes about ffmpeng
[reference](https://gist.github.com/dvlden/b9d923cb31775f92fa54eb8c39ccd5a9)

## Quick look

* convert to mp4
```
ffmpeg -i  a.flv -c:v libx264 -strict -2 a.mp4
```
* h264 to mpeg4 & mpeg4 to h264
```
ffmpeg -i input.mp4 -vcodec mpeg4 output.mp4

ffmpeg -i input.mp4 -vcodec h264 output.mp4
```
* get audio only
```
#ffmpeg -i a.mp4 -f wav -ar 16000 a.wav
ffmpeg -i a.mp4 -acodec aac -vn output.aac
```

* get video only
```
ffmpeg -i input.mp4 -vcodec copy -an output.mp4
```
* cut video
```
ffmpeg -ss 00:00:15 -t 00:00:05 -i input.mp4 -vcodec copy -acodec copy output.mp4
```

## Basic parameters
#### main parameters：
```
-i 设定输入流 
-f 设定输出格式 
-ss 开始时间 
```

#### video parameters：
```
-b 设定视频流量(码率)，默认为200Kbit/s 
-r 设定帧速率，默认为25 
-s 设定画面的宽与高 
-aspect 设定画面的比例 
-vn 不处理视频 
-vcodec 设定视频编解码器，未设定时则使用与输入流相同的编解码器 
```

#### 音频参数：
```
-ar 设定采样率 
-ac 设定声音的Channel数 
-acodec 设定声音编解码器，未设定时则使用与输入流相同的编解码器 
-an 不处理音频
```


