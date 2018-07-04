# ansible-role-rpmfusion

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-rpmfusion.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-rpmfusion)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-rpmfusion-blue.svg?style=flat)](https://galaxy.ansible.com/linuxhq/rpmfusion)
[![License](https://img.shields.io/badge/license-GPLv3-brightgreen.svg?style=flat)](https://github.com/linuxhq/ansible-role-rpmfusion/blob/master/COPYING)

RHEL/CentOS - RPM Fusion is a merger of Dribble, Freshrpms, and Livna

## Requirements

This role requires that you have the epel repository installed.

 * https://galaxy.ansible.com/linuxhq/epel/

## Role Variables

Available variables are listed below, along with default values:

    rpmfusion_baseurl: 'https://download1.rpmfusion.org'
    rpmfusion_dist: "{{ ansible_distribution_major_version }}"
    rpmfusion_disablerepo: []
    rpmfusion_enablerepo: []
    rpmfusion_packages: []
    rpmfusion_repository_free_updates: false
    rpmfusion_repository_free_updates_debuginfo: false
    rpmfusion_repository_free_updates_source: false
    rpmfusion_repository_free_updates_testing: false
    rpmfusion_repository_free_updates_testing_debuginfo: false
    rpmfusion_repository_free_updates_testing_source: false
    rpmfusion_repository_nonfree_updates: false
    rpmfusion_repository_nonfree_updates_debuginfo: false
    rpmfusion_repository_nonfree_updates_source: false
    rpmfusion_repository_nonfree_updates_testing: false
    rpmfusion_repository_nonfree_updates_testing_debuginfo: false
    rpmfusion_repository_nonfree_updates_testing_source: false

All repositories are disabled by default.

## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.rpmfusion
          rpmfusion_enablerepo:
            - epel
            - rpmfusion-free-updates
          rpmfusion_packages:
            - nrdp
            - snes9x
          rpmfusion_repository_free_updates: true

## License

Copyright (C) 2018 Taylor Kimball <tkimball@linuxhq.org>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <http://www.gnu.org/licenses/>.
