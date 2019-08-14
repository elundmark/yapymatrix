# Yet Anoter Python Matrix

![Preview](https://i.imgur.com/fs7BZOm.png)

[https://giphy.com/gifs/matrix-lrIeTla9JsxCwn9QX1](https://giphy.com/gifs/matrix-lrIeTla9JsxCwn9QX1)
Direct GIF link: [https://media.giphy.com/media/lrIeTla9JsxCwn9QX1/giphy.gif](https://media.giphy.com/media/lrIeTla9JsxCwn9QX1/giphy.gif)

## Why

Yes, it's yet another matrix code generator.

I couldn't find any other ones with the right colors, flow, and options, so I wrote my own. Enjoy!

## Options

Here's the current list of options.

Better documentation will be added later.

```
--fps                           # Default: 12
--force-black                   # Default: False
--no-colors                     # Default: False
--tv-intro                      # Default: False
--sparse-columns                # Default: False
--very-sparse-columns           # Default: False
--spaces-abs-max-height=INT     # Default: 35
--strings-abs-max-height=INT    # Default: 25
--spaces-rel-max-height=FLOAT   # Default: 0.8
--strings-rel-max-height=FLOAT  # Default: 0.8
--include-spaces=INT            # Default: 2
--onscreen-letters-timer=INT    # Default: 4
--show-options                  # Useful for debugging
--help                          # Show all options
```

## Required / Tested on

* Linux
* Best used with [Matrix Code NFI](https://www.dafont.com/matrix-code-nfi.font)
* Python >= 3.7.3
* Loaded libraries:
	- curses
	- time
	- signal
	- sys
	- random

## Usage

```
chmod u+x yapymatrix
./yapymatrix [ options ]
```

To stop the program, use `Ctrl + C`

## Performace

It's not bad. On a 1920x1080 fullscreen terminal (213 cols x 57 lines) and the default speed, my 2015 laptop i5 processor (4 threads) uses about 22%. This is heavier than say [cmatrix](https://github.com/abishekvashok/cmatrix).
