# GitBook 同步说明

本目录 `docs/` 用于 [GitBook](https://app.gitbook.com/) 发布 **TG营销软件** 文档。

## 仓库内文件

```
群组-tl/
├── .gitbook.yaml      # GitBook 配置，root 指向 ./docs/
└── docs/
    ├── README.md      # 站点首页
    ├── SUMMARY.md     # 左侧目录
    ├── getting-started/
    ├── group-marketing/    # 群组营销
    ├── channel-marketing/  # 频道营销
    └── shared/
```

## GitHub Sync 步骤（摘要）

1. 将 `docs/` 与 `.gitbook.yaml` **commit 并 push** 到 GitHub
2. GitBook → **Integrations** → 安装 **GitHub**
3. 打开 **Pang Docs**（或新建站点）→ **Git sync** → 选择仓库与分支 `main`
4. **Sync now** → 确认左侧目录与 `SUMMARY.md` 一致
5. **Publish** 获得公开链接

## 日常更新

修改 `docs/**/*.md` → `git push` → GitBook 自动同步（约 1～5 分钟）。

## 双向同步

建议新手仅使用 **GitHub → GitBook**（单向），在本地/Cursor 改 Markdown 即可。

## 文档范围

| 分支 | 对应程序 |
|------|----------|
| 群组营销 | `TG群组自动营销`（本仓库） |
| 频道营销 | `TG_ChannelMarketing`（独立目录，内容已写入 channel-marketing/） |

频道营销源码若在另一仓库，文档仍可在本 `docs/` 统一维护，无需拆站。
