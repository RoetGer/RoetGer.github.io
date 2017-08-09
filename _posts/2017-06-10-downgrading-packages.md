---
layout: post
title: Telling APT to downgrade packages
comments: true
category: Programming
tags: Linux
---

APT does not automatically downgrade packages, this can hinder sometimes its ability 
to resolve dependency issues on its own.

In case that you want to allow downgrades, the user Gilles has posted the necessary 
steps onto stackexchange:
(https://unix.stackexchange.com/questions/218911/help-me-repair-my-python-i-think-dpkg-has-to-be-reset-very-tricky-issue)

Just create a file `allow-downgrade` in the directory `/etc/apt/preferences.d/` and enter:

'''bash
Package: *
Pin: release o=Ubuntu
Pin-Priority: 1001
'''

This will allow APT to downgrade packages in order to resolve dependency issues.
