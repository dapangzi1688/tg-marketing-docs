# 小号群发

从指定**频道消息**转发到账号已加入的群组（与机器人群发的「纯文本词库」模式不同）。

## 前置条件

* `账号/` 内有 session
* `广告.txt`：每行一条频道消息链接，格式如  
  `https://t.me/频道用户名/消息ID`
* `config/Configuration.ini` 中 `channel_ID` 或从 `广告.txt` 解析频道名

## 启动流程

1. 主菜单 → `2.群发` → `2.小号群发`
2. 按提示配置发送方式、间隔、账号上限等

## 发送逻辑

* 读取 `广告.txt` 中的消息，向各群 `forward_messages`
* 支持隐藏转发来源（drop_author）等模式
* 遇 `UserBannedInChannelError` 时同样会 **SpamBot 双向验证**：
  * 未双向 → 跳过该群继续
  * 已双向 → `move_bad_account` 移入 `双向限制账号/`

## 日志

* `log/群发日志.txt` — 总日志
* `log/群发日志记录/` — 分账号记录
* 可选：日志上传到指定频道（需有效 `channel_ID`）

## 相关

* [配置文件](config-files.md)
* [机器人群发对比](mass-send-robot.md)
