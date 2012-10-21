## Web-Mote

This is a currently Python, web-based interface for MPlayer I put together because I felt like controlling my RasPi-based media center with an iPod touch that serves no other purpose.

The latest re-write of the system was done for the purposes of exploring some UI construction techniques. Writeups available in

[Part 1](http://langnostic.blogspot.ca/2012/10/webmote-right-way.html) and [Part 2](http://langnostic.blogspot.ca/2012/10/webmote-right-way-part-2-or-controlling.html)

#### Usage

1. install the dependencies
2. run `python web-mote.py`
3. navigate to `http://[machine ip]:8080` to use the remote menu

You can select a port other than `8080` by passing an argument to your script (for example, `python web-mote.py 4343` would start it on port `4343`). You can run it in the background using GNU Screen. Assuming you have it installed, you start a background server with `screen -d -m -S web-mote python web-mote.py`, attach to it using `screen -r web-mote` and detach with `Ctrl+a Ctrl+d`.

Like I said, it's meant to be used through my iPod touch, so the stylesheet is specifically crafted to fit the width of the screen and be readable at that size. If you're using another device, you may need to play with the .css file.

#### Dependencies

- [Python 2.7](http://python.org/download/releases/2.7/)
- [mplayer](http://www.mplayerhq.hu/design7/news.html)
- OPTIONALLY [omxplayer](https://github.com/huceke/omxplayer) *if you're on [Raspbian](http://www.raspbian.org/), you already have this. If you're not, you probably don't need it.*
- OPTIONALLY [GNU Screen](http://www.gnu.org/software/screen/) *you'll need this or similar to run web-mote in the background*
- Python [web.py](http://webpy.org/) module

If you're on Debian or Raspbian, you can install everything you need by running the following as `root`:

    apt-get install mplayer screen python-setuptools
    easy_install web.py

#### Licensing/Components
*(Why is this always the longest section?)*

This program is released under the GNU AGPL (check the `LICENSE` file for details).

The front-end uses [Twitter Bootstrap](https://github.com/twitter/bootstrap) for styling and icons, which is released under the [Apache License](https://github.com/twitter/bootstrap/blob/master/LICENSE)

A previous version used artwork from the [famfamfam SILK Icon set](http://www.famfamfam.com/lab/icons/silk/), which are released under [CC-BY 2.5](http://creativecommons.org/licenses/by/2.5/)

A previous version used artwork from [lucamennoia's media player icons piece](http://lucamennoia.deviantart.com/art/CustomMediaPlayer-icon-buttons-174712679) (released under [CC-NC-SA](http://creativecommons.org/licenses/by-nc-sa/3.0/), so I didn't even need to attribute them, but I'm cool that way).

The folder/video/audio/image icons are from the [Crystal Clear set](http://commons.wikimedia.org/wiki/Crystal_Clear) (released under [LGPL](http://www.gnu.org/licenses/lgpl.html)).

A copy of [jQuery](http://jquery.com/) and [jQueryUI](http://jqueryui.com/) are included for ease of use. Both are [dual-licensed under GPL and MIT-style licenses](http://jquery.org/license/).

The system uses [backbone.js](http://backbonejs.org/) (and therefore also [underscore.js](http://underscorejs.org/)) for the purposes of internal routing. Both are released under the [MIT-style Expat license](https://github.com/documentcloud/backbone/blob/master/LICENSE)

[handlebars.js](http://handlebarsjs.com/) is used for HTML templating. It is released under an [MIT-style Expat license](https://github.com/wycats/handlebars.js/blob/master/LICENSE).
