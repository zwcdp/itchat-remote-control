# itchat remote control 使用说明
## 简单介绍
这是一个实现微信利用大号控制小号，使用生活号代理工作号收发消息的的Python程序，使用[@LittleCoder](https://github.com/littlecodersh)开源的WeChat的Python接口[itchat](https://github.com/littlecodersh/ItChat)。

该程序使用 python3, 依赖 itchat
```
pip install itchat
```
or
```
pip3 install itchat
```
## 程序运行
更改程序中的accout2昵称为生活号昵称，运行程序扫码登录工作号，即可利用生活号代为处理工作号消息。运行程序活动目录下生成二维码图片
```
python itchat.py
```
or
```
pip3 itchat.py
```
## 程序说明
### 私聊
#### 接收消息
工作号接收的所有文本消息,视频,语言,图片 都直接转发给生活号并注明 发送用户(备注名或昵称)

工作号接收的分享链接,音乐分享,地图 都以文本形式转发给用户并注明发送用户,可通过链接直接访问

工作号接收的红包消息,通过文本提醒发送到生活号
#### 发送消息
分为 固定用户模式发送消息 和 指定用户模式发送消息

固定用户模式发送消息:用户可以发送视频,图片,文本消息,语音 给固定用户(固定用户可以通过命令更改,通过从常用用户<程序运行后给工作号发送过消息的用户,程序记忆这些用户,重新运行程序时载入>中选择)

指定用户模式发送消息:用户在消息中指定发往用户,只能发送文本消息
### 群聊
#### 接受消息
群聊只处理文本消息

当工作号被@或者文本中包含关键词语(在代码中预设)时发送消息到生活号

所有群消息记录到活动目录下'room_history.txt'

当需要查看某群历史消息时，通过 *最近群聊* 获取 **群聊名id** ,通过 *群聊查询[int]* 
获取聊天记录文件，默认显示最近500条消息

#### 发送消息

利用 **群聊名id** 发送消息 群聊[ **群聊名id** ]--[内容] : 向该群发消息

群聊[ **群聊名id** ]--@[好友名]--[内容] : 在该群@好友并发送消息(不能@非好友)
## 使用帮助

help : 显示帮助信息

全部好友 : 获取所有好友

[好友名]--[内容] : 以指定模式发送消息

？[姓] : 查询当前姓所有好友

@@@ : 获取最近聊天好友列表

@@[int] : 设定固定模式聊天对象

@？ : 查询当前固定模式聊天对象

@[内容] : 向固定模式发送消息

最近群聊 : 获取最近聊天群组 index::群组名

群聊查询[int] : 获取该群聊聊天历史

群聊[int]--[内容] : 向该群发消息

群聊[int]--@[好友名]--[内容] : 在该群@好友并发送消息
