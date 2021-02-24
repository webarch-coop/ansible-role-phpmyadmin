# phpMyAdmin

An Ansible role to install [phpMyAdmin](https://www.phpmyadmin.net/), using
`git`, it has, so far, only been tested on Debian Buster, this role
automatically upgrades from the Debian packaged version in Stretch.

It hasn't yet be tested with the Debian packages version of phpMyAdmin in
Debian Bullseye or Buster Backports.

With [version 4.8.x upwards](https://github.com/phpmyadmin/phpmyadmin/releases)
two factor authentication is available and this is installed automatically.

This is role designed to be used with [Apache](https://git.coop/webarch/apache)
and requires [Yarn](https://git.coop/webarch/yarn) and Composer.

[Webarchitects](https://www.webarch.coop/) uses this role via the [users
role](https://git.coop/webarch/users/) which is in turn used by the [WSH
example repo](https://git.coop/webarch/wsh/).

For the configurable variables see [defaults/main.yml](defaults/main.yml).
