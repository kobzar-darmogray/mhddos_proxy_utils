# mhddos_proxy_utils

Utility for converting shared targets into config format

```bash
$ cat config.txt 
http://localhost
https://localhost

localhost
localhost (53 udp/tcp)
127.0.0.1 (21/tcp, 22/tcp, 80/tcp, 443/tcp)
```
```bash
$ python3 config_converter.py -c config.txt
unexpected target, skipping: 		'localhost'
unexpected ports description, skipping: 'localhost (53 udp/tcp)'
---
http://localhost
https://localhost
tcp://127.0.0.1:21
tcp://127.0.0.1:22
tcp://127.0.0.1:80
tcp://127.0.0.1:443
```
```bash
$ ls -1 | grep config
config.txt
converted_config.txt
```
