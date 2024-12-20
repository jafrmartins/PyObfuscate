# PyObfuscate
**_The Easiest Way to Encrypt your .py files_**

## Installation to Local Folder using _PIP_

### Linux / MacOS

```console
user@machine:~$ pip install ./PyObfuscate --upgrade -t ~/.local/lib/<PYTHON>/site-packages/PyObfuscate
user@machine:~$ export PATH="~/.local/lib/<PYTHON>/site-packages/PyObfuscate/bin:$PATH"
```

### Windows
```console
user@machine:~$ pip install ./PyObfuscate --upgrade -t ~/.local/lib/<PYTHON>/site-packages/PyObfuscate
```

## CLI Usage
```console
user@machine:~$ pyobfuscate --help
usage: PyObfuscate [-h] SRC DEST MSG

A simple python obfuscator

positional arguments:
  SRC         Filepath to the file(s) to obfuscate
  DEST        Destination Folder
  MSG         Encoding Message

options:
  -h, --help  show this help message and exit
```

## API Usage
```python
from PyObfuscate.lib.framework import encrypt_file, encrypt_source, cyphers

src = "/path/to/file.py"
dest = "/path/to/dest.py"

encrypt_file(src, dest, varnames=["your", "message", "here"], cyphers=cyphers, iterations=6)

source = """#!/bin/env python3
print("hello world")
"""

program = encrypt_source(seed=src, varnames=varnames, cyphers=cyphers, iterations=iterations)

header = """#!/bin/env python
import base64
import codecs
"""

program = """%s

%s

""" % (header, program,)

with open("encoded.py", "wb") as f:
    f.write(program)
    f.close()

```

