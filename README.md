# Wuthering Waves Global 代理分流规则

鸣潮国际服 (Wuthering Waves Global) 的 Clash / Mihomo 分流规则，命中即走代理。

## 文件

- `wuthering-waves-global.list` — classical 格式 rule-provider

## 使用 (rule-provider，可远程订阅自动更新)

```yaml
rule-providers:
  wuwa-global:
    type: http
    behavior: classical
    url: "https://raw.githubusercontent.com/Rainerhu/wuthering-waves-global-proxy/main/wuthering-waves-global.list"
    path: ./ruleset/wuwa-global.list
    interval: 86400

rules:
  - RULE-SET,wuwa-global,🎮 游戏代理
  # ... 其他规则
  - MATCH,DIRECT
```

## 覆盖范围

kurogame 官方启动器、账号、登录网关、数据上报、CDN 等域名。

> 注意：域名规则保证登录/更新/公告/资源走代理。实际对战为 UDP，服务器 IP 官方未公开且按区域变化，需 TUN + 进程规则 (`Client-Win64-Shipping.exe`) 才能覆盖对战流量。选节点建议与账号服务器同区 (美服→美国 / 亚服→日本·新加坡 / 欧服→欧洲)。
