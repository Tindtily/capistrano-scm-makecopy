capistrano-scm-makecopy
===================

A copy strategy for Capistrano 3, which mimics the `:copy` scm of Capistrano 2.

This will make Capistrano tar the current directory, upload it to the server(s) and then extract it in the release directory.

This is a fork from [capistrano-scm-copy](https://github.com/wercker/capistrano-scm-copy). It only fixed an issue that the tar command ran twice. As the repository was archived, I had to start all over again.

Requirements
============

Machine running Capistrano:

- Capistrano 3
- tar

Servers:

- mktemp
- tar

Installation
============

First make sure you install the capistrano-scm-makecopy by adding it to your `Gemfile`:

    gem "capistrano-scm-makecopy"

Add to Capfile:

    require 'capistrano/makecopy'
    install_plugin Capistrano::SCM::MakeCopy

TODO
====

I'm new to programming for Capistrano and even Ruby in general. So any feedback is appreciated. 

License
=======

The MIT License (MIT)

Changelog
=========

0.8.4
-----

- Fix empty variable error

0.8.3
-----

- Fix require error

0.8.2
-----

- Update readme

0.8.1
-----

- Fix issue [Appears to try to upload archive file 2x](https://github.com/wercker/capistrano-scm-copy/issues/17)

0.5.0
-----

- Fix issue related to `tar_roles` (see wercker/capistrano-scm-copy#15)

0.4.0
-----

- Add support for `tar_roles` (see wercker/capistrano-scm-copy#8)

0.3.0
-----

- Fix issue when running on Mac OS X (see wercker/capistrano-scm-copy#9)
- Allow exclude directory to be an Array (see wercker/capistrano-scm-copy#9)

0.2.0
-----

- Add `exclude_dir`

0.1.0
-----

- Add `:include_dir`

0.0.2
-----

- Add `task :set_current_revision` 

0.0.1
-----

- Initial release
