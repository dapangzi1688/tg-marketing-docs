# 账号与 Session

## session 文件

* 路径：`账号/你的账号名.session`
* 一个 session 对应一个 Telegram 用户号
* 附属文件 `-journal`、`-wal`、`-shm` 由 SQLite 自动生成，移动账号时会一并处理

## 支持的格式

| 格式 | 说明 |
|------|------|
| Telethon | 标准格式，直接使用 |
| Telethon 旧版 | 缺少 `version` 表时自动修复 |
| Pyrogram | 加载时自动转为 Telethon |
| 无效/损坏 | 移入 `异常账号/` |

## 账号归档文件夹

| 文件夹 | 触发条件 |
|--------|----------|
| `异常账号/` | 未授权、冻结、session 损坏、顶号等 |
| `双向限制账号/` | SpamBot 确认账号级双向限制 |
| `无群组账号/` | 群组营销：没有可发消息的群 |

## 检测账号（菜单 06）

两套软件均提供 **检测账号**：

1. 加载 `账号/` 下所有 session
2. 可选：是否通过 @SpamBot 检测双向（输入 `y` / `n`）
3. 自动移走冻结、双向、无效 session

## 相关文档

* [Session 协议与转换](../shared/session-format.md)
* [双向限制与解除](../shared/spam-restriction.md)
