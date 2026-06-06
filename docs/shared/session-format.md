# Session 协议与转换

## 问题现象

加载 session 报错：

```
no such column: version
```

## 原因

Pyrogram 的 session 数据库列名与 Telethon 不兼容（Pyrogram 用 `number`，Telethon 查 `version`）。

## 自动处理（推荐）

`load_clients()` 连接前会：

1. 识别 session 格式（pyrogram / telethon / invalid）
2. Pyrogram → 自动转为 Telethon 并验证
3. 无效文件 → 移入 `异常账号/`

## 手动转换

**群组营销** 综合菜单 → **16.py转换tl**（适合批量处理外部目录 session，先删后读）。

## 旧版 Telethon session

缺少 `version` 表的旧 Telethon 文件会自动补表并验证，无需手动操作。

## 注意

* 转换失败时源文件可能已被删除，请提前备份
* 同一 session 不要在转换过程中被其他程序占用
