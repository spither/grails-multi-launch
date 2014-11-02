grails-multi-launch
===================

Grails launching script that transparently handles multiple grails versions.

This script will look for the requested or required grails version in `/usr/local/grails/grails-*` however if that doesn't exist it will use wget and unzip to automatically fetch the required version and store it in `~/.grails-multi/grails-*`.

This script will set the `GRAILS_HOME` environment variable before running grails.

Ideally `JAVA_HOME` should already be set, but if not the script will try to take a guess and set it for you.

Installation
============

Download the [script here](https://github.com/spither/grails-multi-launch/raw/master/grails), place it somewhere on your path (perhaps /usr/local/bin) and make it executable:

    sudo cp grails /usr/local/bin/
    sudo chmod +x /usr/local/bin/grails

Usage
=====

To force the grails version to be used, specify the version number as the first parameter:

    $ grails 2.2.0 create-app MyApp
    another-app$ grails 2.2.0 upgrade

Or just pretend it's the real grails command when within a project to auto-detect the version (from application.properties):

    my-app$ grails run-app
