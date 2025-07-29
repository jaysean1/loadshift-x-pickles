# index.html的功能说明


## overview

index.html 是一个完整的流程展示页面，包括订单的创建，AI分析，报价，订单确认，装车，运输，交付，服务评价等流程

index.html页面会通过iframe嵌套其他页面，包括：

`pickles-zt2-demo/pages/client_quote.html` 报价页面
`pickles-zt2-demo/pages/phonecall_confirm.html` 电话确认页面
`pickles-zt2-demo/pages/order_confirmation.html` 订单确认页面
`pickles-zt2-demo/pages/pickup_auth.html` 装车授权页面
`pickles-zt2-demo/pages/god_mode.html` 上帝模式页面
`pickles-zt2-demo/pages/delivery_complete.html` 交付完成页面


## 页面布局

- 在页面的左侧/右侧，我们会通过iframe嵌套需要展示的流程页面
- 在页面的右侧/左侧。我们会展示页面的一些流程说明
- 注意：页面布局是根据嵌入页面的宽度进行一些适当调整，尤其是上帝模式页面，是一个pc页面，宽度有点大，我们可以在iframe中缩小展示的页面比例，保证嵌入的页面能够完全展示
- 页面的布局左右可以切换，比如第一个页面是iframe在左侧，说明在右侧，下一个页面是iframe在右侧，说明在左侧，etc
- 在页面的顶部的右下角，需要有一个上一步和下一步的按钮，点击后，会切换我们的展示的流程页面
- 针对移动端的页面，需要一个iphone的模拟的容器，在内部展示我们的页面

