# Yet Anoter Python Matrix

[![Preview](https://i.imgur.com/mLwIpXP.png)](https://i.imgur.com/LgHiLiA.png)

[https://giphy.com/gifs/matrix-lrIeTla9JsxCwn9QX1](https://giphy.com/gifs/matrix-lrIeTla9JsxCwn9QX1)

## Why

Yes, it's yet another matrix code generator. [Cmatrix](https://github.com/abishekvashok/cmatrix) is one of my favorite programs, but after a few days learning Python I thought to myself, "Hey I could do this myself, maybe better, the right way". And I think I did okey.

I've gone back to the source material, and tried to really figure out how to make it look like the original. The beautiful thing is, if you don't agree with the result, you can change it to your own liking! :-)

## Options

Here's the current list of options. Change them by passing them one after each other as arguments:

```
$ yapymatrix --fps=21 --include-spaces=7 --very-sparse-columns
```

| Option                         |  Type     |  Default |  Comment          |
|--------------------------------|:---------:|:--------:|:-----------------:|
| --fps=N                        |  integer  |  21      |                   |
| --force-black                  |  boolean  |  False   |                   |
| --no-colors                    |  boolean  |  False   |                   |
| --random-bold                  |  integer  |  8       |                   |
| --no-bold-characters           |  boolean  |  False   |                   |
| --tv-intro                     |  boolean  |  False   |                   |
| --sparse-columns               |  boolean  |  False   |                   |
| --very-sparse-columns          |  boolean  |  False   |                   |
| --spaces-abs-min-height=N      |  integer  |  5       |                   |
| --spaces-abs-max-height=N      |  integer  |  35      |                   |
| --spaces-rel-max-height        |  float    |  0.8     |                   |
| --strings-abs-max-height=N     |  integer  |  25      |                   |
| --strings-abs-min-height=N     |  integer  |  5       |                   |
| --strings-rel-max-height       |  float    |  0.6     |                   |
| --include-spaces=N             |  integer  |  3       |                   |
| --onscreen-letters-timer=N     |  integer  |  4       |                   |
| --show-options                 |  boolean  |          |  Debugging tool   |
| --help                         |  boolean  |          |  Show all options |

### `--fps=N` _int_

Frames per second. Any integer __or float__ can be passed, it will then be calculated as `1 / fps` and used as seconds to `sleep` between reflows. If a value over `60` is passed, `sleep` will be omitted.

_Default: 21_

### `--force-black` _boolean_

Color all backgrounds black. Normally your terminals default color-scheme will be used.

_Default: False_

### `--no-colors` _boolean_

Do not use any colors. Speeds up things quite a bit, so think of using this if you are using something like `cool-retro-term`.

_Default: False_

### `--random-bold=N` _integer_

Make characters bold by a random chanse of 1 in N. Making this `0` will _not_ turn off bold characters completely.

_Default: 8_

### `--no-bold-characters` _boolean_

Turn off all use of bold characters.

_Default: False_

### `--tv-intro` _boolean_

This skips a step when the program starts, and it will look more like an old crt television warming up. It started out a a bug, but now I kinda like it, so I made it an optional extra.

_Default: False_

### `--sparse-columns | --very-sparse-columns` _boolean_

This will skip every other / or third column, to make it look a little lighter. Works well on bigger screens. Plus it speed up things a bit.

_Default: False_

### `--*-(abs|rel)-(min|max)-height=N` _integer_

These values will decide how long a string of characters or spaces can be. Absolute minimum height of strings cannot be less than 5, but other than that you can set this to whatever you want. `*-rel-*` means relative to the terminals height. The lowest of these values will then be applied.

_Default: see table above_

### `--include-spaces=N` _integer_

The original matrix code has spaces included in the strings, which I don't think I've seen in other versions. Experimenting with this value will increase the amount it will "sparkle", or set it to 0 to disable spaces entirely.

_Default: 3_

### `--onscreen-letters-timer=N` _integer_

This might be the most important part imo, how long should the characters "stick" in one place? The number represents the maximum amount of times it shows before it is replaced. Randomness is introduced to make it look organic.

_Default: 4_

## Required / Recommended / Tested on

* Made for Linux - might work on Windows/Mac, no guarantees because I don't have access to any of those OS's
* Best used with [Matrix Code NFI](https://www.dafont.com/matrix-code-nfi.font)
* Best used with a 16 color terminal
* Also works fine on monochrome terminals
* Tested in Python >= 3.7.3
* Loaded libraries: __curses__ , __time__ , __signal__ , __sys__ , __random__

## Usage

```sh
git clone https://github.com/elundmark/yapymatrix.git
cd yapymatrix/
chmod u+x yapymatrix
./yapymatrix [ options ]
```

To stop the program, use `Ctrl + C`. I am not planning on adding keyboard shortcuts, but who knows what happens in the future.

## Performance

It's not, bad.

It's not killing my 2015 laptop i5 processor with 4 threads, but it does require a lot of cpu-time, depending of the size and speed.

* Will consume around _25_ MB of ram, `33%` of a modern dual-core cpu, @ `1920` x `1080`
* On a normal sized terminal it's more like _14 MB_ and `14%` cpu usage.

This __is__ heavier than the original [cmatrix](https://github.com/abishekvashok/cmatrix).

I have really tried to make it faster, but I think I have squeezed all the performance I can out of it.

## TODO's

* Add a 1-3 wide random "rogue" column that goes 2x or 3x as fast, as an option. Shouldn't be that hard to implement.
* Testing testing testing.
* Spell-checking.

## Also

This is my first ever python script, so be kind when commenting! At the time I'm writing this I've only been exposed to python for a week.
