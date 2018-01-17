###  1.Weinre是什么？

Weinre全称 Web Inspector Remote，是一个简单好用的远程调试工具。我们可以在自己的PC上修改对应网页的页面元素、样式，或是查看Javascript变量，同时还可以看到手机上页面的错误和警告信息。

### 2、Weinre组成原理

.. 目标页面（target）：也就是调试的页面，页面中需要嵌入weinre提供的远程js，这里的js相当一个锚点作用，后文会提到；
.. 服务端（agent）：一个HTTP Server，为目标页面与客户端建立通信；
.. 客户端（client）：本地的Web Inspector调试客户端。
