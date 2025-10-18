# yt-dlp
ytdlp mp3 download with thumbnail, links from links.txt, no playlist, just title without id
```bash
yt-dlp -x --audio-format mp3 --embed-thumbnail --hls-prefer-ffmpeg --no-playlist -o "%(title)s.%(ext)s" -a "./links.txt"
```
# Conversion
## Imagery
Convert image to another format.
```bash
magick file.in file.out
```
Example:
```bash
magick potato.png potato.jpg
```
Convert png to jpg.
# Video
mp4 → mp3
```bash
ffmpeg -i in.mp4 -q:a 0 -map a out.mp3
```
mp4 → gif
```bash
ffmpeg -i in.mp4 -vf "fps=10,scale=640:-1:flags=lanczos" -loop 0 out.gif
```
**Optional quality tweaks:**
- `-vf fps=10` → change frame rate
- `scale=640:-1` → resize width
- `-q:a 0` → max audio quality
