### 1.基本HTTP GET/response交互

* 实验图像
![Image text](image/HTTP2-1.png)
  
```
    GET /wireshark-labs/HTTP-wireshark-file1.html HTTP/1.1\r\n
    Host: gaia.cs.umass.edu\r\n
    Connection: keep-alive\r\n
    Pragma: no-cache\r\n
    Cache-Control: no-cache\r\n
    Upgrade-Insecure-Requests: 1\r\n
    User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/109.0.0.0 Safari/537.36 Edg/109.0.1518.78\r\n
    Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9\r\n
    Accept-Encoding: gzip, deflate\r\n
    Accept-Language: zh-CN,zh;q=0.9,en;q=0.8,en-US;q=0.7,en-GB;q=0.6,pl;q=0.5\r\n
    \r\n
    [Full request URI: http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file1.html]
    [HTTP request 1/1]
    [Response in frame: 35]
```

```
    HTTP/1.1 200 OK\r\n
    Date: Mon, 27 Feb 2023 02:45:29 GMT\r\n
    Server: Apache/2.4.6 (CentOS) OpenSSL/1.0.2k-fips PHP/7.4.33 mod_perl/2.0.11 Perl/v5.16.3\r\n
    Last-Modified: Sun, 26 Feb 2023 06:59:01 GMT\r\n
    ETag: "80-5f594e5be12ef"\r\n
    Accept-Ranges: bytes\r\n
    Content-Length: 128\r\n
        [Content length: 128]
    Keep-Alive: timeout=5, max=100\r\n
    Connection: Keep-Alive\r\n
    Content-Type: text/html; charset=UTF-8\r\n
    \r\n
    [HTTP response 1/1]
    [Time since request: 0.231533000 seconds]
    [Request in frame: 29]
    [Request URI: http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file1.html]
    File Data: 128 bytes

    <html>\n
    Congratulations.  You've downloaded the file \n
    http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file1.html!\n
    </html>\n
```
1. 您的浏览器是否运行HTTP版本1.0或1.1？服务器运行什么版本的HTTP？  
浏览器和服务器都运行 HTTP/1.1  

2. 您的浏览器会从接服务器接受哪种语言（如果有的话）？  
Accept-Language: zh-CN  

3. 您的计算机的IP地址是什么？ gaia.cs.umass.edu服务器地址呢？  
计算机IP 172.22.50.8 
gaia.cs.umass.edu服务器IP 128.119.245.12

4. 服务器返回到浏览器的状态代码是什么？  
200 OK  

5. 服务器上HTML文件的最近一次修改是什么时候？  
Last-Modified: Sun, 26 Feb 2023 06:59:01 GMT

6. 服务器返回多少字节的内容到您的浏览器？  
Content-Length: 128

7. 通过检查数据包内容窗口中的原始数据，你是否看到有协议头在数据包列表窗口中未显示？ 如果是，请举一个例子。  
应该没有  

### 2.HTTP条件Get/response交互

* 实验图像
![Image text](image/HTTP2-2.png)  

```
    GET /wireshark-labs/HTTP-wireshark-file2.html HTTP/1.1\r\n
    Host: gaia.cs.umass.edu\r\n
    Connection: keep-alive\r\n
    Cache-Control: max-age=0\r\n
    Upgrade-Insecure-Requests: 1\r\n
    User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/109.0.0.0 Safari/537.36 Edg/109.0.1518.78\r\n
    Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9\r\n
    Accept-Encoding: gzip, deflate\r\n
    Accept-Language: zh-CN,zh;q=0.9,en;q=0.8,en-US;q=0.7,en-GB;q=0.6,pl;q=0.5\r\n
    \r\n
    [Full request URI: http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file2.html]
    [HTTP request 1/2]
    [Response in frame: 402]
    [Next request in frame: 925]
```

