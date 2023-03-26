# webhooks

Various custom webhooks that I use together with homeassistant, mpd and the ikea
styrbar 5-button remote

```
webhook -hooks hooks.json -verbose
```

## love

Love the currently playing song in mpd when I long-press the up button on my
ikea 5-button remote.

A few things happen:

- Love the song in [pimpd2](https://github.com/trapd00r/pimpd2)
- Copy the song to a pre-defined directory where all loved songs reside
- Add a new custom tag in beets, called `loved`; this allows for beet /
  [beet2mpd](https://github.com/trapd00r/beet2mpd) to accept queries like:

  `beet2mpd loved:1 albumtype:single`

  Which will add all loved songs that are considered singles.

- Update the smart playlists that beet handles.
- Send a very beautiful notification to the desktop. It's red.

  ![screenshot](/extra/love.png)


```
curl http://192.168.1.12:9000/hooks/mpd_love_song
```


## mpd_randomize

Clear the playlist and add 250 random songs to the playlist with a long press on
the down button

```
curl http://192.168.1.12:9000/hooks/mpd_randomize
```
