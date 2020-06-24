---
layout: default
title: Travis
parent: CI Configuration
nav_order: 1
---

Install the gem in a `before_install` step then run the keepclean binary in a `script` step:

```yaml
language: ruby
rvm:
  - 2.5.3
before_install:
  - gem install keepclean
script:
  - keepclean
  - bundle exec rspec
```
