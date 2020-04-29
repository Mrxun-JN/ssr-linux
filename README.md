# ssr-linux
how to use shadowsocks in linux



## download & edit
```bash
git clone zipfile

tar && cd 

vim config.json
```

edit the configure file

```json
{
    "server": "0.0.0.0",
    "server_ipv6": "::",
    "server_port": 8388,
    "local_address": "127.0.0.1",
    "local_port": 1080,
    "password": "m",
    "method": "aes-128-ctr",
    "protocol": "auth_aes128_md5",
    "protocol_param": "",
    "obfs": "tls1.2_ticket_auth_compatible",
    "obfs_param": "",
    "speed_limit_per_con": 0,
    "speed_limit_per_user": 0,
    "additional_ports" : {}, // only works under multi-user mode
    "additional_ports_only" : false, // only works under multi-user mode
    "timeout": 120,
    "udp_timeout": 60,
    "dns_ipv6": false,
    "connect_verbose_info": 0,
    "redirect": "",
    "fast_open": false
}
```

change to your configure

```json

"server_port":8388,        //端口
"password":"password",     //密码
 "protocol":"origin",       //协议插件
 "obfs":"http_simple",      //混淆插件
 "method":"aes-256-cfb",    //加密方式      

```

## use

```python
python local.py -c config.json -d start
```

if something wrong, you can find in google

## in Ubuntu

you can use

```bash
sudo apt-get install proxychains
```

then wget command will use your ssr config
```bash
proxychains wget www.google.com

```
