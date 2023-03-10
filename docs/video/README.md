# Automated Overview Video Generation (using FFMPEG)

> credit: [@cairocoder01](https://github.com/cairocoder01)

 ## Get Audio
 1. Write out a script to be recorded
 2. Go to https://cloud.google.com/text-to-speech#section-2 and select a desired voice in the demo section. (recommended: Voice Type: `News` / Voice Name: `en-US-News-L`)
 3. Paste your script into the demo.
 4. Open Chrome dev tools -> Network
 5. Click "Speak It" button
 6. Look for a request starting with "proxy" (e.g. https://cxl-services.appspot.com/proxy?url=https://texttospeech.googleapis.com/...)
 7. Open response and copy the `audioContent` property into a text file (e.g. audio.txt).
 8. Open a terminal/console in the directory where the text file is saved and run `base64 -d -i audio.txt -o audio.mp3`
 9. If you have multiple audio files, they can first, be merged into a single file, by listing them within a text file (E.g. `audio_files.txt`) and using the `ffmpeg` command to merge.

 ```sh
 ffmpeg -f concat -i audio_files.txt -c:a libmp3lame audio.mp3
 ```

 ## Get Screenshots
 See [FFMPEG wiki](https://trac.ffmpeg.org/wiki/Slideshow) for details.

 1. Take screenshots of all views you want to be shown in the video.
 2. Edit `video.txt` to set the order and duration of each image.

```sh
file '../imgs/1.png'
duration 25 # 0:25
file '../imgs/2.png'
duration 28 # 0:53
file '../imgs/3.png'
duration 27 # 1:20
file '../imgs/4.png'
duration 10 # 1:30
...
```

 3. Open a terminal/console and run:

 ```sh
 ffmpeg -f concat -safe 0 -i video.txt -vsync vfr -pix_fmt yuv420p -vf "pad=ceil(iw/2)*2:ceil(ih/2)*2" video.mp4
 ```
 4. Your video without audio is available in `video.mp4`

 ## Merge Audio and Video

 ```sh
 ffmpeg -i video.mp4 -i audio/audio.mp3 -c:v copy -c:a aac dt_make_howto.mp4
 ```