ansible-role-concourse-ci
===

[![GitHub release](https://img.shields.io/github/release/dbaba/ansible-role-concourse-ci.svg)](https://github.com/dbaba/ansible-role-concourse-ci/releases/latest)
[![master Build Status](https://travis-ci.org/dbaba/ansible-role-concourse-ci.svg?branch=master)](https://travis-ci.org/dbaba/ansible-role-concourse-ci/)
[![License MIT](https://img.shields.io/github/license/dbaba/candy-red.svg)](http://opensource.org/licenses/MIT)

This is an Ansible role for [Concourse CI](https://concourse.ci) running as Docker containers with Docker-Compose.

This role offers 1 web node and 1 worker node.

# Prerequisites

 * Ansible ... 2.0+
 * Vagrant ... 1.8+
 * Ruby    ... 2.0+ (tested version=2.3.1)

# Dependencies

 * [andrewrothstein.docker](https://galaxy.ansible.com/andrewrothstein/docker/)
 * [andrewrothstein.docker-compose](https://galaxy.ansible.com/andrewrothstein/docker-compose/)

# Setup
## For Evaluating Concourse CI

    git clone https://github.com/dbaba/ansible-role-concourse-ci.git
    cd ansible-role-concourse-ci
    vagrant up

Then open your browser, go to http://localhost:8080 (user:`concourse`/password:`ci`) and you can download `fly` binary there.

## For Development and running test-kitchen

    mkdir ansible-roles # this empty folder is used for installing dependencies by `ansible-galaxy`
    cd ansible-roles
    git clone https://github.com/dbaba/ansible-role-concourse-ci.git
    gem install bundler
    bundle install
    ansible-galaxy install -r requirements.yml

# Test
## Perform test with test-kitchen

    kitchen test

## Clear test VMs

    kitchen destroy

# Revision History
 * 1.0.1
    - Set the valid slack notification secured key
 * 1.0.0
    - Initial Release
