项目管理辅助系统
==
projectManagementAidedSystem
==

# 个人简介
2020年7月，本人于重庆交通大学机电与车辆工程学院毕业，现就职于湖北省路桥集团有限公司，从事设备物资管理工作，因工作之需，研发了一套项目管理辅助系统。该系统于2020年9月初研发，目标是对项目部各个部门的表格数据进行整理，以便快速获取所需信息，以提升工作效率。
目前以本人所在设备物资部，进行对应开发，该系统仅供同行参考，若有较好建议，请联系作者，谢谢。该系统目前处于个人测试开发阶段，后续可根据工作需要进行改变设计。


# 1.项目辅助系统的来源和意义
本系统根据作者实际工作中遇到的问题，逐一进行尝试与解决，目的是给公司带来一定的价值，提高个人魅力:blush:

2020年毕业后，通过校招来到了湖北路桥，关于公司信息可以到百度查询，这里就不在搬砖了。刚进入公司会有大约1周的培训时间，然后就会分配工作，留在集团本部还是项目部，看个人能力了。由于本人能力一般，结束后就被分配到咸九2标项目部了，位于通山县厦铺镇，尼玛挨着三省交界的地方，具体什么情况，大家可以想象一哈，夜市，妹子什么的就不用想了。

言归正传，初到设备物资部，目前职位是料账员，每天就是做做EXCEL表格，工作没什么难度，简单来说就是每天造表，材料采购计划表，设备配置计划表，材料交接单，零星材料结算表....

造着造着，表一多，结算金额有时候就容易搞混淆，有时领导突然来句，下个月资金计划报多少？，问的你当场发门，你对领导说等一下，我找找表统计一下。。。
哈哈哈，是不是太麻烦了，要是能把之前的表统计好，然后直接查询得出结果快了吗？由于本人在大学学过一些编程知识，于是乎，搭建了一个项目管理系统，用于解决造表，结算，存储等工作。

