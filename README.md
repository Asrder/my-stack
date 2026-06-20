# 🧰 我的项目收藏

> 个人在用的工具、服务、开源项目整理。持续更新中。

---

## 🌐 网络与代理

| 项目 | 用途 | 链接 |
|------|------|------|
| fscarmen/warp | Cloudflare WARP 一键脚本，换出口 IP / 补 IPv6 / 解锁流媒体 | [GitLab](https://gitlab.com/fscarmen/warp) |
| Xray-core (XTLS) | 代理核心，支持 VLESS/VMess/Trojan 等 | [GitHub](https://github.com/XTLS/Xray-core) |
| sing-box | 通用代理平台，支持多种协议 | [GitHub](https://github.com/SagerNet/sing-box) |
| 3X-UI | Xray 面板，可视化管代理节点 | [GitHub](https://github.com/MHSanaei/3x-ui) |

**常用命令速记**
```bash
# WARP 一键脚本
wget -N https://gitlab.com/fscarmen/warp/-/raw/main/menu.sh && bash menu.sh
```


## 🖥️ 服务器运维与安全

| 项目 | 用途 | 链接 |
|------|------|------|
| fail2ban | 日志监控 + 自动封禁异常 IP，防 SSH/Web 暴力破解 | [GitHub](https://github.com/fail2ban/fail2ban) |
| 666shen/tcp-dashboard | VPS TCP 深度调优面板，一键优化网络参数 | [GitHub](https://github.com/666shen/tcp-dashboard) |
| BBR | TCP 拥塞控制算法，提升网络速度（内核自带） | 内核内置 |

**fail2ban 常用命令**
```bash
# 安装并启动（Debian/Ubuntu）
apt install fail2ban -y
systemctl enable fail2ban --now

# 查看状态
fail2ban-client status
fail2ban-client status sshd

# 手动解封 IP
fail2ban-client set sshd unbanip <IP>
```


## 🛠️ 开发工具

| 工具 | 用途 |
|------|------|
| Git | 版本控制 |
| VS Code | 代码编辑器 |
| SSH | 远程连接服务器 |


## 📝 备注

### 服务器维护小贴士
- 系统提示 `Pending kernel upgrade` → 方便时 `reboot` 生效新内核
- SSH 优先用**密钥登录**，禁用密码登录更安全
- NAT VPS 上 fail2ban 的 `maxretry` 设高些，避免误封共享 IP 用户
- 重要数据定期备份，别只存在 VPS 上

### 白名单配置（防误封自己）
```ini
# /etc/fail2ban/jail.local
[DEFAULT]
ignoreip = 127.0.0.1/8 ::1 你的IP
```

---

*最后更新：2026-06-20*
