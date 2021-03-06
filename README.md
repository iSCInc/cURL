# curl

[![Build Status](https://travis-ci.org/iSCInc/cURL.svg?branch=master)](https://travis-ci.org/iSCInc/cURL)

  > Collects all versions of [**cURL**](http://curl.haxx.se/download/curl-7.38.0.zip) on *iSC Inc.*.

## Install:
1. `git submodule init`
2. `git submodule add https://github.com/Krinkle/ts-krinkle-basetool.git lib/basetool`

* Copy `sample-local.php` and rename to `local.php`
* Fill in paths for the needed directories (and create them if needed). Keep in mind that the PHP script
  needs to be able to write, read and remove files from these directories.
  In the case of `cacheDir`, it needs to be able to create directories as well.
* Make sure the path of `mediawikiCoreRepoDir` points to a mediawiki core checkout:<br>
  `git clone https://gerrit.wikimedia.org/r/p/mediawiki/core.git mediawiki-core`
* Run:<br>
  `php scripts/updateSnaphots.php`
* Symlink `{cacheDir}/snapshots` to `./public_html/builds`
* Schedule updateSnaphots.php to run hourly<br>
   `0 * * * * php /path/to/mw-tool-snapshots/scripts/updateSnaphots.php > {logsDir}/updateSnaphots.log 2>&1`
* Symlink `./public_html` to be or to be inside of `/path/to/public_html`
