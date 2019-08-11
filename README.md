# Navigate and play M3U/M3U8 playlist from Vim.

The M3U/M3U8 playlists have a very simple format. The M3U file can also include comments, prefaced by the "#" character. In extended M3U, "#" also introduces extended M3U directives. Basically most M3U playlists are composed of a header, information about the content and the path / link to the media content (TV streaming, Videos, Radio, etc) as seen in the example.
```bash
#EXTM3U
#EXTINF:1, Sample Windows artist - Sample title
C:\Documents and Settings\I\My Music\Sample.mp3
#EXTINF:2, Sample Linux artist - Sample title
/home/user/Music/Sample.mp3
#EXTINF:3 tvg-id="TVE TDT HD 3.sp" tvg-name="La 2 1080" tvg-logo="" group-title="****TDT SPAIN****",La 2 1080
http://premium.vsytes.net:8080/User1/XXX
```

With the following Vim key mapping (.vimrc), you can view a M3U playlist from Vim, search for the desired content, position the cursor over the line and with a key (e.g. F6) start playing it. The same example is shown with three different media players.

```bash
# Mplayer (4Mb Cache optional).
nmap <F6> :exec '!mplayer -cache 4096 -cache-min 99 '.getline('.')

# FFplay.
nmap <F6> :exec '!ffplay '.getline('.')

# VLC
nmap <F6> :exec 'vlc '.getline('.')
```