```
    HTTP/1.1 200 OK\r\n
    Date: Tue, 28 Feb 2023 03:17:25 GMT\r\n
    Server: Apache/2.4.6 (CentOS) OpenSSL/1.0.2k-fips PHP/7.4.33 mod_perl/2.0.11 Perl/v5.16.3\r\n
    Last-Modified: Mon, 27 Feb 2023 06:59:01 GMT\r\n
    ETag: "173-5f5a903938350"\r\n
    Accept-Ranges: bytes\r\n
    Content-Length: 371\r\n
    Keep-Alive: timeout=5, max=100\r\n
    Connection: Keep-Alive\r\n
    Content-Type: text/html; charset=UTF-8\r\n
    \r\n
    [HTTP response 1/2]
    [Time since request: 0.226782000 seconds]
    [Request in frame: 316]
    [Next request in frame: 925]
    [Next response in frame: 1180]
    [Request URI: http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file2.html]
    File Data: 371 bytes
```

```
    GET /wireshark-labs/HTTP-wireshark-file2.html HTTP/1.1\r\n
    Host: gaia.cs.umass.edu\r\n
    Connection: keep-alive\r\n
    Cache-Control: max-age=0\r\n
    Upgrade-Insecure-Requests: 1\r\n
    User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/109.0.0.0 Safari/537.36 Edg/109.0.1518.78\r\n
    Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9\r\n
    Accept-Encoding: gzip, deflate\r\n
    Accept-Language: zh-CN,zh;q=0.9,en;q=0.8,en-US;q=0.7,en-GB;q=0.6,pl;q=0.5\r\n
    If-None-Match: "173-5f5a903938350"\r\n
    If-Modified-Since: Mon, 27 Feb 2023 06:59:01 GMT\r\n
    \r\n
    [Full request URI: http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file2.html]
    [HTTP request 2/2]
    [Prev request in frame: 316]
    [Response in frame: 1180]

```

```
    HTTP/1.1 304 Not Modified\r\n
    Date: Tue, 28 Feb 2023 03:17:27 GMT\r\n
    Server: Apache/2.4.6 (CentOS) OpenSSL/1.0.2k-fips PHP/7.4.33 mod_perl/2.0.11 Perl/v5.16.3\r\n
    Connection: Keep-Alive\r\n
    Keep-Alive: timeout=5, max=99\r\n
    ETag: "173-5f5a903938350"\r\n
    \r\n
    [HTTP response 2/2]
    [Time since request: 0.226891000 seconds]
    [Prev request in frame: 316]
    [Prev response in frame: 402]
    [Request in frame: 925]
    [Request URI: http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file2.html]
```

8. 检查第一个从您浏览器到服务器的HTTP GET请求的内容。您在HTTP GET中看到了“IF-MODIFIED-SINCE”行吗？  
没看到  

9. 检查服务器响应的内容。服务器是否显式返回文件的内容？ 你是怎么知道的？  
服务器显式返回了文件内容，在实体部分可以看到  

10. 现在，检查第二个HTTP GET请求的内容。 您在HTTP GET中看到了“IF-MODIFIED-SINCE:”行吗？ 如果是，“IF-MODIFIED-SINCE:”头后面包含哪些信息？  
If-Modified-Since: Mon, 02 Dec 2019 06:59:01 GMT\r\n  
包含了本地保存的文件的在服务器上的最后修改时间  

11. 针对第二个HTTP GET，从服务器响应的HTTP状态码和短语是什么？服务器是否明确地返回文件的内容？请解释。  
304 Not Modified  
服务器没有返回文件的内容，因为浏览器只是从其缓存中检索了该内容。如果该文件在上次访问后被修改过，它就会返回该文件的内容，相反，它只是告诉我的浏览器从其缓存中检索旧文件。

### 3.检索长文件

* 实验图像
![Image text](image/HTTP2-3.png)   

