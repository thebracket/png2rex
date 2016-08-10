# rex2png - a utility for converting PNG files into REXPaint files

This is a simple utility I needed for [Black Future](https://github.com/thebracket/bgame) to convert PNG files into REXPaint format.
It handles transparency, and translucency with appropriate CP-467 tiles. It's pretty simple, but it does what I need. I hope
you find it useful!

## To build

This uses a standard CMake setup, and requires zlib and libpng. Typically:
 `mkdir build; cd build; cmake -g"Unix Makefiles" ../src; make` 
will get you going.

## Usage

`png2rex <inputfile> <outputfile`

For example:

`png2rex ../testimage/kitty.png kitty.xp`

You can then load the resulting image into your game, or with REXPaint.

**Original Kitty PNG**
![Original PNG of a kitty](https://raw.githubusercontent.com/thebracket/png2rex/master/testimage/kitty.png)

**REXPaint Kitty**
![REXPaint output](https://raw.githubusercontent.com/thebracket/png2rex/master/testimage/Kitty-REX.png)

*Credits*: 
* [REXPaint by Kyzrati of Grid Sage Games](http://www.gridsagegames.com/rexpaint/).
* REXPaint load/save provided with [REXSpeeder](https://github.com/pyridine/REXSpeeder)
* PNG Loader from [SantosDev](http://santosdev.blogspot.com/2012/08/loading-png-image-with-libpng-1512-or.html)
