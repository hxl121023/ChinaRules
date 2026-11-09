# ChinaRules

中国域名与 IP 规则库：Anywhere 路由规则集（`.arrs`）与 Clash 规则（`.yaml`）两种格式。

## Anywhere 版（.arrs）

全集共 **156,804 条**（域名后缀 143,806 + IPv4 段 8,427 + IPv6 段 4,571）。

⚠️ **Anywhere 官方规定单个规则集最多 100,000 条，超限整文件拒绝导入**（见官方文档 Documentations/Routing.md 的 Limits 一节），所以全集拆成两个文件，**两个都要订阅**，动作都是直连（routing = 1）：

| 文件 | 条数 | 内容 |
|---|---|---|
| ChinaMax.arrs | 99,999 | 域名后缀 87,001 + 全部 IPv4/IPv6 段 |
| ChinaMax2.arrs | 56,805 | 其余域名后缀 56,805 |

直链（免登录可拉）：

```
https://raw.githubusercontent.com/hxl121023/ChinaRules/main/ChinaMax.arrs
https://raw.githubusercontent.com/hxl121023/ChinaRules/main/ChinaMax2.arrs
```

在 Anywhere 里添加远程规则集时把两个链接都加上即可。域名规则与 IP 规则可以混在同一个规则集里（官方文档的完整示例就是域名 + IP 同文件），拆分纯粹是因为条数上限。

## Clash 版（.yaml）

**ChinaMax.yaml** —— 同一份规则的 Clash 格式，单文件全集 156,804 条（Clash 没有 10 万条上限）：

```
https://raw.githubusercontent.com/hxl121023/ChinaRules/main/ChinaMax.yaml
```

## 数据来源与比对

经过三轮全网比对查漏补缺：先比对常见渠道，再挖不常见渠道，最后补上 blackmatrix7 本体，逐源统计现库未覆盖的部分并并入（域名并集去重去冗余、IP 段并集聚合）：

- 域名：felixonmars/dnsmasq-china-list、Loyalsoldier direct、MetaCubeX geosite-cn、chikacya（CN_Additional / ChinaDomain / Geosite_CN / CN_Accelerated）、Sukka domestic、353355 cn-additional 原文、Aethersailor Custom_Direct、momokind 直连补充、ACL4SSR ChinaDomain、blackmatrix7 ChinaMax（ChinaMax_Domain.yaml，精确域名按后缀并入）
- IP：APNIC 官方分配表、chikacya ChinaIP / GeoIP_CN（Country.mmdb）、blackmatrix7 ChinaIPs 与 ChinaMax_IP、17mon china_ip_list（全注册局合并）、firehol ipip_country_cn、misakaio/chnroutes2（BGP）、gaoyifan/china-operator-ip（BGP）、ChanthMiao China-IPv6-List

注：域名关键词（DOMAIN-KEYWORD）类规则口径不一、容易误伤，未并入。

更新于 2026-11-09。
