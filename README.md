# Ansible Role: PHP-XHProf

[![CI](https://github.com/geerlingguy/ansible-role-php-xhprof/actions/workflows/ci.yml/badge.svg)](https://github.com/geerlingguy/ansible-role-php-xhprof/actions/workflows/ci.yml)

Installs PHP [XHProf](http://php.net/manual/en/book.xhprof.php) on Linux servers.

> **Note**: The XHProf extension has been on life support since Facebook abandoned active development around 2015. There is a better-maintained fork that works on the latest PHP versions called Tideways, and there's an Ansible role for it—please check out [`geerlingguy.php-tideways`](https://github.com/geerlingguy/ansible-role-php-tideways) if you need to support modern PHP versions.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    workspace: /root

Where XHProf setup files will be downloaded and built.

    xhprof_version: "2.1.2"

The version of XHProf to download.

    xhprof_download_url: https://github.com/longxinH/xhprof/archive/v{{ xhprof_version }}.zip
    xhprof_download_folder_name: xhprof-{{ xhprof_version }}

The URL from which XHProf will be downloaded.

    xhprof_output_dir: /tmp

Directory where XHProf runs are stored.

    php_xhprof_lib_dir: /usr/share/php/xhprof_lib

Directory where the XHProf PHP library is stored.

    php_xhprof_html_dir: /usr/share/php/xhprof_html

Directory where the XHProf UI is stored.

## Dependencies

  - geerlingguy.php

## Example Playbook

    - hosts: webservers
      roles:
        - geerlingguy.php-xhprof

## License

MIT / BSD

## Author Information

This role was created in 2014 by [Jeff Geerling](https://www.jeffgeerling.com/), author of [Ansible for DevOps](https://www.ansiblefordevops.com/).
