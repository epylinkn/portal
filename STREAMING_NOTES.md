UNRELATED:
https://unix.stackexchange.com/questions/43601/how-can-i-set-my-default-shell-to-start-up-tmux/306165#306165



force audio over HDMI in sudo raspi-config > advanced


TODO:
MMAL
v4l2
https://www.raspberrypi.org/forums/viewtopic.php?t=227185
https://rwdy15.wordpress.com/2015/02/12/streaming-with-ffmpeg-and-receiving-with-vlc/


Still the best resource:
https://info-beamer.com/blog/dual-display-or-4k-and-hevc-on-the-pi-4
https://info-beamer.com/raspberry-pi-digital-signage-hevc-4k-video-demo-13218.html
> The HEVC decoder of the Pi4 can theoretically decode videos with a resolution up to 4096x4096 pixels. That's more than enough to decode 4K videos (3840x2160).
actual ffmpeg patch... https://github.com/info-beamer/FFmpeg/commit/9f99212dfac45d17de83b8f514d2e9c6de17ccac
https://github.com/popcornmix/FFmpeg/tree/2711

info-beamer dude on reddit!
https://www.reddit.com/r/raspberry_pi/comments/e64bl6/is_the_4bs_h265_hardware_decode_currently/




A good overview of streaming...
https://www.wowza.com/blog/streaming-protocols

## pi 4 hardware acceleration
libelec was first

apparently, ffmpeg and vlc now have it...
VLC testing: https://www.raspberrypi.org/forums/viewtopic.php?t=257395

https://www.raspberrypi.org/documentation/usage/video/
Pi 4 moving away form OMXPlayer...
> VLC has hardware support for H264 and the new HEVC codec.

curising omx issues with @popcornmix
https://github.com/popcornmix/omxplayer/issues/714


answered:
https://raspberrypi.stackexchange.com/questions/99885/hevc-playback-on-rpi-4

## FFMPEG "re-streaming"

- THE streaming guide
https://trac.ffmpeg.org/wiki/StreamingGuide

wowza guide with re-streaming examples for all streaming protocols!
https://www.wowza.com/docs/how-to-restream-using-ffmpeg-with-wowza-streaming-engine#sample

## vlc

### streaming examples
https://wiki.videolan.org/Documentation:Streaming_HowTo/Command_Line_Examples/

### cropping
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

Red5 Pro
FFServer (deprecated)
https://stackoverflow.com/questions/26999595/what-steps-are-needed-to-stream-rtsp-from-ffmpego
https://en.wikipedia.org/wiki/List_of_RTMP_software

## pi wall

https://groups.google.com/forum/?hl=en-GB#!topic/piwall-users/VIQWmDqQAJI
> but i think that it is not possible with piwall software, because it send video information by LAN network, and use one ip address for every tv (a piece of tv wall). with Rpi4 you have 1 board, 1 ip address, 2 microhdmi output, but you can use only one htmi output.


http://www.piwall.co.uk/
NOTE: hoenstly this shit is really outdated... source uses OMXPlayer...



## gstreamer

https://brettviren.github.io/pygst-tutorial-org/pygst-tutorial.html



## some router shit
https://superuser.com/questions/695813/wifi-udp-unicast-vs-multicast-speed
https://raspberrypi.stackexchange.com/questions/37920/how-do-i-set-up-networking-wifi-static-ip-address/37921#37921
https://www.raspberrypi.org/forums/viewtopic.php?t=189582
