# 【IP 报文| 实用小技巧】IP报文可以告诉你什么？
抓包，对于学网络的同学不是一个陌生的词汇。抓包，大家也经常在抓，但是你有真正认真分析过报文吗？

可以试一试能从这张抓包获取的报文中分析出源MAC,目的MAC，源IP，目的IP和端口号吗？
![Wireshark抓取以太网帧报文](https://i0.hdslb.com/bfs/article/f406d2788c574b9974a4bb551cde7e67f5fa6a70.png@1134w_112h.webp "Wireshark抓取以太网帧报文")

得到这个以太网帧报文，我们首先需要知道以太网帧的格式！

格式如下：
![Ethernet Version 2 帧格式](gitbook.png)
上述以太网帧格式可以得出6字节的目的MAC地址+6字节的源MAC地址+2字节的类型参数+46-1500字节的数据+2字节的CRC

目的MAC地址和源MAC地址就没什么好讲的了，我们着重来讲讲2个字节的类型参数

作用：标识出以太网帧所携带的上层数据类型

其中：0x0800代表IPv4，0x86DD代表IPv6，0x0806代表ARP，0x8100代表Dot1q，0x8864代表PPPoE。    

所以暂且可以得知：目的MAC地址为：aa:bb:cc:00:02:00，源MAC地址为：aa:bb:cc:00:01:00

<iframe  
    width="800" 
    height="450"  
    src="//player.bilibili.com/player.html?aid=19579680&cid=31928452&page=1" 
    scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> 
</iframe>