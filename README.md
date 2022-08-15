<p align="center">
  <a href="https://v2.nonebot.dev/"><img src="https://v2.nonebot.dev/logo.png" width="200" height="200" alt="nonebot"></a>
</p>

<div align="center">
<h1 align="center">🔥 nonebot_plugin_firexN</h1>

✨ 定时发送QQ消息插件 ✨

</div>

<p align="center">
  <a href="https://github.com/GC-ZF/nonebot_plugin_firexN/blob/main/LICENSE">
    <img src="https://img.shields.io/github/license/GC-ZF/nonebot_plugin_firexN" alt="license">
  </a>
  <a href="https://pypi.python.org/pypi/nonebot_plugin_firexN">
    <img src="https://img.shields.io/pypi/v/nonebot_plugin_firexN" alt="pypi">
  </a>
  <img src="https://img.shields.io/badge/python-3.7.3+-blue" alt="python">
  <img  src="https://visitor-badge.glitch.me/badge?page_id=nonebot_plugin_firexN" /><br />
</p></br>

## 插件描述

一款基于[Nonebot2](https://github.com/nonebot/nonebot2)的插件

**避免尴尬，从我做起，一起燚xN吧**

<div align="center">
  <img height="300px" src="https://test1.jsdelivr.net/gh/GC-ZF/nonebot_plugin_firexN/example.png">
</div>


定时早晚各发一条信息(以防早上忘记回复,晚上还有第二次提醒),默认调用[API](https://v1.hitokoto.cn?c=a&c=b&c=c&c=d&c=h)随机发送一句,也可以自定义发送消息的内容及时间。当然如果你愿意花一些心思去读代码,此插件还可以改成你需要的定时提醒工具(再加几个定时器,喝水小助手不就有了么！)

本人未系统学习过py,靠仅有的cpp和py的一点点理解制作的,如果有任何问题、建议,欢迎[issues](https://github.com/GC-ZF/nonebot_plugin_firexN/issues)

## 依赖
本插件依赖[定时任务](https://github.com/nonebot/plugin-apscheduler),首先确保自己有`nonebot_plugin_apscheduler`(pip list查看),安装命令
```python
pip install nonebot_plugin_apscheduler
```
## 安装
```python
pip install nonebot_plugin_firexN
```
## 配置项
在`bot.py`中添加
```python
nonebot.load_plugin("nonebot_plugin_firexN")
```
在`.evn`中配置参数说明
```python
fire_users = ["xxx","xxx"]    # 必填 联系人QQ
fire_switch_morning = False   # 选填 True/False 默认开启 早上消息推送是否开启
fire_switch_night = False     # 选填 True/False 默认开启 晚上消息推送是否开启
fire_mode = 1                 # 选填 默认模式2 模式1发送自定义句子，模式2随机调用一句
fire_sentence_moring = ["句子1","句子2","..."]    # 如果是模式1 此项必填，早上随机发送该字段中的一句
fire_sentence_night = ["句子1","句子2","..."]     # 如果是模式1 此项必填，晚上随机发送该字段中的一句
fire_time_moring = "8 0"    # 选填 早上发送时间默认为7:00
fire_time_night = "23 0"    # 选填 晚上发送时间默认为22:00                   
```
## 配置示例
模式1
```python
fire_users = ["1310446718","2689438597"]    # 必填 联系人QQ
fire_switch_morning = True    # 选填 True/False 默认开启 早上消息推送是否开启
fire_switch_night = False     # 选填 True/False 默认开启 晚上消息推送是否开启
fire_mode = 1                 # 选填 默认模式2 模式1发送自定义句子，模式2随机调用一句
fire_sentence_moring = ["🌞早，又是元气满满的一天","句子2","..."]    # 如果是模式1 此项必填，早上随机发送该字段中的一句
fire_sentence_night = ["🌛今天续火花了么，晚安啦","句子2","..."]     # 如果是模式1 此项必填，晚上随机发送该字段中的一句
fire_time_moring = "8 0"    # 选填 早上发送时间默认为7:00
fire_time_night = "23 0"    # 选填 晚上发送时间默认为22:00 
```
模式2
```python
fire_users = ["xxx","xxx"]    # 必填 联系人QQ
fire_mode = 2                 # 必填 模式1发送自定义句子，模式2随机调用一句  
```
## 补充
本插件的初衷是续火花而不是群聊定时推送，所以pip安装并没有群聊功能，如果需要你可以将仓库中`send_msg.py`，保存到在`[nb根目录]/plugins/group/send_msg.py`中
在`.evn`中配置参数说明，之后重启.py。
```python
send_group_id = ["xxx","xxx"]    # 必填 群号
send_switch_morning = False                      # 选填 True/False 默认开启 早上消息推送是否开启
send_switch_night = False                        # 选填 True/False 默认开启 晚上消息推送是否开启
send_mode = 1                 # 选填 默认模式2 模式1发送自定义句子，模式2随机调用一句
send_sentence_moring = ["句子1","句子2","..."]    # 如果是模式1 此项必填，早上随机发送该字段中的一句
send_sentence_night = ["句子1","句子2","..."]     # 如果是模式1 此项必填，晚上随机发送该字段中的一句
send_time_moring = "8 0"    # 选填 早上发送时间默认为7:00
send_time_night = "23 0"    # 选填 晚上发送时间默认为22:00                   
```
因此功能不属于本插件，另外推荐一款群管插件[yzyyz1387/nonebot_plugin_admin](https://github.com/yzyyz1387/nonebot_plugin_admin)，群聊定时推送功能已向作者提交合并申请。
## 更新记录
2022.8.15，新增消息推送开关，更改fire_mode为选填，默认模式2
```
fire_switch_morning = True    # 选填 True/False 默认开启 早上消息推送是否开启
fire_switch_night = False     # 选填 True/False 默认开启 晚上消息推送是否开启
fire_mode = 1                 # 选填 默认模式2 模式1发送自定义句子，模式2随机调用一句
```
