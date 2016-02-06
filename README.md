#Ahjolinna's MPV conf build (⌐■_■)


---input wanted

![mpv-conf Preview](http://i.imgur.com/5B881oX.png)

#### Summary : 
This is my first version of MPV(-build-git) with some premade conf files, and with MVtools support ( Motion Interpolation aka smooth motion).

#### Basic info:
* ytdl works out of the box, there is A LOT "keyboard bindings", it should support every codec what mpv and ffmpeg can/has (even non-free codecs)

* There is 4 different quality settings : uq, hq, mq & lq. MVtools uses medium quality because it's so CPU intensive. There is also the "normal" mpv.desktop file.

* You can also use `--script-opts=ao-level=<level>` to force a specific quality level from command line. Upon start will select a level (o.uq/o.hq/o.mq/o.lq) whose options will then be applied.

* the plan is to have only 2 premade quality desktop file (max 3), the normal and MVtools. The idea is that uq would be for 4k owners only, lq is "fallback for laptop's and hq is the default one...mq would be for MVtools.

* if someone wants I can make version without the non-free codec support , and/or more lighter/simpler one, and/or stable version (not git)..but I will do that after conf files are in better shape

####ytdl info:
ytdl ("youtube and a like") support  was  added so it mpv will automatically work with without adding the additional '--ytdl' command, aka you only need to add/write mpv <link> nothing else.. nothing more
```
Example: mpv https://vimeo.com/148177620
```
Twitch live streaming info: If you want to watch live twich.tv video streams you need to install 'livestreamer' app, and to watch them with MPV you need to use this following command :
```
livestreamer -p mpv <twitch link> <quality> --player-continuous-http
``` 
```
Example: livestreamer -p mpv http://www.twitch.tv/angryjoeshow best --player-continuous-http
```

#### side note:
the <quality> "command" is for the stream quality** 
**You can get the list of available quality formats using:  "youtube-dl <link>  --list-formats"

####NOTE:
if you want to use MVtools you need to install 'vapoursynth-plugin-mvtools' to use it, BUT remember it's really CPU demanding feature
```
    What Smooth Motion is not, is a frame interpolation system—it will not introduce the “soap opera effect” like you see on 120Hz+ TVs, or reduce 24p judder.

    Smooth Motion is designed to display content where the source framerate does not match up to any of the refresh rates that your display supports. For example, that would be 25/50fps content on a 60Hz-only display, or 24p content on a 60Hz-only display.

    It does not replace ReClock or VideoClock, and if your display supports 1080p24, 1080p50, and 1080p60 then you should not need to use Smooth Motion at all.

    Because Smooth Motion works by using frame blending you may see slight ghost images at the edge of moving objects—but this seems to be rare and dependent on the display you are using, and is definitely preferable to the usual judder from mismatched framerates/refresh rates.
```

there is more info at mpv's [wiki page](https://github.com/mpv-player/mpv/wiki/Interpolation)

## (MPV) Requirements
* [`Adobe Source Sans Pro`](http://adobe-fonts.github.io/source-sans-pro/): used in OSD
* `youtube-dl`: youtube videos and a like
* `livestreamer`: to watch live video streams (twitch.tv)
* `vapoursynth`: for some script support like MVtools '--enable-vapoursynth' needs to be added in mpv build
* `vapoursynth-plugin-mvtools`: Realtime motion interpolating playback in mpv
* `acpitool`: for "battery mode" detection
* `inxi`: HIDPI-detection
* `libvdpau or libva`: for hardware-acceleration support

`|-o-| ---FUTURE PLANS--- |-o-|`
```
1) make vdpau/vaapi only enabled with the correct hardware/drivers ||DONE
2) make non-free codecs optional
3) more "automatic" quality settings in the (lua) scripts || semi-DONE
4) adding laptop & desktop detection it has been added/changed to battery detection || DONE
5) support for upscaling for 4K monitors (the 4k upscaling is now on 'ultra-quality'-settings)..|| DONE
5.1)  make "4k support" automatic by adding monitor resolution detection (detection support is now added) || semi-DONE
6) better documentation when most of these features have been || done
7) one thing I would like to do, is to have same video quality setting  what bomi-player uses (video->Quality Preset)...but they are little bit weird...it would be nice if someone could help with that
```
`( ∙_∙) ( ∙_∙)>⌐■-■ (⌐■_■)`

