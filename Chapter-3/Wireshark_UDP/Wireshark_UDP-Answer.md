### Wireshark_UDP

使用下载的Wireshark捕获的数据包文件http-ethereal-trace-5  

```
Frame 1: 92 bytes on wire (736 bits), 92 bytes captured (736 bits)
Ethernet II, Src: Dell_4f:36:23 (00:08:74:4f:36:23), Dst: HewlettP_61:eb:ed (00:30:c1:61:eb:ed)
Internet Protocol Version 4, Src: 192.168.1.102, Dst: 192.168.1.104
User Datagram Protocol, Src Port: 4334, Dst Port: 161
    Source Port: 4334
    Destination Port: 161
    Length: 58
    Checksum: 0x65f8 [unverified]
    [Checksum Status: Unverified]
    [Stream index: 0]
    [Timestamps]
Simple Network Management Protocol
```

1. 字段有：Sources Port, Destination Port, Length, Checksum, payload

2. 8字节  Sources Port, Destination Port, Length, Checksum 分别占2字节

3. Length的值是指的是 UDP头部+payload的字节数。  

4. UDP数据报在单个IP包中携带，因此限制为IPv4最大有效载荷为655507字节，IPv6最大有效载荷为655527字节。

5. 源端口可能的最大值 (2^16 – 1) = 65535.

6. 十六进制 0x11，十进制 17  

7. 源端口号变为了目的端口号，目的端口号变为了源端口号  
