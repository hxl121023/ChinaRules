# ChinaRules

中国域名与 IP 规则库，Anywhere 路由规则集（`.arrs`）格式。

## 文件

**ChinaMax.arrs** —— 一个文件全包，导入 Anywhere 后是一套「直连」规则：

| 类型 | 代码 | 条数 |
|---|---|---|
| 域名后缀 | 2 | 143639 |
| IPv4 CIDR（中国 IP 段） | 0 | 7679 |
| IPv6 CIDR（中国 IP 段） | 1 | 4520 |
| **合计** | | **155838** |

直链（免登录可拉）：

```
https://raw.githubusercontent.com/hxl121023/ChinaRules/main/ChinaMax.arrs
```

在 Anywhere 里添加远程规则集时填这个链接即可。

## 数据来源与比对

经过两轮全网比对查漏补缺：先比对常见渠道，再挖不常见渠道，逐源统计现库未覆盖的部分并并入（域名并集去重去冗余、IP 段并集聚合）。

- 域名：[APNIC](https://ftp.apnic.net/stats/apnic/delegated-apnic-latest) 之外的大陆域名集 —— felixonmars/dnsmasq-china-list、Loyalsoldier direct、MetaCubeX geosite-cn、chikacya（CN_Additional / ChinaDomain / Geosite_CN / CN_Accelerated）、Sukka domestic、353355 cn-additional 原文、Aethersailor Custom_Direct、momokind 直连补充、ACL4SSR ChinaDomain
- IP：APNIC 官方分配表、chikacya ChinaIP / GeoIP_CN（Country.mmdb）、blackmatrix7 ChinaIPs、misakaio/chnroutes2（BGP）、gaoyifan/china-operator-ip（BGP）、firehol ipip_country_cn、17mon china_ip_list、ChanthMiao China-IPv6-List

注：blackmatrix7 的 ChinaMax 域名文件本体没拉到（其 GitHub 镜像只剩 1.1 KB 残文件、GitLab 在机器人墙后），但它的 IP 文件已并入，且其域名上游（felixonmars + GeoIP 系）都在并集里。域名关键词（DOMAIN-KEYWORD）类规则口径不一、容易误伤，未并入。

更新于 2026-11-09。
