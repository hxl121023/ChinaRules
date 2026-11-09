# ChinaRules

中国域名与 IP 规则库，Anywhere 路由规则集（`.arrs`）格式。

## 文件

**ChinaMax.arrs** —— 一个文件全包，导入 Anywhere 后是一套「直连」规则：

| 类型 | 代码 | 条数 |
|---|---|---|
| 域名后缀 | 2 | 110146 |
| IPv4 CIDR（中国 IP 段） | 0 | 5498 |
| IPv6 CIDR（中国 IP 段） | 1 | 2018 |
| **合计** | | **117662** |

直链（免登录可拉）：

```
https://raw.githubusercontent.com/hxl121023/ChinaRules/main/ChinaMax.arrs
```

在 Anywhere 里添加远程规则集时填这个链接即可。

## 数据来源

- IP 段：[APNIC](https://ftp.apnic.net/stats/apnic/delegated-apnic-latest) 官方分配表中登记给 CN 的全部 IPv4 / IPv6 段，已做聚合
- 域名：[felixonmars/dnsmasq-china-list](https://github.com/felixonmars/dnsmasq-china-list)（accelerated-domains）+ [Loyalsoldier/v2ray-rules-dat](https://github.com/Loyalsoldier/v2ray-rules-dat) 的 direct 列表，合并去重，并去掉已被上级后缀覆盖的子域名（原列表中的精确域名在 .arrs 里同样按后缀收录，.arrs 无独立的精确域名类型）

更新于 2026-11-09。
