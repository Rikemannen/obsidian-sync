# yt-dlp
Download mp3's of links in links.txt along with their thumbnail, ignore playlists. You can set a full path in `-o` and `-a`
```bash
yt-dlp -x --audio-format mp3 --embed-thumbnail --hls-prefer-ffmpeg --no-playlist -o "~/Music/%(uploader)s - %(title)s.%(ext)s" -a "./links.txt"
```
Create a list of urls in a playlist and save to links.txt
```bash
yt-dlp --flat-playlist -J "PLAYLIST_URL" | python -c "import sys, json; data=json.load(sys.stdin); print('\n'.join('https://www.youtube.com/  
watch?v='+e['url'] for e in data['entries']))" > links.txt
```
Download all links except for those already downloaded according to downloaded.txt, along with settings from first command.
```bash
yt-dlp -x --audio-format mp3 --embed-thumbnail --hls-prefer-ffmpeg --no-playlist -o "~/Music/%(uploader)s - %(title)s.%(ext)s" -a "./links.txt" --download-archive "downloaded.txt"
```
Wanna download a playlist? Use this :)
```bash
yt-dlp -x --audio-format mp3 --embed-thumbnail --hls-prefer-ffmpeg -o "~/Music/%(uploader)s - %(title)s.%(ext)s" --download-archive "~/Music/existing.txt" "PLAYLIST_URL"
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
