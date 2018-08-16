网易云信 Web UI组件介绍
====

NIM_Web_UIKit是一款可以帮助用户快速打造出聊天功能的UI组件，开发者可以通过一些简洁的代码，快速的实现自己的聊天工具。NIMKit完全开源，如果开发者希望更深层次的自定义，也可自行修改代码。


本工程线上演示效果： [http://site.elesos.com/NIM_Web_UIKit/test/](http://site.elesos.com/NIM_Web_UIKit/test/)

线上im测试：[https://www.starrtc.com/demo/im/](https://www.starrtc.com/demo/im/)

修改使用本工程
----
node环境是开发前提

1. 安装依赖   ` npm install`
2.	修改代码
3.	使用gulp构建生成uiKit文件 `gulp`


使用方法
-------
列表组件
----
会话列表：new NIMUIKit.SessionList(options)
---
options：初始化实例参数
---

| 参数 | 类型 | 说明 | 
| --- | --- | --- |
| parent | Node/String| 可选，定义组件插入的节点，也可在实例化后 调用inject方法
| clazz| String |可选，组件样式名，组件元素样式都基于该命名空间，默认样式为m-pannel|
| onclickitem | Function |可选，用来自定义点击列表项回调函数|
| onclickavatar | Function |可选，用来自定义点击列表项头像回调函数|
| data | Object | 必填，显示UI所需要的数据，具体内容见下文|
| infoprovider | Function | 必填，返回一个对象，由上层来控制显示规则，呈现数据|

#### data
| 参数 | 类型 | 说明 | 
| --- | --- | --- |
| sessions | Array| SDK 返回的sessions数据|

#### infoprovider return {Object｝
| 参数 | 类型 | 说明 | 
| --- | --- | --- |
| scene | String| p2p or team|
| target | String|scene+“-”account，例"p2p-test"|
| crtSession | String|scene+“-”account，例"p2p-test"|
| account| String| 账号|
| avatar | String| 头像地址|
| nick | String| 昵称|
| time | String| 消息时间|
| text | String| 消息内容|
| unread | String| 未读数|




inject(String|Node)
---
将组件插入浏览器节点


----------


群组列表：new NIMUIKit.TeamList(options)
---
options：初始化实例参数
---

| 参数 | 类型 | 说明 | 
| --- | --- | --- |
| parent | Node/String| 可选，定义组件插入的节点，也可在实例化后 调用inject方法
| clazz| String |可选，组件样式名，组件元素样式都基于该命名空间，默认样式为m-pannel|
| onclickitem | Function |可选，用来自定义点击列表项回调函数|
| onclickavatar | Function |可选，用来自定义点击列表项头像回调函数|
| data | Object | 必填，显示UI所需要的数据，具体内容见下文|
| infoprovider | Function | 必填，由上层来控制显示规则，呈现数据|

#### data
| 参数 | 类型 | 说明 | 
| --- | --- | --- |
| teams | Array| 群组列表|

#### infoprovider return {Object｝
| 参数 | 类型 | 说明 | 
| --- | --- | --- |
| target | String|scene+“-”account，例"p2p-test"|
| crtSession | String|scene+“-”account，例"p2p-test"|
| account| String| 账号|
| avatar | String| 头像地址|
| nick | String| 群，讨论组名|


inject(String|Node)
---
将组件插入浏览器节点


----------


好友列表：new NIMUIKit.FriendList(options)
---
options：初始化实例参数
---

| 参数 | 类型 | 说明 | 
| --- | --- | --- |
| parent | Node/String| 可选，定义组件插入的节点，也可在实例化后 调用inject方法
| clazz| String |可选，组件样式名，组件元素样式都基于该命名空间，默认样式为m-pannel|
| onclickitem | Function |可选，用来自定义点击列表项回调函数|
| onclickavatar | Function |可选，用来自定义点击列表项头像回调函数|
| data | Object | 必填，显示UI所需要的数据，具体内容见下文|

#### data
| 参数 | 类型 | 说明 | 
| --- | --- | --- |
| friends | Array| 好友列表|
| account|String | 当前用户账号|

#### infoprovider return {Object｝
| 参数 | 类型 | 说明 | 
| --- | --- | --- |
| target | String|scene+“-”account，例"p2p-test"|
| crtSession | String|scene+“-”account，例"p2p-test"|
| account| String| 账号|
| avatar | String| 头像地址|
| nick | String| 昵称|

inject(String|Node)
---
将组件插入浏览器节点



更多使用案例请参考[NIM_Web_Demo](https://github.com/netease-im/NIM_Web_Demo)