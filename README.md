# sent

sent is a simple plaintext presentation tool.

sent does not need latex, libreoffice or any other fancy file format, it uses
plaintext files to describe the slides and can include images via farbfeld.
Every paragraph represents a slide in the presentation.

The presentation is displayed in a simple X11 window. The content of each slide
is automatically scaled to fit the window and centered so you also don't have to
worry about alignment. Instead you can really concentrate on the content.

This repository holds my fork of Suckless's sent program with some patches applied.

## Applied Patches

- [progress bar](https://tools.suckless.org/sent/patches/progress-bar/)
- [toggle mouse cursor](https://tools.suckless.org/sent/patches/toggle_cursor/)
- [inverted colors](https://tools.suckless.org/sent/patches/inverted-colors/)
- [toggle scm](https://tools.suckless.org/sent/patches/toggle-scm/)

## Dependencies

You need Xlib and Xft to build sent and the [farbfeld](https://tools.suckless.org/farbfeld/) tools installed to use
images in your presentations.

## Demo

To get a little demo, just type

	make && ./sent example

You can navigate with the arrow keys and quit with `q`.


## Usage

	sent [FILE]

If FILE is omitted or equals `-`, stdin will be read. Produce image slides by
prepending a `@` in front of the filename as a single paragraph. Lines starting
with `#` will be ignored. A `\` at the beginning of the line escapes `@` and
`#`. A presentation file could look like this:

	sent
	
	@nyan.png
	
	depends on
	- Xlib
	- Xft
	- farbfeld
	
	sent FILENAME
	one slide per paragraph
	# This is a comment and will not be part of the presentation
	\# This and the next line start with backslashes
	
	\@FILE.png
	
	thanks / questions?


## Development

sent is developed at http://tools.suckless.org/sent
