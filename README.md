# shell_reference
A reference guide for useful shell commands and tools

## FFmpeg
### How to download video from a website
1. Find the url of the .m3u8 file
   - Often you can find it either by searching the network tab or page source.
   - Usually the file you want is called "master.m3u8"
   - .m3u8 files are playlist files that tell a media player where to find their resources and what order to play them.
   - <https://en.wikipedia.org/wiki/M3U>
2. In the terminal run: `ffmpeg -i "https://url-for-m3u8.com/playlist/master.m3u8" output.mp4`
   - The quotation marks are important for escaping.
   - You can change the name and type of the output.
   - Look at FFmpeg's documentation for more options.