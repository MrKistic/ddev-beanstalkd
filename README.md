[![tests](https://github.com/mrkistic/ddev-beanstalkd/actions/workflows/tests.yml/badge.svg)](https://github.com/mrkistic/ddev-beanstalkd/actions/workflows/tests.yml)

## What is this?

This repository allows you to quickly install [beanstalkd](https://beanstalkd.github.io/) into a [DDEV](https://ddev.readthedocs.io) project using just `ddev get mrkistic/ddev-beanstalkd`.

## Installation

1.`ddev get mrkistic/ddev-beanstalkd && ddev restart`

## Explanation

This beanstalkd recipe for [ddev](https://ddev.readthedocs.io) installs [`.ddev/docker-compose.beanstalkd.yaml`](docker-compose.beanstalkd.yaml) which uses the `rayyounghong/beanstalkd` docker image.

This image *does* support arm64. See full supported OS/ARCH list at [Docker Hub](https://hub.docker.com/r/rayyounghong/beanstalkd/tags).

## Interacting with beanstalkd

* The beanstalkd instance will listen on TCP port 11300 (the beanstalkd default).
* Configure your application to access beanstalkd on the host:port `beanstalkd:11300`.
* To reach the beanstalkd admin interface, run ddev ssh to connect to the web container, then use nc or telnet to connect to the beanstalkd container on port 11300, i.e. nc beanstalkd 11300. 