```
    GET /wireshark-labs/HTTP-wireshark-file3.html HTTP/1.1\r\n
    Host: gaia.cs.umass.edu\r\n
    Connection: keep-alive\r\n
    Cache-Control: max-age=0\r\n
    Upgrade-Insecure-Requests: 1\r\n
    User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/109.0.0.0 Safari/537.36 Edg/109.0.1518.78\r\n
    Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9\r\n
    Accept-Encoding: gzip, deflate\r\n
    Accept-Language: zh-CN,zh;q=0.9,en;q=0.8,en-US;q=0.7,en-GB;q=0.6,pl;q=0.5\r\n
    \r\n
    [Full request URI: http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file3.html]
    [HTTP request 1/1]
    [Response in frame: 45]
```

```
    [4 Reassembled TCP Segments (4861 bytes): #41(1394), #42(1394), #43(1394), #45(679)]
    [Frame: 41, payload: 0-1393 (1394 bytes)]
    [Frame: 42, payload: 1394-2787 (1394 bytes)]
    [Frame: 43, payload: 2788-4181 (1394 bytes)]
    [Frame: 45, payload: 4182-4860 (679 bytes)]
    [Segment count: 4]
    [Reassembled TCP length: 4861]
    [Reassembled TCP Data: 485454502f312e3120323030204f4b0d0a446174653a205475652c203238204665622032…]

    Hypertext Transfer Protocol
    HTTP/1.1 200 OK\r\n
    Date: Tue, 28 Feb 2023 06:32:28 GMT\r\n
    Server: Apache/2.4.6 (CentOS) OpenSSL/1.0.2k-fips PHP/7.4.33 mod_perl/2.0.11 Perl/v5.16.3\r\n
    Last-Modified: Tue, 28 Feb 2023 06:32:02 GMT\r\n
    ETag: "1194-5f5bcc0df4c6c"\r\n
    Accept-Ranges: bytes\r\n
    Content-Length: 4500\r\n
    Keep-Alive: timeout=5, max=100\r\n
    Connection: Keep-Alive\r\n
    Content-Type: text/html; charset=UTF-8\r\n
    \r\n
    [HTTP response 1/1]
    [Time since request: 0.231152000 seconds]
    [Request in frame: 37]
    [Request URI: http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file3.html]
    File Data: 4500 bytes
   ```

12. 您的浏览器发送多少HTTP GET请求消息？哪个数据包包含了美国权利法案的消息？  
只发送了一个HTTP GET请求消息。  
返回的四个TCP数据包都包含了美国权利法案的消息。  

13. 哪个数据包包含响应HTTP GET请求的状态码和短语？
第一个TCP数据包, 包含响应HTTP GET请求的状态码和短语  

14. 响应中的状态码和短语是什么？  
200 OK  

15. 需要多少包含数据的TCP段来执行单个HTTP响应和权利法案文本？  
需要4个TCP数据包  

### 4.具有嵌入对象的HTML文档  

* 实验图像
![Image text](image/HTTP2-4.png)  

16. 您的浏览器发送了几个HTTP GET请求消息？ 这些GET请求发送到哪个IP地址？  
3个HTTP GET请求消息。分别是主页的文件，pearson的logo图，和封面图。它们的请求发送到的ip地址:
* 主页的文件: 128.119.245.12
* pearson的logo图: 128.119.245.12
* 封面图: 178.79.137.164

17. 浏览器从两个网站串行还是并行下载了两张图片？请说明。
浏览器会串行下载这两个图像。我认为情况就是这样，因为浏览器在请求第二张图像之前请求并发送了第一张图像。如果它们是并行运行的，那么两个文件都将被请求，并在同一时间段内返回。但是，在本例中，只有在第一个图像返回后才请求第二个图像。

### 5.HTTP认证

* 实验图像
![Image text](image/HTTP2-5.png)  

18. 对于您的浏览器的初始HTTP GET消息，服务器响应（状态码和短语）是什么响应？  
401 Unauthorized

19. 当您的浏览器第二次发送HTTP GET消息时，HTTP GET消息中包含哪些新字段？  
Authorization: Basic d2lyZXNoYXJrLXN0dWRlbnRzOm5ldHdvcms=\r\n
Credentials: wireshark-students:network


