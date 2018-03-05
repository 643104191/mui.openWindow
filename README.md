mui.openWindow兼容web&amp;plus环境下的页面传参

------

# 背景介绍

- 刚刚好要写个微信公众号和html5+兼容的项目
- 发现总是用localStorage传参不是事啊
- 太不优雅了
- 想了想还是想办法兼容下吧

# 兼容原理

- 调用mui.openWindow前先判断相关环境,执行相关兼容方法

# 使用场景

- 需要兼容网页&html5+的项目
- 项目需要引入mui.js
- 打开页面/webview用的是mui.openWindow

# 使用方法

引入mui.openWindow.js文件,正常写传参代码

```javascript

mui.openWindow({
    url: 'target.html',
    id: 'target',
    extras: {name:'mui'}
});

```

接收参数页面

```javascript

// 同步调用
if (mui.os.plus) {
    mui.plusReady(function(){
        var extras = mui.getExtras();
        console.log(extras);
    });
}else{
    var extras = mui.getExtras();
    console.log(extras);
}
// 异步调用
mui.getExtras(function(extras){
    console.log(extras);
});

```

# 上源码

- [github](https://github.com/643104191/mui.openWindow) \(觉得ok的记得给我点个星星啊\)

- [点我在线预览](https://643104191.github.io/mui.openWindow/) \(记得给我点个星星啊\)