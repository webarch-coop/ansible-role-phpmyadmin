# phpMyAdmin

An Ansible role to install [phpMyAdmin](https://www.phpmyadmin.net/), using
`git`, it has, so far, only been tested on Debian Buster, this role
automatically upgrades from the Debian packaged version in Stretch.

When [Version 5](https://github.com/phpmyadmin/phpmyadmin/releases) is used two
factor authentication is available, however it is currently an alpha release.

This is role designed to be used with [Apache](https://git.coop/webarch/apache)
and requires [Yarn](https://git.coop/webarch/yarn) and Composer.

[Webarchitects](https://www.webarch.coop/) uses this role via the [users
role](https://git.coop/webarch/users/) which is in turn used by the [WSH
example repo](https://git.coop/webarch/wsh/).

For the configurable variables see [defaults/main.yml](defaults/main.yml).

To trigger the running of the `composer` and `yarn` tasks even when the
`phpmyadmin_version` hasn't changed you need to manually delete the
`phpmyadmin_version_file`.
