# ChinaRules

中国域名与 IP 规则库，Anywhere 路由规则集（`.arrs`）格式。

## 文件

**ChinaMax.arrs** —— 一个文件全包，导入 Anywhere 后是一套「直连」规则：

| 类型 | 代码 | 条数 |
|---|---|---|
| 域名后缀 | 2 | 143250 |
| IPv4 CIDR（中国 IP 段） | 0 | 5645 |
| IPv6 CIDR（中国 IP 段） | 1 | 2294 |
| **合计** | | **151189** |

直链（免登录可拉）：

```
https://raw.githubusercontent.com/hxl121023/ChinaRules/main/ChinaMax.arrs
```

在 Anywhere 里添加远程规则集时填这个链接即可。

## 数据来源与比对

2026-11-09 全网比对过一轮并查漏补缺，合并了这些公开直连集（域名并集去重去冗余、IP 段并集聚合）：

- IP 段：[APNIC](https://ftp.apnic.net/stats/apnic/delegated-apnic-latest) 官方分配表 CN 段 + chikacya 的 ChinaIP / GeoIP_CN（源自 Country.mmdb）
- 域名：[felixonmars/dnsmasq-china-list](https://github.com/felixonmars/dnsmasq-china-list)、[Loyalsoldier/v2ray-rules-dat](https://github.com/Loyalsoldier/v2ray-rules-dat) direct 列表、[MetaCubeX/meta-rules-dat](https://github.com/MetaCubeX/meta-rules-dat) 的 geosite-cn、[chikacya/anywhere-rules](https://github.com/chikacya/anywhere-rules) 的 CN_Additional / ChinaDomain / Geosite_CN / CN_Accelerated、[Sukka](https://ruleset.skk.moe) domestic

注：blackmatrix7 的 ChinaMax 本体文件这次没拉到（其 GitHub 镜像只剩 1.1 KB 残文件、GitLab 在机器人墙后），但它的上游（felixonmars + GeoIP）都在上面的并集里。域名关键词（DOMAIN-KEYWORD）类规则口径不一、容易误伤，未并入。

更新于 2026-11-09。
