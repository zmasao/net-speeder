# net-speeder
net-speeder 在高延迟不稳定链路上优化单线程下载速度

项目由 https://code.google.com/archive/p/net-speeder  迁入

A program to speed up single thread download upon long delay and unstable network

在高延迟不稳定链路上优化单线程下载速度

注1：开启了net-speeder的服务器上对外ping时看到的是4倍，实际网络上是2倍流量。另外两倍是内部dup出来的，不占用带宽。
另外，内部dup包并非是偷懒未判断。。。是为了更快触发快速重传的。
注2：net-speeder不依赖ttl的大小，ttl的大小跟流量无比例关系。不存在windows的ttl大，发包就多的情况。


安装步骤：

    bash <(curl https://raw.githubusercontent.com/zmasao/net-speeder/master/net_speeder_lazyinstall.sh)


使用方法(需要root权限启动）：

    #参数：./net_speeder 网卡名 加速规则（bpf规则）
    #ovz用法(加速所有ip协议数据)：
    ./net_speeder venet0 "ip"
