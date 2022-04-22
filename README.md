# shell_reference
A reference guide for useful shell commands and tools

## Basics
### Navigation
#### cd (change directory)
`cd ..`
- `..`: means 1 directory above

#### ls (list)
`ls -lh`
- flags:
   - `l`: list the results with extra informatation including the permissions, the owner, the size, and last date edited
   - `h`: show the file size in human-readable format (KB, MB, GB)

### file and directory management
#### mkrdir (make directory)
`mkdir 'dir_name'`
- `'dir_name'`: The directory you want to create

## FFmpeg (video editing)
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

## grep (searching for text)
Stands for "Gnu REgex Parser"  
`grep -rnI --include="*.txt" 'search_regex' .`
- flags:
   - `r`: recursively search sub-directories
   - `n`: return the line-numbers where the text was found
   - `I`: ignore binary files
   - `include`: only include files matching the given format string in the search
      - `"*.txt"`: the format string to match the file name against
- `'search_regex'`: a regex string to match
- `.`: The directory to start the search (in this example the current directory)

## find (searching for a file/directory name)
`find . -name 'search_regex' -type f`
- flags:
   - `-name 'search_regex'`: the regex string to match (omitting will get everything)
   - `-type f`: search for only files (`-type d` for directories, omit for both)
- `.`: The directory to start the search (in this example the current directory)

## zip (compressing and encrypting)
`zip -re output_name.zip 'dir_name'`  
You will be prompted for a password afterwards  
- flags:
   - `r`: recursively add sub-directories
   - `e`: encrypt the result
- `'dir_name'`: The directory containing everything you want zipped
- `output_name.zip`: The outputted zip file name

## hashing
`shasum -a 512256 'file_name'`
- flags:
   - `a`: specify which hashing algorithm to use
- `512256`: choose the SHA 512/256 algorithm (currently considered secure)
- `'file_name'`: The file containing the data to hash

## hexdump (view binary value of a file)
Formats the result into human readable chunk and includes the ascii interpretation as well.  
`xxd 'file_name'`
- flags:
   - `p`: output the plain unformatted hexdump.
   - `b`: output the result as bits instead of hex
   - `l`: specify the length of the output (defaults to whole file)
   - `s`: seek to start the output at a given offset
- `'file_name'`: The file containing the data to hash

## ps (processes)
`ps -ef`
- flags:
   - `e`: show every process on the system.
   - `f`: show full formatted listing

### Columns
- UID: Username of the process's owner
- PID: Process ID number
- PPID: ID number of the process's parent process
- C: CPU usage and scheduling information
- STIME: Time when the process started
- TTY: Terminal associated with the process
- TIME: Total CPU usage
- CMD: Name of the process, including arguments, if any

