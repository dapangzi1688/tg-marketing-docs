# 群组营销 — 配置文件

## botconfig.txt

机器人群发、转发消息等使用的**词库**。

```
优惠
限时
点击了解
```

每行一条，发送时随机抽取最多 3 条用空格拼接。

## 广告.txt

小号群发必填；机器人群发用于日志关联。

```
https://t.me/your_channel/123
https://t.me/your_channel/124
```

## 群组.txt

加群、筛选等功能的群组链接列表。

## config/Configuration.ini

```ini
client_token=你的授权码
client_code=你的端码
api_id=2040
api_hash=...
channel_ID=频道用户名或0
delay=0
header=转发
```

| 字段 | 说明 |
|------|------|
| `channel_ID` | 小号群发默认频道；`0` 且无法从广告解析则跳过日志上传 |
| `delay` | 部分功能默认间隔 |

## 异常广告id.txt

可选：记录发送异常的频道消息 ID，用于跳过问题广告（默认功能关闭）。
