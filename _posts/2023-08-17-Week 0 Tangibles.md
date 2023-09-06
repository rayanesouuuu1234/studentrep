---
toc: True
comments: True
layout: post
title: Week 0
description: 
courses: {'csp': {'week': 0}}
type: tangibles
---


**Ran:** $ sudo pip install yaml

**Error:** Downloading/unpacking yaml
Could not find any downloads that satisfy the requirement yaml
No distributions at all found for yaml
Storing complete log in /home/pa/.pip/pip.log

**Fixes:** 
- brew install libyaml
- sudo python -m easy_install pyyaml

Analysis: Apart from some pretty small mistakes in the proccess of downloading (upgrading to python3) languages, this was the one that I spent the most time on. The fix was found on a github page, and after experimenting w/ different commands, I finally got it fixed. 
