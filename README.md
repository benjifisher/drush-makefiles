# drush-makefiles
A configuration file for creating a Drupal site using "drush make"

Drupal is an open-source Content Management System (CMS) written in PHP:  see
https://www.drupal.org/ .

Drush is a command-line interface (CLI) for managing Drupal:  see https://github.com/drush-ops/drush .

An easy way to spin up a new Drupal site is to to use the `drush make`
subcommand.  A typical invocation is
```
$ mkdir /var/www/mysite
$ drush make --prepare-install site.make /var/www/mysite
```
This will download and install Drupal in the directory `/var/www/mysite`,
along with contributed modules and themes and external libraries, as specified
in the configuration file `site.make`.

Older versions of drush support an info-style format for `site.make`, similar
to the format of Drupal `.info` files before Drupal 8.  More recent versions
of drush support both that format and YAML.

I am starting this repository with makefiles in both formats, using a copy of
the configuration file I used for the site http://200doc.org .  My plan is to
update the YAML version of the file as I start new projects.  If I create a
new site this way, I will tag the version of `site.yml` that I use.  If I
decide that a particular site needs some contrib modules that I do not want to
include in most sites, then I can create a branch for that project.

## Contributed modules and themes

As of this writing, my makefile specifies the following contributed modules:

### Views-related modules:
- [Date](https://www.drupal.org/project/date)
- [Entity](https://www.drupal.org/project/entity)
- [Entityreference](https://www.drupal.org/project/entityreference)
- [Link](https://www.drupal.org/project/link)
- [Views](https://www.drupal.org/project/views)

### Media-related modules:
- [File entity](https://www.drupal.org/project/file_entity)
- [Media youtube](https://www.drupal.org/project/media_youtube)
- [Media](https://www.drupal.org/project/media)

### Features-related modules, for managing configuration:
- [Diff](https://www.drupal.org/project/diff)
- [Features](https://www.drupal.org/project/features)
- [Strongarm](https://www.drupal.org/project/strongarm)

### API modules, required by other modules:
- [Ctools](https://www.drupal.org/project/ctools)
- [Libraries](https://www.drupal.org/project/libraries)
- [Token](https://www.drupal.org/project/token)

### Other modules I like to use:

- [Content access](https://www.drupal.org/project/content_access)
- [Devel](https://www.drupal.org/project/devel)
- [Fences](https://www.drupal.org/project/fences)
- [Mollom](https://www.drupal.org/project/mollom)
- [Navbar](https://www.drupal.org/project/navbar)
- [Pathauto](https://www.drupal.org/project/pathauto)
- [Wysiwyg](https://www.drupal.org/project/wysiwyg)

### Base theme:

- [Zen](https://www.drupal.org/project/zen)

## External libraries

As of this writing, my makefile specifies the following external libraries:

- [backbone](http://backbonejs.org/backbone-min.js)
- [ckeditor](http://download.cksource.com/CKEditor/CKEditor/CKEditor%204.4.7/ckeditor_4.4.7_standard.zip)
- [mediaelement](http://github.com/johndyer/mediaelement/zipball/master)
- [modernizr](http://modernizr.com/e8a28f6b-fa15-ac47-8f9b-ec7ae832b542)
- [underscore](https://github.com/jashkenas/underscore/archive/1.5.2.zip)

Three of these are required for the Navbar (responsive toolbar) module.  The
mediaelement library is useful for the Media module.
