# ChinaRules

中国域名与 IP 规则库：Anywhere 路由规则集（`.arrs`）与 Clash 规则（`.yaml`）两种格式。
每日由服务器自动检测各来源更新、并入新增规则后推送本仓库。

## Anywhere 版（.arrs）

规则集名为 **MY🐲Direct**。全集共 **156822 条**（域名后缀 143823 + IPv4 段 8427 + IPv6 段 4571 + 自定义关键词 1 条）。

⚠️ **Anywhere 官方规定单个规则集最多 100,000 条，超限整文件拒绝导入**，所以全集拆成两个文件，**两个都要订阅**，动作都是直连（routing = 1）：

| 文件 | 条数 | 内容 |
|---|---|---|
| MYDirect.arrs | 99999 | 关键词 + 域名后缀前段 + 全部 IPv4/IPv6 段 |
| MYDirect2.arrs | 56823 | 其余域名后缀 |

```
https://raw.githubusercontent.com/hxl121023/ChinaRules/main/MYDirect.arrs
https://raw.githubusercontent.com/hxl121023/ChinaRules/main/MYDirect2.arrs
```

域名规则与 IP 规则可以混在同一个规则集里（官方文档示例即混排），拆分纯粹因为条数上限。

## 广告拦截版（.arrs，拒绝连接）

规则集名为 **MY🐲Block**，共 **169701 条**域名后缀，动作是拒绝连接（routing = 2）。来源：HaGeZi Light、OISD Small、EasyPrivacy、anti-AD（含中文广告与追踪域名），并集后按后缀去冗余。同样拆成两个文件，**两个都要订阅**：

| 文件 | 条数 | 内容 |
|---|---|---|
| MYBlock.arrs | 99999 | 域名后缀前段 |
| MYBlock2.arrs | 69702 | 域名后缀后段 |

```
https://raw.githubusercontent.com/hxl121023/ChinaRules/main/MYBlock.arrs
https://raw.githubusercontent.com/hxl121023/ChinaRules/main/MYBlock2.arrs
```

与直连集重叠的域名多为国内广告域名：在 Anywhere 的路由列表里把 MY🐲Block 两个集拖到 MY🐲Direct 上面，冲突时拦截优先。

## Clash 版（.yaml）

**MYDirect.yaml** —— 同一份规则的 Clash 格式，单文件全集（Clash 没有 10 万条上限）：

```
https://raw.githubusercontent.com/hxl121023/ChinaRules/main/MYDirect.yaml
```

## 数据来源

直连集经三轮全网比对查漏补缺后定下的来源（每日自动复查）：felixonmars、Loyalsoldier、MetaCubeX geosite-cn、chikacya（CN_Additional / ChinaDomain / Geosite_CN / CN_Accelerated / ChinaIP / GeoIP_CN）、Sukka、353355 cn-additional、Aethersailor Custom_Direct、momokind、ACL4SSR、blackmatrix7（ChinaMax_Domain / ChinaMax_IP / ChinaIPs）、APNIC、17mon、firehol ipip、misakaio chnroutes2、gaoyifan china-operator-ip、ChanthMiao IPv6。域名关键词类口径不一、易误伤，未并入。

更新于 2026-11-10。