# 2.仓库管理系统的研究现状
国内目前阿里巴巴，京东等一些物流公司在这方面做得比较出色 [<sup>1</sup>](#refer-anchor-1)，然而项目设备物资部和物流类似的作用，包含统计材料采购价格，登记物资的采购，选择供应商购买，然后发放物资等等流程，我们需确保最大减少项目部的开销，考虑购买材料成本，运输成本等。我们在构建仓库管理模块可以从物流公司学习，可以实现自动化操作，自动化填写订单，自动化验收，尽量减少人力，毕竟天天造表耗时，且没啥技术含量。

# 3.项目管理系统设计需求分析

## 3.1实践过程中出现的问题 ##
经过几个月的实习，项目管理中存在问题如下：
1. 集团公司表格众多，各种各样的表格对新人来说难以查找，随着项目的进行，电脑上会出现越来越多的EXCEL表格，表格中信息难以分析和利用。
2. 当前的网页管理平台，审批流程众多，容易造成项目部事情已办妥，而流程还在审批，且如果审批过程中出现问题，则审批时间进一步延长。如果出现审批流程不合格，则项目部已办妥的事情作废，一切从零开始，在合作企业面前显得项目部“言而无信”。
3. 仓库管理信息准确性不足，每次整理剩余量需要大量人力物力财力。
4. 零星材料结算出现混乱，容易出现重复结算。
5. 目前材料收料单，材料领料单众多，但是数据无法高效快速的进行统计利用。
6. 人员素质低，如图所示为领料单的表示方法，工字钢表示出现如下情况:
![错误2](https://github.com/FrankZhou-jun/projectManagerAidedSystem/raw/main/images/工字钢表示错误2.JPG)
领料单规格表示多样化，甚至有时候出现错误。
![错误3](https://github.com/FrankZhou-jun/projectManagerAidedSystem/raw/main/images/工字钢表示错误3.JPG)
![仓库规格表示不唯一](https://github.com/FrankZhou-jun/projectManagerAidedSystem/raw/main/images/仓库规格表示不唯一.jpg)
当作者在库中查找给钢板型号时，竟然没有找到，可能有如下原因:
（1）. 交接单出现错误，未及时纠正。
（2）. 统计人员出现错误，录入信息出现错误。
（3）. 领料单出现错误。
如果每次统计的数据不准确,创库管理信息将无法有效利用,在这个数据为王的时代，这样下去成本该如何控制？

随着不断的实习，对公司的流程也越来越熟悉，最令人头疼的某过于材料的月消耗报表，搞得你晕头转向，感觉一天就在坐在那里进行合并、拆分、求和、粘贴、复制。wc，不用你们猜，我都感觉自己像个机器人一样，当我在抱怨自己想机器人时，部长来了句，前辈们都是这么坚持过来的，你要传承下去:flushed:突然想起一句话，只要你自己不觉得尴尬，尴尬的就是别人:upside_down_face::upside_down_face::upside_down_face:。

## 3.2领导指出的问题 ##

2021年2月2日，召开了咸九2标员工座年终座谈会，袁总在会上指出问题如下：
1. 所有表格整齐划一。
2. 尽快计算出成本核算，及时得出盈亏。

本人有一些拙见如下：

针对问题1，使用固定的软件造表，即可实现表格整齐划一。例如本文所设计的软件系统，安装到个项目部，即可对统一项目的风格。确实，如果表格不整齐划一，可能会出现以下问题：1，不利于项目之间的人员调动，当员工调到新的项目，要重新学习，按照部长的要求改变之前的习惯，因为各个项目每个部长的风格不一样，且各个同学都知道，习惯一旦养成，很难更改，所以造表的人容易被上级叼来叼去，压力极大。本人在实习中就出现这样的问题，一张材料月消耗报表，按照部长的要求造好表之后给财务，而财务说这个表不是这样造的，后来了解到，部长是从枣潜一个标段调过来的，财务又从另一个地方调过来的，各个项目标段造表风格不一样，导致我在夹在两者之间，最后让他们沟通一下，这表到底怎么搞！

针对问题2，21世纪必将是一个大数据的时代，我们可以利用之前的数据进行模型训练，然后利用该模型进行模型评估，即进行成本预测。虽然目前在这方面相关研究的较少，但我相信这将是时代发展的趋势，现在最要紧的就是记录数据，不然以后都没数据可以经行研究。对一个项目的成本，分摊到各个子工程，如钢便桥工程，钢筋厂工程，拌合楼工程，每个工程都有一定的成本，这个成本可以根据历史数据或当前造价预估出来，但我觉得还是用历史数据进行分析较好，因为造价计算工程复杂，而利用历史数据只需搭建好后模型，进行训练就完了， 通过得出每个子工程的盈亏，就可以及时分析出这个项目到底是赚了还是亏了。

## 3.3实践过程中出现的发现的问题

 问题1、随着表格数量的增加，在读取数据生成目录时候出现加载数据缓慢的问题，且无法及时显示有效数据进行查看，针对此问题，重新设计目录显示类别，可按照供应商类别查看，时间查看，仓库地点查看等方式。
 问题2、文本分类问题，将初步进行探讨。

## 3.4功能更新 ##
1. 2020年10月1日-2021年2月1日，在表格打印模块添加了材料采购计划表，材料进场台账表，对促进表格整齐划一的构想迈出了一大步。
2. 2020年10月，在数据采集模块，增加了摄像功能，可对需要留存的东西拍照留底，同时可对照片生成PDF格式。解决了打印机无法扫描留底的问题，避免了手机拍照，然后在电脑与手机之间频繁传输文件的问题。
3. 2021年2月21日，在自动话办公模块增加了导出材料月消耗报表功能，具有对OA系统导出的收发明细表进行加工的功能，解决了每月需要频繁手动修改计算材料消耗月报表的耗时问题。
4. 2021年2月22日，根据集团公司下发的审计要求，增加导出材料采购台账，入库单台账功能。
5. 2021年4月7日，针对材料采购计划表中存在材料已经购买验收，而计划来不及签字的问题，对材料采购计划表进行分类，即可分为待补充签字计划，安全用品计划，总量计划，零星材料计划，废计划。
6. 2021年5月，合同、支付、结算三位一体，整合台账。
7. 2021年5月，新增合同表，扣款明细表。
8. 2021年5月，针对采购计划表中材料规格明细表出现大量的情况，为便于统一验收和领用，采用电子打印进行统一验收和领用（签字后装订成册）。
9. 2021年7月，因个人原因及各种现实因素辞职。

# 4.项目管理辅助系统功能模块设计

该系统目前包含了五大模块，表格打印模块，流程管理模块，仓库管理模块，监控管理，结算管理模块，自动化办公模块，数据采集模块。如果不能显示图片，需要一定的上网技巧哟。
## 4.1软件界面
![表格打印模块](https://github.com/FrankZhou-jun/projectManagerAidedSystem/raw/main/images/表格打印模块.jpg)
![流程管理模块](https://github.com/FrankZhou-jun/projectManagerAidedSystem/raw/main/images/流程管理模块.png)
![仓库管理模块](https://github.com/FrankZhou-jun/projectManagerAidedSystem/raw/main/images/仓库管理模块.jpg)
![结算管理模块](https://github.com/FrankZhou-jun/projectManagerAidedSystem/raw/main/images/结算管理模块.jpg)
![数据采集模块](https://github.com/FrankZhou-jun/projectManagerAidedSystem/raw/main/images/数据采集模块.jpg)


# 5.安装使用说明

# 5.1参考文献
<div id="refer-anchor-1"></div>

- [1] 冯尧. 仓储管理系统设计与实现[D].

# 6.致谢

