# lax.pro.malibu：年付49.9美元拿下三网CN2 GIA回程，DMIT洛杉矶限量VPS选购与对比全解

很多人第一次看到 lax.pro.malibu 这个字符串，是在某个论坛帖子的标题里。点进去发现是 DMIT 的一款洛杉矶限量年付套餐，三网 CN2 GIA 回程、AMD EPYC 平台、49.9 美元一年，配的回复大半是"还有货吗""蹲一个补货"。这篇就把这个套餐到底是什么、值不值、跟同门其它方案怎么选、买之前要留意哪些坑，一次讲清楚。

## 这个套餐到底是什么

DMIT 是一家 2018 年开始运营的 VPS 商家，注册在纽约，团队和支持都偏中文用户，主打中国大陆方向的网络质量。LAX Pro 系列是它洛杉矶 Premium Network 产品线，三网回程统一走中国电信 CN2 GIA（AS4809）。

LAX.Pro.MALIBU（完整产品编号 LAX.AN4.Pro.MALIBU）是这个系列里三款限量年付套餐的中间档。配置如下：

| 项目 | 规格 |
| --- | --- |
| CPU | 1 vCPU（AMD EPYC 9004 系列，Zen 4） |
| 内存 | 1 GB |
| 存储 | 20 GB SSD |
| 端口 | 1 Gbps |
| 月流量 | 1 TB |
| IP | 1 IPv4 + 1 IPv6 /64 |
| 网络 | Premium Network Profile |
| 价格 | 49.9 USD / 年 |
| 测试 IP | 154.17.2.2（LAX Pro 节点） |

路由方式跟整个 Pro 系列一致：去程中国电信走 CN2 GIA、中国联通走 AS4837 直连、中国移动走 CMI（AS58453）；回程三网统一走 CN2 GIA（AS4809）。回程这点是 Pro 系列跟很多"伪 CN2"商家的核心区别——不少商家只在去程挂个 CN2 标签，回程还是普通 AS4134，晚高峰该堵还是堵。DMIT Pro 系列把回程也锁在 GIA 上，这是它价格不低但论坛里口碑稳定的主要原因。

硬件平台这块要单独说一下。DMIT 洛杉矶当前同时跑了三个 AMD EPYC 平台：AS3（7003 系列，Zen 3）、AN4（9004 系列，Zen 4）、AN5（9005 系列，Zen 5）。限量套餐只锁在 AN4，所以 Malibu 拿到的是 Zen 4 核心。同价位里这个不算最新，但比很多对手还在用的 Intel Xeon E5 老平台要新一截。

超流量策略是 DMIT 这两年新加的。月流量跑满之后不会断网，端口降速到 2 Mbps 继续跑，下个月自动恢复。Malibu 的降速档是 2 Mbps，对于轻度使用来说能撑住基础连接，但显然扛不住任何正经的视频或大文件传输。

