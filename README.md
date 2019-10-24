# Yet Another Python Matrix

[![Preview](https://i.imgur.com/mLwIpXP.png)](https://i.imgur.com/LgHiLiA.png)

[https://giphy.com/gifs/matrix-lrIeTla9JsxCwn9QX1](https://giphy.com/gifs/matrix-lrIeTla9JsxCwn9QX1)

## Why

Well, first of all, [The Matrix](https://www.imdb.com/title/tt0133093/) is the best Sci-Fi movie ever made, and the green code rain alone inspired me like few other things ever have.

Yes, it's yet another matrix code generator. [Cmatrix](https://github.com/abishekvashok/cmatrix) is one of my favorite programs, but after a few days learning Python I thought to myself, __"Hey I could do this myself, maybe better, the right way"__. And I think I did okey.

I've gone back to the source material, and tried to really figure out how to make it look like the original. The beautiful thing is, if you disagree with the result, you can change it to your own liking! :-)

## Usage

```sh
git clone https://github.com/elundmark/yapymatrix.git
cd yapymatrix/
chmod u+x yapymatrix
./yapymatrix [ options ]
```

To stop the program, use `Ctrl + C`. I am not planning on adding any keyboard shortcuts, but who knows what happens in the future.

## Options

Here's the current list of options. This can also be printed by executing `yapymatrix --help`

```
usage: YAPYMatrix [-h] [-V] [-f FPS] [-s STOP_AFTER] [-b] [-C] [-B] [-l] [-L]
                  [-t] [--include-spaces INCLUDE_SPACES]
                  [--onscreen-letters-timer ONSCREEN_LETTERS_TIMER]
                  [--random-bold RANDOM_BOLD] [-R ROGUE_AGENTS]
                  [--spaces-abs-min-height SPACES_ABS_MIN_HEIGHT]
                  [--spaces-abs-max-height SPACES_ABS_MAX_HEIGHT]
                  [--spaces-rel-max-height SPACES_REL_MAX_HEIGHT]
                  [--strings-abs-max-height STRINGS_ABS_MAX_HEIGHT]
                  [--strings-abs-min-height STRINGS_ABS_MIN_HEIGHT]
                  [--strings-rel-max-height STRINGS_REL_MAX_HEIGHT]
                  [--vertical-cache VERTICAL_CACHE]

YAPYMatrix 0.4.1 (2019-10-24) Highly customizable Matrix Code Emulator written
in python [https://github.com/elundmark/yapymatrix]

optional arguments:
  -h, --help            show this help message and exit
  -V, --version         show program's version number and exit
  -f FPS, --fps FPS     Frames per second, or delay between updates to be
                        precise. This will be converted to 1 / fps and used as
                        seconds to sleep between updates. If this is over 60,
                        sleep will be omitted (Default: 21)
  -s STOP_AFTER, --stop-after STOP_AFTER
                        Stop program after N loops, useful if you want to have
                        it on for a while but not forever (Default: 0)
  -b, --force-black     Color all backgrounds black. Normally your terminals
                        default color-scheme will be used (Default: False)
  -C, --no-colors       Do not use any colors. This will speed up things quite
                        a bit, so think of using this if you are using
                        something like cool-retro-term (Default: False)
  -B, --no-bold-characters
                        Do not use any bold characters (Default: False)
  -l, --sparse-columns  This will skip every other column, to make it look a
                        little lighter. Works best on wide terminals. Plus it
                        speeds up things a bit (Default: False)
  -L, --very-sparse-columns
                        This will skip 2 of 3 column, to make it look a lot
                        lighter. Works best on wide terminals. Plus it speeds
                        up things a lot (Default: False)
  -t, --tv-intro        This skips a step when the program starts, and it will
                        look more like an old crt television warming up. This
                        started out a a bug, but now I kinda like it, so I
                        made it an optional extra (Default: False)
  --include-spaces INCLUDE_SPACES
                        The original matrix code has spaces included in the
                        strings, which I don't think I've seen in any other
                        versions. Experimenting with this value will increase
                        the amount it will 'sparkle', or set it to 0 to
                        disable spaces entirely (Default: 3)
  --onscreen-letters-timer ONSCREEN_LETTERS_TIMER
                        This might be the most important part imo; how long
                        should the characters 'stick' in one place? The number
                        represents the maximum amount of times it shows before
                        it is replaced. Randomness is also added to make it
                        look organic (Default: 5)
  --random-bold RANDOM_BOLD
                        Make characters bold by a random chanse of 1 in N.
                        Making this 0 will not turn off bold characters
                        completely, to do this, use --no-bold-characters
                        instead (Default: 8)
  -R ROGUE_AGENTS, --rogue-agents ROGUE_AGENTS
                        This makes N columns randomly go twice as fast
                        (Default: 0)
  --spaces-abs-min-height SPACES_ABS_MIN_HEIGHT
                        Minimum height of vertical spaces (Default: 5)
  --spaces-abs-max-height SPACES_ABS_MAX_HEIGHT
                        Maximum height of vertical spaces (Default: 35)
  --spaces-rel-max-height SPACES_REL_MAX_HEIGHT
                        Maximum height of vertical spaces, relative to the
                        terminals height (--spaces-abs-max-height will
                        override this value if it is lower) (Default: 0.8)
  --strings-abs-max-height STRINGS_ABS_MAX_HEIGHT
                        Maximum height of vertical strings (Default: 25)
  --strings-abs-min-height STRINGS_ABS_MIN_HEIGHT
                        Minimum height of vertical strings. Cannot be lower
                        than 5 (Default: 5)
  --strings-rel-max-height STRINGS_REL_MAX_HEIGHT
                        Maximum height of vertical strings, relative to the
                        terminals height (--strings-abs-max-height will
                        override this value if it is lower) (Default: 0.6)
  --vertical-cache VERTICAL_CACHE
                        Advanced: Vertical cache. The bigger you set this to,
                        the more time passes before anything repeats, but it
                        requires more ram and will require more time to
                        calculate on startup. You should probably leave this
                        value alone (Default: 7)
```

## About

* Tested in Python >= `3.7.3`.
* Best used with a 16 color terminal and a font plus terminal that handles bold characters.
* Made mainly for Linux - might work on Mac, no guarantees because I don't have access to one.
* Best used with the [Matrix Code NFI Font](https://www.dafont.com/matrix-code-nfi.font).
    - Bold characters with this font will not work, but it still looks pretty good.
* Loaded libraries: `argparse` `curses` `time` `signal` `sys` `random` `pprint`.

## Performance

It's not bad, it depends mostly on your terminal size and what you set `--fps` to, and of course a decent computer. It will consume around 25 MB of ram, 33% of a modern dual-core cpu, on a fullscreen terminal in a 1920 by 1080 pixel workspace. On a normal sized terminal it's more like _14 MB_ and `14%` cpu usage.

This __is__ heavier than the original [cmatrix](https://github.com/abishekvashok/cmatrix). Can't be helped.

I have really tried to make it faster, but I think I have squeezed all the performance I can out of it, for now.

## Other notes

This is my first ever python script, so be kind when commenting! At the time I'm writing this I've only been exposed to python for a week.
