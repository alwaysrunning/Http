# Http-

http协议是超文本传输协议（应用层协议），在浏览器与服务器之间都是用http协议通过internet进行数据的发送和接受的。
http 是一个基于请求和响应模式的的协议；

一、http - Request:（包含Request line，Request Header，Request body）


1.Request line: 

请求方法

请求资源源

http版本协议号；

2.Request Header:

Cache-Control: 客户端希望服务端是否缓存自己的请求数据（"Cache-Control: no-cache"，"Cache-Control: max-age=0"）

Connect：客户端是否希望与服务端保持长时间链接（Connection: close", "Connection: keep-alive）

Pragma：如 "Pragma: no-cache"：希望在服务端该请求结果相关的数据不进行缓存

Accept：表示客户端可接受的介质类型

Accept-Charset：客户端所能识别的字符集编码格式

Accept-Language：客户端所能识别的语言，格式：“Accept-Language:语言1[:权重]，语言2[:权重]”，如：”Accept-Language: zh, en;q=0.7”；

Host：客户请求的主机域名或主机IP

User-Agent：表明用户所使用的浏览器标识

Referer：指明该请求是从哪个关联链接而来的

Accept-Encoding：客户端所能识别的编码压缩格式

If-None-Match：该字段与客户端缓存相关，客户端发送URL请求的同时发送该字段及标识，如果服务端的标识与客户端的标识一致，则返回304表明此URL未修改过，如果不一致则服务端返回完整的数据信息，如：“If-None-Match:0f0a893aad8c61:253,0f0a893aad8c61:252, 0f0a893aad8c61:251”；

Content-Length：客户端以POST方法上传数据时数据体部分的内容长度，如：“Content-Length:24”；Content-Type：客户端发送的数据体的内容类型

Content- Type：客户端发送的数据体的内容类型

3.Request body 



二、http - Response: （包含Response line，Response Header，Response body）


1.Response line: 响应状态 200成功  304not modified  403服务器拒绝提供服务  404not found

2.Response header :

Cache- Control：服务端要求中间代理及客户端如何缓存自己响应的数据，如“Cache-Control:no-cache”，如：“Cache-Control: private” 不希望被缓存，“Cache-Control: public” 可以被缓存；

Connection：服务端是否希望与客户端之间保持长连接，如“Connection: close”, “Connection: keep-alive”；

Date：只有当请求方法为POST或PUT方法时客户端才可能会有些字段；

Pragma：包含了服务端一些特殊响应信息，如 “Pragma: no-cache” 服务端希望代理或客户端不应缓存结果数据；

Transfer-Encoding：服务端向客户端传输数据所采用的传输模式(仅在HTTP1.1中出现)，如：“Transfer-Encoding:chunked”，注：该字段的优先级要高于“Content-Length”　字段的优先级；

Accept-Ranges：表明服务端接收的数据单位，如：“Accept-Ranges:bytes”；Location：服务端向客户端返回此信息以使客户端进行重定向，如：“Location: http://www.hexun.com”；

Server：服务端返回的用于标识自己的一些信息，如：“ Server: Microsoft-IIS/6.0”；

Content-Encoding：服务端所响应数据的编码格式，如：“Content-Encoding: gzip”；

Content-Length：服务端所返回数据的数据体部分的内容长度，如：“ Content-Length: 24”；

Content-Type：服务端所返回的数据体的内容类型，如：“Content-Type: text/html; charset=gb2312” ；

ETag：服务端返回的响应数据的标识字段，客户端可根据此字段的值向服务器发送某URL是否更新的信息；

3.Response body: html...



三、补充：



tcp/ip协议是分层的，从底层至应用层分别为物理层，链路层，网络层，传输层，应用层。从应用层到底层，数据是一层层
封装的，封装的一般方式都是在原有的数据前加一个数据控制头；

其中对于tcp传输协议，客户端与服务端进行连接之前需要经过TCP三次握手

第一次握手：客户端发送syn包(syn=j)到服务器，并进入SYN_SEND状态，等待服务器确认;

第二次握手：服务器收到syn包，必须确认客户的SYN(ack=j+1)，同时自己也发送一个SYN包(syn=k)，即SYN+ACK包，此时服务器进入SYN_RECV状态;

第三次握手：客户端收到服务器的SYN+ACK包，向服务器发送确认包ACK(ack=k+1)，此包发送完毕，客户端和服务器进入ESTABLISHED状态，完成三次握手。
