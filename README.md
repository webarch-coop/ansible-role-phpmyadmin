# phpMyAdmin

This is an Ansible role to install [phpMyAdmin](https://www.phpmyadmin.net/),
using `git`, it has, so far, only been tested on Debian Buster using the [Alpha
version 5](https://github.com/phpmyadmin/phpmyadmin/releases). 

[Webarchitects](https://www.webarch.coop/) uses this role via the [users
role](https://git.coop/webarch/users/) which is in trun used by the [WSH
example repo](https://git.coop/webarch/wsh/).

For the configurable variables see [defaults/main.yml](defaults/main.yml).

To trigger the running of the `composer` and `yarn` tasks even when the
`phpmyadmin_version` hasn't changed you need to manually delete the
`phpmyadmin_version_file`.
