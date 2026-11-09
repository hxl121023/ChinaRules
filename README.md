# ChinaRules

中国域名与 IP 规则库，Anywhere 路由规则集（`.arrs`）格式。

## 文件

**ChinaMax.arrs** —— 一个文件全包，导入 Anywhere 后是一套「直连」规则：

| 类型 | 代码 | 条数 |
|---|---|---|
| 域名后缀 | 2 | 143806 |
| IPv4 CIDR（中国 IP 段） | 0 | 8427 |
| IPv6 CIDR（中国 IP 段） | 1 | 4571 |
| **合计** | | **156804** |

直链（免登录可拉）：

```
https://raw.githubusercontent.com/hxl121023/ChinaRules/main/ChinaMax.arrs
```

在 Anywhere 里添加远程规则集时填这个链接即可。

## 数据来源与比对

经过三轮全网比对查漏补缺：先比对常见渠道，再挖不常见渠道，最后补上前两轮唯一没拿到的 blackmatrix7 ChinaMax 本体（之前只拉到 1.1 KB 的 ChinaMax.yaml 残文件，完整内容实际在同仓库 rule/Clash/ChinaMax/ 下分拆为 ChinaMax_Domain.yaml 与 ChinaMax_IP.yaml 两个文件）。逐源统计现库未覆盖的部分并并入（域名并集去重去冗余、IP 段并集聚合）。

- 域名：[APNIC](https://ftp.apnic.net/stats/apnic/delegated-apnic-latest) 之外的大陆域名集 —— felixonmars/dnsmasq-china-list、Loyalsoldier direct、MetaCubeX geosite-cn、chikacya（CN_Additional / ChinaDomain / Geosite_CN / CN_Accelerated）、Sukka domestic、353355 cn-additional 原文、Aethersailor Custom_Direct、momokind 直连补充、ACL4SSR ChinaDomain、blackmatrix7 ChinaMax_Domain（110,207 后缀 + 271 精确域名，按本库口径统一按后缀并入）
- IP：APNIC 官方分配表、chikacya ChinaIP / GeoIP_CN（Country.mmdb）、blackmatrix7 ChinaMax_IP / ChinaIPs、misakaio/chnroutes2（BGP）、gaoyifan/china-operator-ip（BGP）、firehol ipip_country_cn、17mon china_ip_list、ChanthMiao China-IPv6-List

注：域名关键词（DOMAIN-KEYWORD）类规则口径不一、容易误伤，未并入。

更新于 2026-11-09。
