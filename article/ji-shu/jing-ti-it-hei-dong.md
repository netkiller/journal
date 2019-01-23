---
layout: journal
title: 警惕IT黑洞
date: '2016-05-09T19:30:00.000Z'
categories: management technology
---

# 警惕IT黑洞

## 什么是IT黑洞

IT黑洞是指企业在利用信息技术进行经营管理时，巨额的软硬件或软件投资并不能给企业带来预期的管理效率，企业在这方面的投资好像陷入一个“黑洞”的现象。

产生IT黑洞原因是，运维管理层没有能力解决生产中遇到的问题，害怕承担责任，从而将风险转嫁给第三方。试图说服企业，上了这些硬件就能保证生产安全稳定。

如此一来IT预算成倍增长，企业几乎将所有的技术都应用的生产环境中。

使用最新的防火墙，转发能力最强的路由器，吞吐最强的交换机，昂贵的负载均衡，高大上的SAN区域存储，去重复压缩备份，实时备份与恢复，主流的服务器甚至小型机。

我曾经写过一个段子调侃一下IT黑洞：

```text
要是咱做首席架构师
一定要的选Java
选最好的五星级机房
万兆骨干以太网直接接入
至少百十来个机柜吧
什么防火墙，路由器，交换机，负载均衡呀
能给他接的全给他接上
楼上有健身房，楼内有游戏室
一进门儿，甭管有事儿没事儿都得跟人家说
may i help you sir？
一口地道的英国伦敦腔儿
倍儿有面子
什么 hibernate, structs, spring,ActiveMQ 全都给我装上
别说代码多少行,光 xml 配置文件就100M多兆
一个 EMC 存储放那儿, 干啥, 存储Log4J的日志
一年服务费就得几万美金
这样一个系统, 你猜得多少码农开发, 得, 光累死的就10好几个
这样的系统能用吗? 当然不能
你还得找个外包公司, 一打 Application Server管理员, 18M认证的那种 , 24*365
在招聘几十个运维的，二十四小时候着
系统光启动就得好几天
周围的公司不是Hadoop就是BigTable
你要是用PHP, MySQL都不好意思跟人家打招呼
就是一个字儿---“贵”
一天的网络流量得花个万八千的
你说这样的开发，码畜一天的多少钱
我觉得怎么着也得四千美金吧
四千美金？！那是成本
八千美金起
你别嫌贵，还不打折
你得研究老板的心理
愿意掏几千美金租五星级机房的企业
根本不在乎再多掏两千
什么叫土豪企业你知道吗？
土豪企业就是
买什么东西都买最贵的，不买最好的
所以，我们做项目的口号就是
不求最好，但求最贵．
```

设备该上的都上了，事故该来的仍然会来，使用第三方企业提供的解决方案未必靠谱，昂贵的硬件与软件投资并没有为创造出应有的价值。

起初IBM,EMC,VMware,Oracle,Microsoft,SAP 等等企业针对不同行业提出很多解决方案，例如ERP,CRM,零售业，航空业解决方案等等。 传统行业经过半个世纪发展，提炼，已经有一个完整、完善、科学的管理方法，流程明确，如制造业有ISO标准，这些软件企业经过漫长需求收集整理最终针对不同行业开发出完善的产品与行业解决方案。 这些方案在传统企业是成功的，我们可以看到IBM,SAP,Oracle在各种传统行业取得了辉煌的成功。

然而，进入90年代，这种传统企业管理模式越来越跟不上时代的步伐，新经济时代的到来致使企业所处的时代背景和竞争环境发生了根本性的变化。 软件供应商的传统解决方案也不适合当下的企业，日益显露出其弊端。传统软件开发方式，一年过半年发布一个版本已经不能适应互联网时代，我们需要一周甚至每天一个版本。尤其在当前中国互联网大环境下，每天可能频繁更新数个版本到生产环境。

1. 技术创新持续进行、速度不断加快，企业竞争优势主要来自创新。随着科技的日新月异，人们的生活节奏越来越快以及对个性的追求，产品的生命周期不断缩短。 与工业经济时代不同，创新\(Innovation\)成为知识经济时代的首要目标。人们通过有计划的、连续不断的创新来赢得市场的竞争优势。 也就是说在知识经济时代创新不再具有一定的阶段性，产品变化不再具有相对稳定性的特点，从而企业通过将产品生产分解再分解，使生产的每一步骤规范化和简单化，并通过规模化大生产降低生产成本，获得市场竞争优势的历史成为过去。
2. 顾客需求瞬息万变，产品周期不断缩短。在知识经济时代，那种”生产什么就卖什么”的时代已经一去不复返了。如今的”买方市场”使顾客的选择范围大大拓宽，也使得他们对产品的期望值在不断提高，他们不再满足于合理的价格，而且还要追求产品的个性化，企业往往要根据顾客的需求”量体裁衣”。同时，市场竞争加剧，大量的替代产品使得任何一家企业都无法垄断市场，而贸易壁垒的取消还意味着顾客不仅仅可以从本国产品还能从外国产品中寻求其最佳利益，于是顾客不再有耐心为某一种产品而长时间地等待了。 企业如果不能即时对市场需求变化做出快速响应，不能在短时间内开发、生产并销售出其产品，企业就会被淘汰出局。
3. 竞争空间不断扩大，激烈程度不断加剧。随着全球经济一体化，企业竞争将不再受地域限制，任何企业都要承受来自国际化企业发展的竞争压力。另一方面，中小企业如雨后春笋，进行专业化灵活多便的生产或服务，并以其低成本运营对规模化企业高成本运营直接产生竞争威胁。

## IT黑洞产生的原因分析

### 人的因素

1. 企业重管理，轻技术。趋向于管理层把人管好，而不是充分授权技术人员，重视技术研发。
2. 管理层没有能力解决生产中遇到的问题
3. 害怕承担责任，如果在生产环境使用MySQL出了问题怎么办，谁能承担责任？不如使用Oracle，出现问题厂家上门解决，将责任转嫁给厂商。
4. 求稳心态，不做事就不会出事，不要在我任上出事，评价下属工作的标准是办事的准确度如何，任何冒险与创新的行为都是不受欢迎的。 因此极大地抑制了成员自我决策的积极性与创造性。导致员工技能单一，适应性差，员工缺乏积极性、主动性、责任感差，致使工作和服务质量下降。

### 来自组织架构的问题

传统的企业组织理论告诉我们，当组织规模扩大到一定程度，必须通过增加管理层次来保证有效领导。在企业规模一定的情况下，管理幅度与管理层次成反比。当企业发展到一定规模后，这种管理体制的弊端就突显出来。

组织层次过多，各部门按专业职能划分，组织机构臃肿，助长官僚作风 这些都是出现IT黑洞的主要原因。各部门只关心本部门的工作，并以达到上级部门满意为准，缺乏合作与服务意识。 各部门往往会从自己局部的利益出发，精心构思自己的行为，使自己的目标凌驾于整个组织的目标之上。这种分散主义和利益分歧，或许能够实现局部利益的提高，但却弱化了整个组织的功效。

延伸阅读《Netkiller 系列 手札》

## 作者

陈景峰，昵称 Netkiller, 英文名 Neo 《Netkiller 系列 手札》电子书的作者，读者QQ群：128659835，个人网站：[http://netkiller.github.io/](http://netkiller.github.io/)

转载请注明出处与作者声明

2015-8-4
