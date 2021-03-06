Ansible Role: docker-selenium
=========

[![Build Status](https://travis-ci.org/jpparsons/ansible-role-docker-selenium.svg)](https://travis-ci.org/jpparsons/ansible-role-docker-selenium)
[![Ansible Galaxy](https://img.shields.io/badge/galaxy-jpparsons.docker-blue.svg)](https://galaxy.ansible.com/detail#/role/6268)
[![GitHub Tags](https://img.shields.io/github/tag/jpparsons/ansible-role-docker-selenium.svg)](https://github.com/jpparsons/ansible-role-docker-selenium)

An Ansible Role that runs selenium docker images built by [SeleniumHQ](https://github.com/SeleniumHQ/docker-selenium).

Requirements
------------

A host system that has Docker installed.

Role Variables
--------------

- __docker_selenium_version__: the selenium release version, default is 2.45.0. See [SeleniumHQ](https://github.com/SeleniumHQ/docker-selenium) for more recent releases.
- __docker_selenium_hub_name__: logical name for the hub, default is selenium-hub.
- __docker_selenium_hub_port__: the hub port mapping between host and container, default 4444:4444.
- __docker_selenium_hub_image__: selenium hub image name in DockerHub.
- __docker_selenium_firefox_image__: selenium node image for firefox in DockerHub.
- __docker_selenium_chrome_image__: selenium node image for chrome in DockerHub.
- __docker_selenium_hub_link__: the hub link for nodes to link with.
- __docker_selenium_firefox_nodes__: the number of firefox container nodes to run.
- __docker_selenium_chrome_nodes__: the number of chrome container nodes to run.
- __docker_selenium_pull_image__: check docker registry for image, default is to pull if missing.
- __docker_selenium_state__: default is started, use reloaded for changes made.

Dependencies
------------

None.

Example Playbook
----------------

Run a specific version of selenium specifying the number of nodes and using debug containers:

    - hosts: servers
      roles:
         - { role: jpparsons.docker-selenium, docker_selenium_version: 2.46.0, 
                   docker_selenium_chrome_nodes: 5, docker_selenium_firefox_image: "selenium/node-firefox-debug",
                   docker_selenium_firefox_nodes: 5,  docker_selenium_chrome_image: "selenium/node-chrome-debug",
                   docker_selenium_state: "reloaded" }

License
-------

GPLv2

Author Information
------------------

John Parsons

Feedback, bug-reports, requests, ...
------------------
Are [welcome](https://github.com/jpparsons/ansible-role-docker-selenium/issues)!
