# Whouse

个人项目仓库。

- 本地路径：`D:\Whouse`
- 远端仓库：https://github.com/Rusher114514/git

## 本机环境适配

这台机器访问 GitHub 有三处特殊限制，仓库已在**本地 git 配置**里做好适配，因此在你自己的终端里直接 `git push` / `git pull` 即可，无需额外参数（前提是本机的 Clash 代理已开启）：

| 限制 | 现象 | 适配方式 |
|---|---|---|
| `hosts` 文件屏蔽 GitHub | `github.com`、`api.github.com` 等被指向 `127.0.0.1` | `http.proxy = http://127.0.0.1:7897` |
| schannel 无法获取 TLS 凭据 | `AcquireCredentialsHandle failed: SEC_E_NO_CREDENTIALS` | `http.sslBackend = openssl` |
| 代理环境变量未持久化 | 新开的终端里没有 `http_proxy` | 代理已写进本仓库配置，不依赖环境变量 |

登录凭据存放在 Windows 凭据管理器（Git Credential Manager），`git push` 不会再次询问账号密码。

> 若 Clash 的端口不是 7897，请更新：`git config --local http.proxy http://127.0.0.1:<端口>`

## 常用检查

```powershell
git config --local --list
git ls-remote origin
git status
```

## 初始提交

由 DeepSeek Harness 初始化并推送到 GitHub。
