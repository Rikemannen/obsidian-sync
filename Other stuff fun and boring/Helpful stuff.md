ytdlp mp3 download with thumbnail, links from links.txt, no playlist, just title without id
```bash
yt-dlp -x --audio-format mp3 --embed-thumbnail --hls-prefer-ffmpeg --no-playlist -o "%(title)s.%(ext)s" -a "./links.txt"
```
