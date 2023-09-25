# gdb 和 pwntools 联合使用

```python
from pwn import *

r = process(["lib_name", "elf_name"])
gdb.attach(r, """
break breakpoint
break *0xadress
continue
""")

r.sendline(b"data")
r.interactive()

```