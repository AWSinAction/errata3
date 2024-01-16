+++
date = "2024-01-16"
draft = false
title = "linkchecker dependencies broken"
section = "3.1.3"
page = 72
+++

> pip3 install linkchecker

Should be:

> pip3 install linkchecker
> pip3 uninstall urllib3
> pip3 install 'urllib3<2.0'
