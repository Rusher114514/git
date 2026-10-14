# Whouse

个人项目仓库，位于 `D:\Whouse`。

## 本机环境说明

这台机器上 `hosts` 文件屏蔽了 `github.com` 等域名（统一指向 `127.0.0.1`），并且 Windows schannel 无法获取 TLS 凭据，因此本仓库做了两处本地配置：

- `http.sslBackend = openssl` —— 绕开 schannel 的 TLS 失败
- 访问 GitHub 时走本地代理 `http://127.0.0.1:7897`（Clash）

推送示例：

```powershell
git -c http.proxy=http://127.0.0.1:7897 push
```

## 初始提交

由 DeepSeek Harness 初始化并推送到 GitHub。
