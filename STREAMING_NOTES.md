force audio over HDMI in sudo raspi-config > advanced




## cropping in vlc
https://forum.videolan.org/viewtopic.php?t=149455
```
DISPLAY=:0 vlc glue.mp4 --video-filter=croppadd --croppadd-cropleft=200 --croppadd-cropright=200 --codec avcodec,none
```

*NOTE*: some concerns about slowing down... maybe it's doing it software and fucking with the hardware acceleration...


## cropping with ffmpeg

This is very doable, but ffmpeg isn't a player so not sure where we would insert this...

References:
https://video.stackexchange.com/questions/4563/how-can-i-crop-a-video-with-ffmpeg


## Streaming media servers

I think we potentially need this to create a simple multicast setup... but I'm confused

http://www.live555.com/liveMedia/
> The libraries can also be used to stream, receive, and process MPEG, H.265, H.264, H.263+, DV or JPEG video, and several audio codecs 
> can also be used to build basic RTSP or SIP clients and servers
