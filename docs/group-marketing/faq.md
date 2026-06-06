# 群组营销 FAQ

## 为什么没有加载到账号？

* session 不在 `账号/` 或已移入 `异常账号/`
* 其他框架协议 session 转换失败
* 同一 session 在其他地方同时登录导致失效

## 群发后很多号进双向限制账号？

* 间隔太短、单号群太多、同 IP 账号过多
* 见 [降低封号风险建议](../shared/safety-tips.md)

## no such column: version

其他框架协议 session 被本框架协议直接读取导致。软件会自动转换；失败请用手动 **16.py转换tl** 或移出损坏文件。

## 检测账号时打印两遍「正在加载账号」？

`check_accounts` 会先提示双向选项再调用 `load_clients()`，属当前设计。

## exe 和源码行为不一致？

需用最新源码重新打包 exe，旧 exe 可能缺少 session 修复、双向验证等逻辑。

## Constructor ID / TL 解析错误？

升级本框架协议到较新版本（Layer 220+），或减少拉群列表时的异常群。
