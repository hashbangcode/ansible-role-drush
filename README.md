# Ansible Role: Drush

An Ansible role that installs [Drush](https://github.com/drush-ops/drush) on Linux.

Supports global installation via Composer or via packaged download (faster).

## Requirements

- Composer (only required if installing via Composer rather than from a packaged download).
- PEAR (only required to install Drush 6 & below).


## Role Variables

Available variables are listed below, along with their default values (see defaults/main.yml):

### Common variables

    drush_install_path: /usr/local/share/drush

The location of the entire drush installation (includes all the supporting files, as well as the drush executable file.

    drush_path: /usr/local/bin/drush

The path where drush will be installed and available to your system. Should be in your user's $PATH so you can run commands simply with `drush` instead of the full path.

    drush_version: 8.1.0

The version of Drush to install (examples: "8.0.2", "7.x", "7.1.0", "master"). This should be a string as it refers to a git branch, tag, or commit hash.

    drush_prefer_packaged_download: true

If set to `true`, the role will attempt to install Drush from a downloaded .phar file. Note that .phar files are only available through later releases of Drush and will require `drush_version` to be set to `8.0.0-rc3` or higher.

### The following variables only apply to installation via Composer

    drush_composer_path: /usr/local/bin/composer

Path to where Composer is installed.

    drush_keep_updated: no

Whether to keep Drush up-to-date with the latest revision of the branch specified by drush_version.


## Dependencies

None.


## Example Playbook

    - hosts: servers
    roles:
      - { role: hashbangcode.pantheon-cli }


## License

MIT


## Author Information

This role was created by [Dan Bohea](http://bohea.co.uk) originally for use with [Vlad](https://github.com/hashbangcode/vlad).

Hat tip to @geerlingguy. Some of this role is based on [his Drush role](https://github.com/geerlingguy/ansible-role-drush).
