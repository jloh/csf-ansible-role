# Change Log

## [v1.3.0](https://github.com/jloh/csf-ansible-role/tree/v1.3.0) (2016-12-28)
[Full Changelog](https://github.com/jloh/csf-ansible-role/compare/v1.2.0...v1.3.0)

**Fixed bugs:**

- Case insensitive comparison for firewalld [\#12](https://github.com/jloh/csf-ansible-role/pull/12) ([gjedeer](https://github.com/gjedeer))

## [v1.2.0](https://github.com/jloh/csf-ansible-role/tree/v1.2.0) (2016-12-22)
[Full Changelog](https://github.com/jloh/csf-ansible-role/compare/v1.1.0...v1.2.0)

**Implemented enhancements:**

- Move custom commands to Ansible modules [\#11](https://github.com/jloh/csf-ansible-role/pull/11) ([jloh](https://github.com/jloh))

**Merged pull requests:**

- Fix CI builds after \#9 [\#10](https://github.com/jloh/csf-ansible-role/pull/10) ([jloh](https://github.com/jloh))
- Add ability to add ignore IPs and enabled blacklists [\#9](https://github.com/jloh/csf-ansible-role/pull/9) ([rainbow-goblin](https://github.com/rainbow-goblin))

## [v1.1.0](https://github.com/jloh/csf-ansible-role/tree/v1.1.0) (2016-11-02)
[Full Changelog](https://github.com/jloh/csf-ansible-role/compare/v1.0.0...v1.1.0)

**Implemented enhancements:**

- Added new global variable: csf\_allow\_ip [\#7](https://github.com/jloh/csf-ansible-role/pull/7) ([marek-knappe](https://github.com/marek-knappe))

**Fixed bugs:**

- Fix DEPRECATION WARNING errors due to bare variables [\#7](https://github.com/jloh/csf-ansible-role/pull/7) ([marek-knappe](https://github.com/marek-knappe))

## [v1.0.0](https://github.com/jloh/csf-ansible-role/tree/v1.0.0) (2016-02-27)
**Implemented enhancements:**

- Added CentOS 7 support. Added optional ipset and gd support [\#2](https://github.com/jloh/csf-ansible-role/pull/2) ([bvansomeren](https://github.com/bvansomeren))

**Fixed bugs:**

- Only fail disable firewalld when it's actually installed. [\#5](https://github.com/jloh/csf-ansible-role/pull/5) ([ju5t](https://github.com/ju5t))
- Minor addition to avoid changed result on csf installation check [\#3](https://github.com/jloh/csf-ansible-role/pull/3) ([dledanseur](https://github.com/dledanseur))

**Merged pull requests:**

- Add a Gitter chat badge to README.md [\#1](https://github.com/jloh/csf-ansible-role/pull/1) ([gitter-badger](https://github.com/gitter-badger))
