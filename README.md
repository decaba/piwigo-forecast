piwigo-forecast
===============

**************************

Notes about this fork
---------------------

This is a fork of the [Piwigo-forecast](http://piwigo.org/ext/extension_view.php?eid=795) plugin for [Piwigo](http://piwigo.org/). It does two things:

* changes 24-hour display to 12-hour display with am/pm
* includes (below) instructions for taking advantage of the plugin's ability to use buffer.php to cache API requests to forecast.io

### Instructions for taking advantage of this plugin's ability to use buffer.php to cache API requests to forecast.io

1. Download [buffer.php](https://github.com/leo/buffer/blob/master/buffer.php) to the root of your piwigo directory.
2. Per [buffer's instructions](https://github.com/leo/buffer/blob/master/README.md), make sure the 'buffer.php' is included in your script and there's a folder called "cache" next to buffer's PHP-file. I put both in the root of my piwigo directory.
3. Adjust your web server's permissions so that buffer.php can write files to the cache directory.
4. Edit [piwigo_directory]/plugins/forecast/lib/forecast.io.php, find the section about buffer (around line 108), and uncomment the line that follows `// all good`. Optionally, change `$content = $cache->data($request_url);` to something like `$content = $cache->data($request_url, 300, 'cache');`.
5. Make sure buffer is initialized by adding to main.inc.php the following: `include_once(PHPWG_ROOT_PATH.'/buffer.php');`

***************************

Piwigo-forecast is a [plugin](http://piwigo.org/ext/extension_view.php?eid=795) for the [Piwigo](http://piwigo.org/) web gallery that display the weather condition from the location and time of you photos or videos for your gallery.

Installation
------------

Upload this in ``your-gallery/plugins/`` dir.

* download the archive from github

        wget -O piwigo-forecast.zip https://github.com/xbgmsharp/piwigo-forecast/archive/master.zip

        unzip piwigo-forecast.zip

        mv piwigo-forecast-master/ forecast

* or clone the project

        git clone git://github.com/xbgmsharp/piwigo-forecast.git forecast

Then, go to the admin site, in the plugin section and activate it.

Usage
-----

Enable the plugin and browse your gallery to photo with GPS location.

Please refer to the [wiki](https://github.com/xbgmsharp/piwigo-forecast/wiki) for additional information.

Support
-----

To get support, please create new [issue](https://github.com/xbgmsharp/piwigo-forecast/issues)

Help me improve the plugin, rate my [plugin](http://piwigo.org/ext/extension_view.php?eid=795), and if possible please send a greeting message to me ;)

Thanks
-----

* [forecast.io](http://forecast.io/)
* [skycons](https://darkskyapp.github.io/skycons/)

Licence
-------
The piwigo-forecast plugin for Piwigo is free software:  you can redistribute it
and/or  modify  it under  the  terms  of the  GNU  General  Public License  as
published by the Free Software Foundation.

This program  is distributed in the hope  that it will be  useful, but WITHOUT
ANY WARRANTY; without even the  implied warranty of MERCHANTABILITY or FITNESS
FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

See <http://www.gnu.org/licenses/gpl.html>.