## EXAMPLE OUTPUT
```python
#!/bin/env python
import base64
import codecs

def test():
    print("hey ok")

secret_callback = """

"""

hey="NDYyOTZDNkU2RDRGMkE3NjRGNjI0MzdCNTIzMDY0NDQzRTY3NzE1QTU3NEE0RTU3MzE0ODY2NDIyQTZGNEM2RjcxNDg3MjRBNTIzRTJCNTA="
you="NDYyOTZDNzE2QjQ2NDYyMzNFNzU0MzdENDEyNTdDNTc0MDMwMjk3RTQ0NkM3NDYwMzU0NjQ1NEI3MTNGNUEyMTczM0Q1OTRENzI0MTI5Njk="
right="NDY2QTYwNTk2RDQ0NEM2NjYwNDY2MjM3Nzc1MDQzNDIzMDU2NkY1NDQ2NjczNzUwNDY0NjRDNzk0MzVBNjE3ODcwNTAzMDYzN0Q3QTQ1NTI="
there="NDYyOTZENTk0QzQ1NDk3Njc0NDg1NDc1MzQzMTQxNDQ3NDQzNDI0RDQ0NTI1RTQyMjg0NjQ1NEI3MTNGNjI3NTZDNjg2NTU2NkM0RjNFMzg="
on="NDYyOTZENjEzRjU0MzA1NDY5MjM1NDczNkI3NjUxNTIzNzcyNTA0ODQ0NzM0MDVGMzU0ODY2NDIyQTc4NTAyNTI0Nzc3OTQ2NkMzMDQ5M0Q="
the="NDYyOTNENjI2QzU4NjcyQTdFNkM2MTc4Nzk2ODUxNDI3MTU0MjM0OTUzMzQ2MzQwNDE0ODY2NDIyQTZGNTA2MzU1MkE3MTU3NEY0NjI4MjE0ODM4NjUyNjc4NEE1QTRDN0I1MjRCMzA0NzU3NzE0NjJCNTg0Qjc2NTc2QTQ4NUEzMDQ3NDQ1NDNENTU1NzY3M0U0RTU4NDkzNTZDMzUzMDQ3MjY1NjU4NTM2MTdC"
wall="aGV5ID0gYmFzZTY0LmI2NGRlY29kZShieXRlcyhoZXksICd1dGYtOCcpKS5kZWNvZGUoJ3V0Zi04Jyk7aGV5ID0gYmFzZTY0LmIxNmRlY29kZShieXRlcyhoZXksICd1dGYtOCcpKS5kZWNvZGUoJ3V0Zi04Jyk7aGV5ID0gYmFzZTY0LmI4NWRlY29kZShieXRlcyhoZXksICd1dGYtOCcpKS5kZWNvZGUoJ3V0Zi04Jyk7aGV5ID0gY29kZWNzLmRlY29kZShzdHIoaGV5KSwgJ3JvdF8xMycpO2hleSA9IGJhc2U2NC5hODVkZWNvZGUoYnl0ZXMoaGV5LCAndXRmLTgnKSkuZGVjb2RlKCd1dGYtOCcpO2hleSA9IGJhc2U2NC5hODVkZWNvZGUoYnl0ZXMoaGV5LCAndXRmLTgnKSkuZGVjb2RlKCd1dGYtOCcpO2hleSA9IGJhc2U2NC5iMTZkZWNvZGUoYnl0ZXMoaGV5LCAndXRmLTgnKSkuZGVjb2RlKCd1dGYtOCcpO3lvdSA9IGJhc2U2NC5iNjRkZWNvZGUoYnl0ZXMoeW91LCAndXRmLTgnKSkuZGVjb2RlKCd1dGYtOCcpO3lvdSA9IGJhc2U2NC5iMTZkZWNvZGUoYnl0ZXMoeW91LCAndXRmLTgnKSkuZGVjb2RlKCd1dGYtOCcpO3lvdSA9IGJhc2U2NC5iODVkZWNvZGUoYnl0ZXMoeW91LCAndXRmLTgnKSkuZGVjb2RlKCd1dGYtOCcpO3lvdSA9IGNvZGVjcy5kZWNvZGUoc3RyKHlvdSksICdyb3RfMTMnKTt5b3UgPSBiYXNlNjQuYTg1ZGVjb2RlKGJ5dGVzKHlvdSwgJ3V0Zi04JykpLmRlY29kZSgndXRmLTgnKTt5b3UgPSBiYXNlNjQuYTg1ZGVjb2RlKGJ5dGVzKHlvdSwgJ3V0Zi04JykpLmRlY29kZSgndXRmLTgnKTt5b3UgPSBiYXNlNjQuYjE2ZGVjb2RlKGJ5dGVzKHlvdSwgJ3V0Zi04JykpLmRlY29kZSgndXRmLTgnKTtyaWdodCA9IGJhc2U2NC5iNjRkZWNvZGUoYnl0ZXMocmlnaHQsICd1dGYtOCcpKS5kZWNvZGUoJ3V0Zi04Jyk7cmlnaHQgPSBiYXNlNjQuYjE2ZGVjb2RlKGJ5dGVzKHJpZ2h0LCAndXRmLTgnKSkuZGVjb2RlKCd1dGYtOCcpO3JpZ2h0ID0gYmFzZTY0LmI4NWRlY29kZShieXRlcyhyaWdodCwgJ3V0Zi04JykpLmRlY29kZSgndXRmLTgnKTtyaWdodCA9IGNvZGVjcy5kZWNvZGUoc3RyKHJpZ2h0KSwgJ3JvdF8xMycpO3JpZ2h0ID0gYmFzZTY0LmE4NWRlY29kZShieXRlcyhyaWdodCwgJ3V0Zi04JykpLmRlY29kZSgndXRmLTgnKTtyaWdodCA9IGJhc2U2NC5hODVkZWNvZGUoYnl0ZXMocmlnaHQsICd1dGYtOCcpKS5kZWNvZGUoJ3V0Zi04Jyk7cmlnaHQgPSBiYXNlNjQuYjE2ZGVjb2RlKGJ5dGVzKHJpZ2h0LCAndXRmLTgnKSkuZGVjb2RlKCd1dGYtOCcpO3RoZXJlID0gYmFzZTY0LmI2NGRlY29kZShieXRlcyh0aGVyZSwgJ3V0Zi04JykpLmRlY29kZSgndXRmLTgnKTt0aGVyZSA9IGJhc2U2NC5iMTZkZWNvZGUoYnl0ZXModGhlcmUsICd1dGYtOCcpKS5kZWNvZGUoJ3V0Zi04Jyk7dGhlcmUgPSBiYXNlNjQuYjg1ZGVjb2RlKGJ5dGVzKHRoZXJlLCAndXRmLTgnKSkuZGVjb2RlKCd1dGYtOCcpO3RoZXJlID0gY29kZWNzLmRlY29kZShzdHIodGhlcmUpLCAncm90XzEzJyk7dGhlcmUgPSBiYXNlNjQuYTg1ZGVjb2RlKGJ5dGVzKHRoZXJlLCAndXRmLTgnKSkuZGVjb2RlKCd1dGYtOCcpO3RoZXJlID0gYmFzZTY0LmE4NWRlY29kZShieXRlcyh0aGVyZSwgJ3V0Zi04JykpLmRlY29kZSgndXRmLTgnKTt0aGVyZSA9IGJhc2U2NC5iMTZkZWNvZGUoYnl0ZXModGhlcmUsICd1dGYtOCcpKS5kZWNvZGUoJ3V0Zi04Jyk7b24gPSBiYXNlNjQuYjY0ZGVjb2RlKGJ5dGVzKG9uLCAndXRmLTgnKSkuZGVjb2RlKCd1dGYtOCcpO29uID0gYmFzZTY0LmIxNmRlY29kZShieXRlcyhvbiwgJ3V0Zi04JykpLmRlY29kZSgndXRmLTgnKTtvbiA9IGJhc2U2NC5iODVkZWNvZGUoYnl0ZXMob24sICd1dGYtOCcpKS5kZWNvZGUoJ3V0Zi04Jyk7b24gPSBjb2RlY3MuZGVjb2RlKHN0cihvbiksICdyb3RfMTMnKTtvbiA9IGJhc2U2NC5hODVkZWNvZGUoYnl0ZXMob24sICd1dGYtOCcpKS5kZWNvZGUoJ3V0Zi04Jyk7b24gPSBiYXNlNjQuYTg1ZGVjb2RlKGJ5dGVzKG9uLCAndXRmLTgnKSkuZGVjb2RlKCd1dGYtOCcpO29uID0gYmFzZTY0LmIxNmRlY29kZShieXRlcyhvbiwgJ3V0Zi04JykpLmRlY29kZSgndXRmLTgnKTt0aGUgPSBiYXNlNjQuYjY0ZGVjb2RlKGJ5dGVzKHRoZSwgJ3V0Zi04JykpLmRlY29kZSgndXRmLTgnKTt0aGUgPSBiYXNlNjQuYjE2ZGVjb2RlKGJ5dGVzKHRoZSwgJ3V0Zi04JykpLmRlY29kZSgndXRmLTgnKTt0aGUgPSBiYXNlNjQuYjg1ZGVjb2RlKGJ5dGVzKHRoZSwgJ3V0Zi04JykpLmRlY29kZSgndXRmLTgnKTt0aGUgPSBjb2RlY3MuZGVjb2RlKHN0cih0aGUpLCAncm90XzEzJyk7dGhlID0gYmFzZTY0LmE4NWRlY29kZShieXRlcyh0aGUsICd1dGYtOCcpKS5kZWNvZGUoJ3V0Zi04Jyk7dGhlID0gYmFzZTY0LmE4NWRlY29kZShieXRlcyh0aGUsICd1dGYtOCcpKS5kZWNvZGUoJ3V0Zi04Jyk7dGhlID0gYmFzZTY0LmIxNmRlY29kZShieXRlcyh0aGUsICd1dGYtOCcpKS5kZWNvZGUoJ3V0Zi04Jyk7ZXZhbChjb21waWxlKGV2YWwoIlx4NjhceDY1XHg3OSIpICsgZXZhbCgiXHg3OVx4NmZceDc1IikgKyBldmFsKCJceDcyXHg2OVx4NjdceDY4XHg3NCIpICsgZXZhbCgiXHg3NFx4NjhceDY1XHg3Mlx4NjUiKSArIGV2YWwoIlx4NmZceDZlIikgKyBldmFsKCJceDc0XHg2OFx4NjUiKSwgJzxzdHJpbmcnLCAnZXhlYycpKQ=="

eval(compile(base64.b64decode(wall).decode("utf-8"), '<string>', 'exec'))
```