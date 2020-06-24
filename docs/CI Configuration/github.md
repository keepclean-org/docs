---
layout: default
title: Github
parent: CI Configuration
nav_order: 2
---

Add a keepclean action to your github project:

```yaml
name: KeepClean

on: pull_request

jobs:
  keepclean:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v2
    - name: Setup System
      run: |
        sudo apt-get install libsqlite3-dev
    - uses: ruby/setup-ruby@v1
      with:
        ruby-version: '2.5.3'
    - name: Bundler
      run: |
        gem install bundler -v '~> 1'
        bundle install
    - name: KeepClean
      run: |
        gem install keepclean
        keepclean
      env:
        KEEPCLEAN_TOKEN: ${{{ secrets.KEEPCLEAN_TOKEN }}}
``` 
