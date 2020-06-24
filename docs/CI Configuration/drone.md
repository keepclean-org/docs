---
layout: default
title: Drone
parent: CI Configuration
nav_order: 0
---

Add a keepclean step to your pipeline:

```yaml
- name: keepclean
  commands:
  - gem install keepclean
  - keepclean
  environment:
    KEEPCLEAN_TOKEN: your keepclean token
``` 
