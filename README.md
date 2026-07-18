# edgetunnel

基于 Cloudflare Workers / Pages 的边缘隧道方案（VLESS / Trojan / Shadowsocks 等），带管理面板与订阅转换。  
本仓库是 [`cmliu/edgetunnel`](https://github.com/cmliu/edgetunnel) 的 fork。

| 项 | 值 |
|---|---|
| 仓库 | https://github.com/ZJ-zhangcn/edgetunnel |
| 分支 | `main` |
| 上游 | https://github.com/cmliu/edgetunnel |
| 与上游代码 | **基本同步上游**，本 fork 未做独立功能分叉（仅文档整理） |

## 与上游的区别

| 项 | 说明 |
|---|---|
| 功能代码 | 跟随上游 `main` |
| 文档 | 中文短说明 + fork 元信息；完整图文仍以上游为准 |
| 用途 | 便于自用收藏 / 同步；需要最新特性时对照上游 Release |

若你需要可感知的功能差异，请直接跟上游；本 fork 不维护平行功能树。

## 部署方式

### 方式 A：Cloudflare Workers

1. Fork/使用本仓库（或上游）到你的 GitHub  
2. 在 Cloudflare 创建 Worker，连接该仓库或上传构建产物  
3. 按上游文档配置环境变量、KV / 绑定  
4. 打开管理面板完成节点与订阅设置  

上游图文：https://cmliussss.com/p/edt2/

### 方式 B：Cloudflare Pages

同样按上游 Pages 流程（GitHub 连接或直接上传）。注意 Pages/Workers 绑定差异以上游说明为准。

### 方式 C：同步上游

仓库带 `sync` 类 workflow 时可 `workflow_dispatch` 同步；也可手动：

```bash
git clone https://github.com/ZJ-zhangcn/edgetunnel.git
cd edgetunnel
git remote add upstream https://github.com/cmliu/edgetunnel.git
git fetch upstream
git merge upstream/main
git push origin main
```

## 能力摘要（与上游一致）

- 协议：VLESS / Trojan / Shadowsocks 等  
- 订阅：Clash / Sing-box / Surge 等  
- 链式：ProxyIP、SOCKS5/HTTP、优选 API  
- 面板：配置、日志、流量相关能力（视版本）

## 验证

部署完成后打开 Worker/Pages 域名下的管理路径，生成订阅并在客户端导入测通。

变量表、排错（如 Error 1101）一律看上游文档与视频，本页不重复粘贴。
