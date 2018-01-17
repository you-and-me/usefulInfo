###  1.Weinre是什么？

Weinre全称 Web Inspector Remote，是一个简单好用的远程调试工具。我们可以在自己的PC上修改对应网页的页面元素、样式，或是查看Javascript变量，同时还可以看到手机上页面的错误和警告信息。

### 2、Weinre组成原理

* 目标页面（target）：也就是调试的页面，页面中需要嵌入weinre提供的远程js，这里的js相当一个锚点作用，后文会提到；
* 服务端（agent）：一个HTTP Server，为目标页面与客户端建立通信；
* 客户端（client）：本地的Web Inspector调试客户端。

### 3、安装及运行Weinre

Weinre支持Windows与Mac（Weinre是运行在java环境下的，请确保机器上有正确的java运行环境）

首先安装 Weinre：

npm install -g weinre

安装完成之后，可以执行weinre -h显示启动参数，这时候执行如下命令开启： weinre --boundHost 192.16.10.164

【PS】Weinre 提供了6个可选的启动参数，常用的是以下两个参数，其它的用默认值就可以了。

* httpPort 调试服务器运行的端口，默认的 8080，如果这个端口有在用，可以改为其它端口；
* boundHost 调试服务器绑定的 IP 地址（或域名），默认 localhost，如果设置为 -all-，表示绑定到所有当前机器可以访问的接口。
   weinre --boundHost -all-
   
   访问http://192.16.10.164:8080,出现正确的页面，说明安装成功！ 按照页面中的提示，将Target Script中给的地址放到你需要调试的页面中，然后访问debug client。访问后，我们能够看到一个类似于chrome控制台的东西出现了，这时，你就可以调试啦！同时，注意到Targets中标明了现在调用远程Weinre js的页面
   
   
【PS】1.利用Weinre也能在console里面查看js的变量，这一点非常方便。2.这个时候用Fiddler抓包，我们能看到来自于target、client的请求。
