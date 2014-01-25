heroku-buildpack-imageoptim
===========================
This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for using multiple utilities to optimize images in your project.
It is suited for [image_optim gem](https://github.com/toy/image_optim).

It doesn't do anything else, so to actually compile your app you should use [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi) to combine it with a real buildpack.

Included utilities
------------------
This buildpack inclues the following utilities:

- [advpng](http://advancemame.sourceforge.net/doc-advpng.html) from [AdvanceCOMP](http://advancemame.sourceforge.net/comp-readme.html)
- [gifsicle](http://www.lcdf.org/gifsicle/)
- [jhead](http://www.sentex.net/~mwandel/jhead/)
- [jpegoptim](http://www.kokkonen.net/tjko/projects.html)
- jpegtran from [libjpeg-turbo](http://libjpeg-turbo.virtualgl.org/)
- [optipng](http://optipng.sourceforge.net/)
- [pngcrush](http://pmt.sourceforge.net/pngcrush/)

Because of the license, [pngout](http://www.advsys.net/ken/util/pngout.htm) is not included.

Usage
-----
To use this buildpack, you should prepare .buildpacks file that contains this buildpack url and your real buildpack url.

    $ ls
    .buildpacks
    ...

    $ cat .buildpacks
    https://github.com/poppen/heroku-buildpack-imageoptim

    $ heroku create --buildpack https://github.com/ddollar/heroku-buildpack-multi

    $ git push heroku master
    ...

