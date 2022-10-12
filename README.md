# Grav .env Plugin

Simple [Grav](http://github.com/getgrav/grav) plugin that provides a simple way to load environment variables from .gravenv and override existing Grav configuration.

Uses [vlucas/phpdotenv](https://github.com/vlucas/phpdotenv) library for handling the env files.

> Note: this plugin was forked from [Jakob Kruse's original version](https://github.com/Ralla/grav-plugin-dotenv) after development was abandoned and is now maintained by the Grav Team.

# Installation

Installing the plugin can be done in one of two ways. Our GPM (Grav Package Manager) installation method enables you to quickly and easily install the plugin with a simple terminal command, while the manual method enables you to do so via a zip file. 

## GPM Installation (Preferred)

The simplest way to install this plugin is via the [Grav Package Manager (GPM)](http://learn.getgrav.org/advanced/grav-gpm) through your system's Terminal (also called the command line). From the root of your Grav install type:

    bin/gpm install dotenv

This will install the plugin into your `/user/plugins` directory within Grav. Its files can be found under `/your/site/grav/user/plugins/dotenv`.

## Manual Installation

To install this plugin, just download the zip version of this repository and unzip it under `/your/site/grav/user/plugins`. Then, rename the folder to `dotenv`.

You should now have all the plugin files under:

    /your/site/grav/user/plugins/dotenv

# Usage

In order to use the plugin, create the file `.gravenv` in the root of your project directory. Here's an example of overriding the existing system configuration:

Current contents of `system.yaml`file:

```
cache:
  enabled: true
twig:
  cache: tue
debugger:
  enabled: false
```

Contents of the `.gravenv` file:

```
system.cache.enabled=false
system.twig.cache=false
system.debugger.enabled=true
```

NOTE: some plugins or YAML variables might contain dashes (`-`). These are not valid in env syntax, so you can replace any `-` with `_DASH_` and the plugin will convert them back to `-` after reading the file.

For example, if you want to set a `active: false` to the configuration of the `lightbox-gallery` plugin you could put this in your config file:

```
plugins.lightbox_DASH_gallery.active=false
```

## Using a Different Env File

If you would prefer to use a file other than `.gravenv` (eg. `.env`) you can do the following:

1. Copy `user/plugins/dotenv/dotenv.yaml` to `user/config/plugins/dotenv.yaml`
1. Edit `user/config/plugins/dotenv.yaml` and change the `filename:` option.