👉 [查看 LAX.Pro.MALIBU 当前是否在售](https://www.dmit.io/aff.php?aff=18446&pid=186)

## 同系列三款限量年付套餐对比

Malibu 不是孤立的，它夹在 WEE 和 PalmSpring 之间。三款都是限量补货、年付计费、共享同一套 CN2 GIA 路由，区别只在 CPU、内存、流量和端口速率上。把三者放一起看，更容易判断自己到底需要哪一档。

| 套餐 | vCPU | 内存 | SSD | 月流量 | 端口 | 年付价格 | 购买 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| LAX.Pro.WEE | 1 | 1 GB | 20 GB | 500 GB | 500 Mbps | 36.9 USD | [购买 WEE](https://www.dmit.io/aff.php?aff=18446&pid=183) |
| **LAX.Pro.MALIBU** | **1** | **1 GB** | **20 GB** | **1 TB** | **1 Gbps** | **49.9 USD** | [购买 Malibu](https://www.dmit.io/aff.php?aff=18446&pid=186) |
| LAX.Pro.PalmSpring | 2 | 2 GB | 40 GB | 2 TB | 2 Gbps | 100 USD | [购买 PalmSpring](https://www.dmit.io/aff.php?aff=18446&pid=182) |

WEE 跟 Malibu 差 13 美元，换来的是流量翻倍（500GB→1TB）、端口从 500Mbps 升到 1Gbps。如果月用量经常贴着 500GB 走，这 13 美元花得不冤。如果用量本来就只有一两百 GB，WEE 完全够，没必要上 Malibu。

PalmSpring 直接翻到 100 美元，但配置也翻了一倍：2 核、2GB 内存、40GB SSD、2TB 流量、2Gbps 端口。它最适合的是"想年付锁定价格、又嫌 1GB 内存太局促"的用户——比如想跑个 WordPress 加 MySQL，或者挂个小 API 服务，2GB 内存是能跑得舒服的最低门槛。

> 三款都是限量补货，DMIT 不补货时不定期断货，看到有货又确实需要的话，等待通常不是最优策略。

## Pro 标准月付套餐：完整价格表

限量套餐断货的时候，Pro 系列还有八档标准套餐，按月计费、长期在售。当前 DMIT 官网 Pricing Page 把这些套餐按硬件平台拆成了三套价格：AS3（Zen 3，最便宜）、AN4（Zen 4，中间）、AN5（Zen 5，最贵）。同一个套餐名在不同平台下是不同的价格和 PID 体系，下面这个表把三档价格都列出来，方便横向比较。

> 说明：TINY / Pocket / STARTER 三档目前在官网只展示 AS3 平台价格；MINI 及以上才有 AS3、AN4、AN5 三档可选。所有套餐均为 1 IPv4 + 1 IPv6 /64（MEDIUM 及以上含 2 个 IPv4，GIANT 含 3 个），全部 KVM 虚拟化，端口速率均为 VirtIO 接口峰值速率，实际速率受 VM 性能和国际链路状况影响。

| 套餐 | vCPU | 内存 | SSD | 月流量 | 端口 | AS3 月付 | AN4 月付 | AN5 月付 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| TINY | 1 | 2 GB | 20 GB | 1 TB | 1 Gbps | $10.90 | — | — |
| Pocket | 2 | 2 GB | 40 GB | 1.5 TB | 4 Gbps | $16.90 | — | — |
| STARTER | 2 | 2 GB | 80 GB | 3 TB | 10 Gbps | $34.90 | — | — |
| MINI | 4 | 4 GB | 80 GB | 5 TB | 10 Gbps | $62.90 | $72.90 | $79.90 |
| MICRO | 4 | 4 GB | 160 GB | 7 TB | 10 Gbps | $87.90 | $102.90 | $110.90 |
| MEDIUM | 6 | 8 GB | 160 GB | 15 TB | 10 Gbps | $199.90 | $239.90 | $289.90 |
| LARGE | 8 | 16 GB | 320 GB | 25 TB | 10 Gbps | — | $459.90 | $499.90 |
| GIANT | 12 | 24 GB | 640 GB | 50 TB | 10 Gbps | — | $929.90 | $1009.90 |

购买入口（按套餐名拼接 AFF 链接，硬件平台在订单页选择）：

- 👉 [购买 TINY](https://www.dmit.io/aff.php?aff=18446&pid=100)
- 👉 [购买 Pocket](https://www.dmit.io/aff.php?aff=18446&pid=137)
- 👉 [购买 STARTER](https://www.dmit.io/aff.php?aff=18446&pid=56)
- 👉 [购买 MINI](https://www.dmit.io/aff.php?aff=18446&pid=58)
- 👉 [购买 MICRO](https://www.dmit.io/aff.php?aff=18446&pid=81)
- 👉 [购买 MEDIUM](https://www.dmit.io/aff.php?aff=18446&pid=82)
- 👉 [购买 LARGE](https://www.dmit.io/aff.php?aff=18446&pid=61)
- 👉 [购买 GIANT](https://www.dmit.io/aff.php?aff=18446&pid=98)

> DMIT 官网注明："The products and prices in the table may not be updated in time due to adjustment, for reference only." 实际下单前请以订单页实时价格为准。

标准月付套餐跟限量年付套餐的关键差异，不只在计费周期上。限量套餐是 DMIT 周期性放出的促销档位，价格已经压到接近成本，不能用任何优惠码叠加；标准套餐价格更高但库存稳定，时常会有节日活动覆盖（比如圣诞、黑色星期五）。如果 Malibu 断货又不想等补货，TINY 是结构上最接近的替代——1 核 2GB、20GB SSD、1TB 流量、1Gbps，月付 $10.90，年付算下来比 Malibu 贵一截但内存翻倍。

## Pro 和 EB 怎么选

DMIT 洛杉矶除了 Pro 系列，还有平行的 EB（Eyeball）系列，同样是 AMD EPYC 平台，同样是洛杉矶机房，但回程路由不一样。

**Pro 系列**：三网回程统一 CN2 GIA（AS4809）。晚高峰延迟更稳、丢包更低，适合对回程质量敏感的场景——跨境访问、面向国内用户的网站、对延迟敏感的代理。

**EB 系列**：三网回程走 CMIN2（中国移动国际，AS58807）。成本更低，对大多数日常用途（内容消费、轻度建站、文件中转）完全够用，但在晚高峰的稳定性上比 Pro 弱一档。EB 的去程是中国电信/联通走 CN2、中国移动走 CMIN2。

EB 系列也有自己的三档限量年付套餐，跟 Pro 一一对应：

| 套餐 | vCPU | 内存 | SSD | 月流量 | 端口 | 年付价格 | 购买 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| LAX.EB.WEE | 1 | 1 GB | 20 GB | 1 TB | 1 Gbps | 39.9 USD | [购买 EB.WEE](https://www.dmit.io/aff.php?aff=18446&pid=188) |
| LAX.EB.CORONA | 1 | 1 GB | 20 GB | 1.5 TB | 2 Gbps | 49.9 USD | [购买 EB.CORONA](https://www.dmit.io/aff.php?aff=18446&pid=218) |
| LAX.EB.FONTANA | 2 | 2 GB | 40 GB | 2.5 TB | 4 Gbps | 100 USD | [购买 EB.FONTANA](https://www.dmit.io/aff.php?aff=18446&pid=219) |

同一个 49.9 美元价位上，Pro.MALIBU 给的是 1Gbps 端口 + 1TB 流量 + CN2 GIA 回程，EB.CORONA 给的是 2Gbps 端口 + 1.5TB 流量 + CMIN2 回程。EB 用更高端口和更多流量换来了更便宜的路由。如果你主要用途是带宽消耗型（看视频、下文件），CMIN2 实际体验差距没那么大，EB.CORONA 的纸面参数更香。如果你需要的是稳定的低延迟、晚高峰不掉速，那 Pro.MALIBU 的 GIA 回程是值得多花钱的地方。

## Malibu 真的值 49.9 美元一年吗

这是搜 lax.pro.malibu 的人最想知道的一件事。把它拆开看：

**1 GB 内存能跑什么。** 单一用途的服务基本够——一个轻量代理、一个个人静态站、一个 Telegram bot、一个监控探针、一个 SSH 跳板。要跑 LAMP/LEMP 加 MySQL 这种组合，1GB 会很局促，建议直接看 PalmSpring 或 TINY。Docker 也行，但只能同时跑一两个轻量容器。

**1 TB 月流量够不够。** 对个人轻度使用绰绰有余。纯文字站、API 中转、SSH 日常操作，月用量通常在几十 GB 量级。但如果你打算挂代理看视频或者做下载中转，1TB 撑不了一个月——这种场景要么选 PalmSpring（2TB），要么直接上 STARTER 以上的大流量档。

**和同价位对手比。** 同档 CN2 GIA VPS 里被讨论最多的是搬瓦工那款 99.99 美元/年的 CN2 GIA-E 套餐，配置接近（1 核 1GB / 20GB SSD / 1TB 流量 / 2.5Gbps 端口），回程同样三网 GIA。Malibu 49.9 美元相当于对折，硬件更新（搬瓦工部分机房还在用老 Xeon），端口速率低一些（1Gbps vs 2.5Gbps）但 1TB 流量本来跑不满 1Gbps。如果是预算敏感、又确实需要 GIA 回程，Malibu 是当前市场上同路由等级里最便宜的一档。

**断货和补货规律。** DMIT 的限量套餐不是常年在售，会周期性补货，常见补货节点是国内的购物节（双十一、双十二、年货节），偶尔也会有非节假日的零星补货。补货信息通常通过官方 Telegram 频道（@dmitnews）和论坛帖子扩散。Malibu 比 WEE 流量大、比 PalmSpring 便宜，是三档里关注度最高的一档，断货速度通常也最快。

> 如果你打开页面看到 Malibu 显示缺货，又不急，可以蹲 @dmitnews 等补货通知；如果手头有具体任务在等，TINY 是结构最接近的常售替代，年付价格会高一些但不会再断货。

## 买之前要知道的几件事

**SSH key 登录，不开放密码 SSH。** DMIT 默认只接受 SSH 公钥认证，下单时需要上传或粘贴公钥。如果你之前只用过密码登录，需要先在本地生成一对密钥（`ssh-keygen`），再把 `~/.ssh/id_ed25519.pub` 的内容填到订单里。DMIT 知识库有完整指引。

**KVM 虚拟化，不是 OpenVZ。** 这意味着你拿到的是接近完整 Linux 内核的隔离环境，可以装 Docker、改内核参数、跑自定义内核模块，不像 OpenVZ 那样一堆限制。对想折腾的人是好消息。

**IPv6 路由不走 GIA。** Pro 系列的 IPv4 走 CN2 GIA，但 IPv6 走的是中国电信普通网络（AS4134），不是 GIA。绝大多数场景下这不是问题——国内 IPv6 出口本来就不像 IPv4 那么拥堵，且很多用户主要用 IPv4。但如果你做的事情重度依赖 IPv6（比如某些 IPv6-only 的服务），需要在评估时把这点算进去。

**IP 被墙可以换。** DMIT 的政策是每 15 天允许一次免费 IP 更换（前提是被墙），超过这个频率每次 5 美元。对面向国内用户的代理用途，这个政策实际意义不小——CN2 GIA 的 IP 一旦被识别封锁，免费换一次能救急。

**3 天退款窗口。** 新购订单支持 3 天内全额退款，超过 3 天不退。退款时 IP 必须仍在可正常访问区域（如果是因为滥用被封的 IP 不在退款范围）。这个窗口比业内常见的 30 天短不少，下单后最好第一时间跑一遍基础测试：延迟、丢包、晚高峰速率、能不能连上目标服务。

**支付方式。** PayPal、支付宝、信用卡都支持。支付宝对国内用户友好。

## 当前可用的优惠信息

**限量套餐无优惠码。** WEE、Malibu、PalmSpring 三款限量年付套餐本身已经是 DMIT 的促销定价，下单时直接显示折后价，不需要输入任何优惠码，DMIT 也不接受对这些套餐叠加优惠码。

**2025 圣诞活动已结束。** DMIT 在 2025 年 12 月办过一轮圣诞促销，覆盖 Pro 和 EB 标准套餐（STARTER 及以上年付），活动已经结束，相关优惠码（如 `2025-XMAS-LAX-PRO-EB-ANNUALLY-STARTER-AND-HIGHER-15OFF-RECURRING`）不再适用。下一轮大型促销通常出现在黑色星期五前后，可以关注官方 Telegram 频道获取最新活动信息。

**标准套餐的日常优惠。** 标准 Pro 和 EB 套餐在大型节日活动期间通常会有循环折扣码放出，平时不一定有。如果你打算买标准月付套餐又不急着当下入手，等节日窗口再下单能省一截。

👉 [前往 DMIT 查看当前在售套餐和活动](https://bit.ly/DmiT)

## 什么样的人适合 Malibu

把上面的信息收一下，结论挺清楚的：

**适合 Malibu 的人：**

- 预算在 50 美元/年左右，明确需要 CN2 GIA 回程
- 用途是个人轻度任务：小代理、个人站、bot、跳板、监控
- 月流量预期在 1TB 以内
- 接受 1GB 内存的限制，不打算跑数据库或重应用
- 看到有货时愿意果断下手，能接受断货要等的现状

**不适合 Malibu 的人：**

- 需要跑 MySQL、WordPress、多容器 Docker 这些吃内存的负载——直接看 PalmSpring 或 TINY
- 月流量超过 1TB（视频、大文件中转）——看 PalmSpring 或 STARTER 以上
- 需要 10Gbps 端口应对并发或大文件分发——最低要 STARTER
- 重度依赖 IPv6 走 GIA——Pro 系列的 IPv6 走 AS4134，不是 GIA
- 想买一台长期稳定供货的机器，不愿意蹲补货——直接选标准月付套餐

Malibu 的真正价值是它把"三网 CN2 GIA 回程 + AMD EPYC"的组合压到了 49.9 美元/年这个档位，同路由等级的对手基本都要 80 美元以上。它的短板也很明确——1GB 内存、限量断货。如果你清楚自己要的是路由质量而不是计算规模，并且能在它有货的时候下手，这个套餐在当下的洛杉矶 CN2 GIA VPS 市场上确实是少数几个值得直接入手的选项之一。

如果当下打开页面发现 Malibu 已经断货，又不想等补货，最近的替代是同系列的 WEE（年付 36.9 美元，500GB 流量）或者标准月付的 TINY（1 核 2GB、月付 10.90 美元起）。前者更便宜但流量更紧，后者内存翻倍但年付总价更高。三个选项怎么取舍，看你更看重流量、内存还是锁定的年付价格。

👉 [查看 DMIT 洛杉矶全部套餐当前状态](https://bit.ly/DmiT)
