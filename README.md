# ChinaRules

中国域名与 IP 规则库，Clash / Mihomo `rule-provider` 格式，跟 blackmatrix7 的 ChinaMax 同款结构。

## 文件

**ChinaMax.yaml** —— 一个文件全包：

| 类型 | 条数 |
|---|---|
| DOMAIN（精确域名） | 559 |
| DOMAIN-SUFFIX（域名后缀） | 109635 |
| IP-CIDR（中国 IPv4 段） | 5498 |
| IP-CIDR6（中国 IPv6 段） | 2018 |
| **合计** | **117710** |

直链（免登录可拉）：

```
https://raw.githubusercontent.com/hxl121023/ChinaRules/main/ChinaMax.yaml
```

Clash / Mihomo 配置里这样引用：

```yaml
rule-providers:
  china:
    type: http
    behavior: classical
    format: yaml
    path: ./rules/ChinaMax.yaml
    url: "https://raw.githubusercontent.com/hxl121023/ChinaRules/main/ChinaMax.yaml"
    interval: 86400
```

## 数据来源

- IP 段：[APNIC](https://ftp.apnic.net/stats/apnic/delegated-apnic-latest) 官方分配表中登记给 CN 的全部 IPv4 / IPv6 段，已做聚合
- 域名：[felixonmars/dnsmasq-china-list](https://github.com/felixonmars/dnsmasq-china-list)（accelerated-domains）+ [Loyalsoldier/v2ray-rules-dat](https://github.com/Loyalsoldier/v2ray-rules-dat) 的 direct 列表，合并去重，并去掉已被上级后缀覆盖的子域名

更新于 2026-11-09。
