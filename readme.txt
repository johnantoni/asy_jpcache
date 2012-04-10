asy_jpcache is Full Page Caching for Textpattern1.0 rev.300 and up (including RC5).

Install asy_jpcache.txt in the Admin-Panel, and click on _help_ to view the installation instructions.

Installation
----------------

1. Copy the directory jpcache and its contents into your main directory. It should be right next to your images and your textpattern directory (on a default install).
Make sure that the jpcache/cache directory can be written to. Usually chmod 777 jpcache/cache/ will do the trick.
2. Edit your index.php in the main directory and before include txpath.'/publish.php'; insert the following line: include './jpcache/jpcache.php'; (IMPORTANT: do NOT edit textpattern/index.php )
3. Don’t forget to activate this Admin-plugin.
4. Optional: Look inside jpcache/jpcache-config.php to change a few settings, like enabling Debugging, permanently turning off gzip-encoding, change timout etc.


Version History
----------------
- Merge Adam Messinger's aam_zcr_clearcache plugin to allow co-operation with ZCR.
- Add privs to allow admin extension tab to be accessed.
- Bugfix: remove invalid index: view notice
- Bugfix: don't cache file downloads
0.9.8
- updated installation instructions
- minor fixes
- removed statistics on read-write ratio
0.9.5
- added option to enable txp's logging (defaults to off)
- clean cache on editing links
- extended help section in admin-plugin
- added statistics on read-write-ratio in admin-plugin
(only if logging is enabled in jpcache and set to 'all' in Textpattern)
0.9 (non-public release)
- added option to skip caching for feeds (defaults to off)
- skip caching of feeds if the request can result in partial content (A-IM/feed, RFC3229)
- skip caching when there is too little content (for example when doing redirects)
- added some code & explanation to hack in application/xhtml+xml support
- added Content-Length header
0.8
- don't clean cache when merely viewing or previewing articles in article-event
- add statistic in admin-side plugin over number and total size of the cache-files
- sniff content and guess Content-Type on PHP4 (see Known Issues)
- finally, completely fix garbled feeds. (strncmp returns 0 for a match, go figure...)
0.7.1 repackaged 0.7. The admin-side plugin was corrupted and could not be installed.
0.7 fixed garbled output of feeds (they were compressed twice), added a missed article hook.
0.6 used headers_list (only PHP5) if apache_get_headers (only SAPI) not available
0.5 initial release

--------------------------------

THIS SOFTWARE IS PROVIDED AS IS AND FOR FREE. THE AUTHOR DISCLAIMS ANY AND ALL FITNESS FOR A PARTICULAR PURPOSE. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY DAMAGES WHATSOEVER ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE.
