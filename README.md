# Ansible Role: Composer

[![Ansible Galaxy](http://img.shields.io/badge/galaxy-novuso.composer-000000.svg)](https://galaxy.ansible.com/list#/roles/3814)
[![MIT License](http://img.shields.io/badge/license-MIT-003399.svg)](http://opensource.org/licenses/MIT)

An Ansible role that manages PHP Composer on Ubuntu 14.04

## Requirements

Composer requires PHP 5.3.2 or greater and commonly included extensions.

See the
[installer](https://github.com/composer/getcomposer.org/blob/master/web/installer)
for more information.

## Role Variables

`composer_local_dir` sets the directory for the local `composer.phar` download.
If `composer_global_install` is true, the file is downloaded here before it is
moved.

    composer_local_dir: "/home/{{ ansible_user_id }}"

`composer_global_path` is the absolute path to the global composer executable.

    composer_global_path: "/usr/local/bin/composer"

`composer_global_install` flags whether or not to install composer globally.

    composer_global_install: true

`composer_keep_updated` flags whether or not to run `composer self-update` to
keep composer update-to-date.

    composer_keep_updated: true

## Dependencies

None

## Example Playbook

    ---
    - hosts: all
      vars:
      - composer_local_dir: "/path/to/project"
      - composer_global_install: false
      roles:
      - novuso.composer

## License

This is released under the [MIT license](http://opensource.org/licenses/MIT).
