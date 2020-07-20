## How to build youself 4g proxies

Allproxy provides a easy to make your 4g proxy, it suporrts most of platform, and easy to use.

[![DEMO](https://img.youtube.com/vi/eQ9m05CQR8U/0.jpg)](https://www.youtube.com/watch?v=eQ9m05CQR8U)

[![PC GUI Client](https://img.youtube.com/vi/fTCktSV2Oyo/0.jpg)](https://www.youtube.com/watch?v=fTCktSV2Oyo)

## Android
1. Download and Install allproxy app from google play.
2. Click connect button, you will get a proxy address, your phone network is published with this address.

## Raspberry PI
1. Download and flash the Image we built, then just plug your 4g device to PI.
2. The allproxy client is saved in ~/allproxyClient
3. The proxies info is save in ~/allproxyClient
4. You can update to the latest arm version "allproxyC" in your PI, because the image is old.

## Windows/MacOs/Raspeberry/openWrt/Other Linux...
1. Change the server address in conf_client.yaml or just use my free servers
2. Open allproxyC

## Where can I get the proxies address
It will generate a file "proxy.info" in the working directory, which contains the proxies infomation, the content likes:
```
{"proxies":
{"d3a849f6c55ea765058bc72ded1cfd91":{"connectedAt":"2019-09-03 14:08:08 +0800","proxyUrl":"http://192.168.2.100:53636"},"6d5ada3b1b0f9fadde94c6dc081dba69":{"connectedAt":"2019-09-03 14:08:08 +0800","proxyUrl":"http://192.168.2.100:53625"}}}
```

## Install PC client as service
1. You need to assign [execute] permission for allproxyC in linux env
```bash
chmod +x allproxyC
```
2. Install it as daemon service 
```bash
allproxyC -i
```
3. Check its status
```bash
allproxyC -q
```
		
## Advance usage 
If you have multiple network interfaces in your machine(Maybe some 4g dongles/stickers), and you want to speed up the proxy,you can just set field 'localAddr' in conf_client.yaml.

+ localAddr , the address should be the IP addre which used to connect with allproxy service, and it will be your wifi adapter IP in most case
```
  localAddr: 192.168.2.46
```

## Free Server
+ conn4.trs.ai:9082   (US)

     
### How can I know which proxy is which device
You can know it by the ip address now.
```
curl ifconfig.me  --interface wwlan1
curl icanhazip.com  --interface wwlan1
curl ifconfig.co  --interface wwlan1
curl ip.cn  --interface wwlan1

-- get IP of a proxy
curl --proxy http://192.168.2.100:53625 ifconfig.me
```
 

## Help
You can get all valid parameters by:
```bash
allproxyC -h
```
Valid Options:

  -h    this help

  -i    install as deamon service

  -q    query the service status

  -s signal
        send signal to IgerslikeProxy: stop, restart, start

  -server string
        The server address

  -u    uninstall deamon service

  -userId string
        The user id

  -w string
        The working directory,default is the current directory


## Contact me
If you want to use your self allproxy server to make better security and speed, pls feel free to contact me by email/skype: mailme.xu#gmail.com
