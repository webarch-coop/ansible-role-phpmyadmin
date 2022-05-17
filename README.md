# Webarchitects phpMyAdmin Ansible role

[![pipeline status](https://git.coop/webarch/phpmyadmin/badges/master/pipeline.svg)](https://git.coop/webarch/phpmyadmin/-/commits/master)

An Ansible role to install [phpMyAdmin](https://www.phpmyadmin.net/), using `git` on Debian Buster and Debian Bullseye.

This role automatically upgrades from the Debian packaged version of phpMyAdmin in Stretch, it hasn't been tested with the Debian packages version of phpMyAdmin in Debian Bullseye or Buster backports.

With [phpMyAdmin version 4.8.x and upwards](https://github.com/phpmyadmin/phpmyadmin/releases) two factor authentication is available and this is installed automatically.

This is role requires [Yarn](https://git.coop/webarch/yarn) and [Composer](https://git.coop/webarch/composer), [Webarchitects](https://www.webarch.coop/) uses this role via the [users role](https://git.coop/webarch/users/) which is in turn used by the [WSH example repo](https://git.coop/webarch/wsh/).

For the configurable variables see [defaults/main.yml](defaults/main.yml):

| Variable name           | Default value                        | Comment                                                                                                                                                        |
|-------------------------|--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `phpmyadmin_version`    | `latest`                             | Use a version number from [this page](https://github.com/phpmyadmin/phpmyadmin/releases) or `latest` to automatically install or upgrade to the latest version |
| `phpmyadmin_user`       | `www-data`                           | The phpMyAdmin user                                                                                                                                            |
| `phpmyadmin_group`      | `{{ phpmyadmin_user }}`              | The phpMyAdmin group                                                                                                                                           |
| `phpmyadmin_dbname`     | `phpmyadmin`                         | The phpMyAdmin MySQL / MariaDB database name                                                                                                                   |
| `phpmyadmin_dbuser`     | `phpmyadmin`                         | The phpMyAdmin MySQL / MariaDB user                                                                                                                            |
| `phpmyadmin_dbhost`     | `localhost`                          | The phpMyAdmin MySQL / MariaDB host                                                                                                                            |
| `phpmyadmin_dbport`     | `3306`                               | The phpMyAdmin MySQL / MariaDB port                                                                                                                            |
| `phpmyadmin_dbsocket`   | `/var/run/mysqld/mysqld.sock`        | The phpMyAdmin MySQL / MariaDB root connection socket                                                                                                          |
| `phpmyadmin_dbpass`     | ""                                   | This role doesn't create the database or set the database user password, see the [MariaDB role](https://git.coop/webarch/mariadb) for Ansible to do this       |
| `phpmyadmin_home`       | `"/var/www"`                         | The `$HOME` directory for the phpMyAdmin user                                                                                                                  |
| `phpmyadmin_private`    | `"{{ phpmyadmin_home }}"`            | The private directory where the blowfish secret for cookies will be saved as `.blowfish.secret`                                                                |
| `phpmyadmin_docroot`    | `"{{ phpmyadmin_home }}/phpmyadmin"` | The Apache `DocumentRoot` for phpMyAdmin                                                                                                                       |
| `phpmyadmin_tmp`        | `"/tmp"`                             | The `TMPDIR` to use                                                                                                                                            |
| `phpmyadmin_lang`       | `"en"`                               | The default language for phpMyAdmin                                                                                                                            |
| `phpmyadmin_deny_root`  | `true`                               | Deny the MySQL / MariaDB `root` user to login to phpMyAdmin                                                                                                    |
| `phpmyadmin_deny_users` | `- "{{ phpmyadmin_user }}"`          | An array of MySQL / MariaDB user names that are denied access to login to phpMyAdmin                                                                           |


The primary URL of this repo is [`https://git.coop/webarch/phpmyadmin`](https://git.coop/webarch/phpmyadmin) however it is also [mirrored to GitHub](https://github.com/webarch-coop/ansible-role-phpmyadmin) and [available via Ansible Galaxy](https://galaxy.ansible.com/chriscroome/phpmyadmin).

If you use this role please use a tagged release, see [the release notes](https://git.coop/webarch/phpmyadmin/-/releases).
