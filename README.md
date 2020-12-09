# bluetooth-chat
基于 Android Classic Bluetooth 的安卓蓝牙聊天软件。
支持一对一实时通信、文件传输、好友添加、好友分组、好友在线状态更新等功能，
其中消息发送支持文本、表情等方式。

## 开发环境
- windows 10 pro
- android studio

## 前景
- 蓝牙技术作为一种小范围无线连接技术，能够在设备间实现方便快捷、灵活安全、低成本、低功耗的数据和语音通信，是目前实现无线个人局域网的主流技术之一。同时，蓝牙系统以自组式组网的方式工作，每个蓝牙设备都可以在网络中实现路由选择的功能，可以形成移动自组网络。蓝牙的特性在许多方面正好符合Ad Hoc和WPAN的概念，显示了其真正的潜力所在。而且，将蓝牙与其他网络相连接可带来更广泛的应用，例如接入互联网、PSTN或公众移动通信网，可以使用户应用更方便或给用户带来更大的实惠。

- 蓝牙聊天作为一款针对局域网范围内的聊天软件，在办公密集，想实现快速稳定实时通讯还是比较有实用价值的。目前蓝牙技术发展迅速，5.0传输速率已经达到2Mbps，传输级别达到无损级别，有效工作距离可达300米，在蓝牙组网方面技术也在进一步更新，相信要不了多久会有很成熟的方案出来，这样一来就可以实现多人在线实时聊天功能，打破只能一对多实时聊天的界限。

## 技术简介
- 蓝牙通信的主从关系
蓝牙技术规定每一对设备之间进行蓝牙通讯时，必须一个为主角色，另一为从角色，才能进行通信，通信时，必须由主端进行查找，发起配对，建链成功后，双方即可收发数据。理论上，一个蓝牙主端设备，可同时与7个蓝牙从端设备进行通讯。一个具备蓝牙通讯功能的设备， 可以在两个角色间切换，平时工作在从模式，等待其它主设备来连接，需要时，转换为主模式，向其它设备发起呼叫。一个蓝牙设备以主模式发起呼叫时，需要知道对方的蓝牙地址，配对密码等信息，配对完成后，可直接发起呼叫。

- 蓝牙的呼叫过程
蓝牙主端设备发起呼叫，首先是查找，找出周围处于可被查找的蓝牙设备。主端设备找到从端蓝牙设备后，与从端蓝牙设备进行配对，此时需要输入从端设备的PIN码，也有设备不需要输入PIN码。配对完成后，从端蓝牙设备会记录主端设备的信任信息，此时主端即可向从端设备发起呼叫，已配对的设备在下次呼叫时，不再需要重新配对。已配对的设备，做为从端的蓝牙设备也可以发起建链请求，但做数据通讯的蓝牙模块一般不发起呼叫。链路建立成功后，主从两端之间即可进行双向的数据或语音通讯。在通信状态下，主端和从端设备都可以发起断链，断开蓝牙链路。

- 蓝牙一对一的串口数据传输应用
蓝牙数据传输应用中，一对一串口数据通讯是最常见的应用之一，蓝牙设备在出厂前即提前设好两个蓝牙设备之间的配对信息，主端预存有从端设备的PIN码、地址等，两端设备加电即自动建链，透明串口传输，无需外围电路干预。一对一应用中从端设备可以设为两种类型，一是静默状态，即只能与指定的主端通信，不被别的蓝牙设备查找；二是开发状态，既可被指定主端查找，也可以被别的蓝牙设备查找建链。

## 功能概述

### 消息模块
- 支持一对一、一对多、多对多实时聊天，能传输文字、表情、图片、文件等。
对方不在线时可支持离线消息发送，在对方在线时能及时推送过去。消息支持历史消息存储与查看。

### 好友模块
- 支持附近好友添加，好友删除，好友分组显示，好友上下线提醒，好友昵称及分组名称修改。

## 运行截图
### 侧边栏
<img src="https://github.com/nxt2045/bluetooth-chat-app/tree/master/screenshot/drawer.JPEG" alt="drawer" width="300"></img>

### 首页
<img src="https://github.com/nxt2045/bluetooth-chat-app/tree/master/screenshot/home.JPEG" alt="home" width="300"></img>

### 添加好友
<img src="https://github.com/nxt2045/bluetooth-chat-app/tree/master/screenshot/add.JPEG" alt="add" width="300"></img>

### 好友配对
<img src="https://github.com/nxt2045/bluetooth-chat-app/tree/master/screenshot/connect1.JPEG" alt="connect1" width="300"></img>
<img src="https://github.com/nxt2045/bluetooth-chat-app/tree/master/screenshot/connect2.JPEG" alt="connect2" width="300"></img>

### 聊天
<img src="https://github.com/nxt2045/bluetooth-chat-app/tree/master/screenshot/chat1.JPEG" alt="chat1" width="300"></img>
<img src="https://github.com/nxt2045/bluetooth-chat-app/tree/master/screenshot/chat2.JPEG" alt="chat2" width="300"></img>


### 表情
<img src="https://github.com/nxt2045/bluetooth-chat-app/tree/master/screenshot/emoji.JPEG" alt="emoji" width="300"></img>

### 文件
<img src="https://github.com/nxt2045/bluetooth-chat-app/tree/master/screenshot/file.JPEG" alt="file" width="300"></img>


