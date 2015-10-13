---
layout: post
comments: true
published: true
title: Clearing DNS Cache in OSX El Capitan
---


I can never remember the terminal command to clear my DNS cache, so I'm posting it here. If you need to flush the DNS in OSX 10.11, use the following command on the terminal:

    sudo dscacheutil -flushcache;sudo killall -HUP mDNSResponder;say "cache flushed"
