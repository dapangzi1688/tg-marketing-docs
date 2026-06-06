# 频道营销 — 配置文件

## 频道.txt

批量加频道使用的链接或 `@username` 列表。

## 广告.txt

评论内容来源，每行一条频道消息链接：

```
https://t.me/source_channel/100
https://t.me/source_channel/101
```

主动发表评论可选择从广告频道或本文件读取。

## 采集/筛选相关

| 文件（示例） | 用途 |
|--------------|------|
| `采集的频道链接.txt` | 采集结果 |
| `可发布评论频道.txt` | 筛选后可评论频道 |

> 具体文件名以软件当前版本为准，以程序目录下实际生成的 txt 为准。

## config/Configuration.ini

与群组营销相同：存储 `client_token`、`client_code` 等授权信息。

## log/ 目录

详见 [主动发表评论 — 日志](active-comment.md#主要日志log)。
