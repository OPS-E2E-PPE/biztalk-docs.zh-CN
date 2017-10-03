---
title: "在 BAM 中定义数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], dimensions
- monitoring business activities [BAM], BAM Activity Wizard
- monitoring business activities [BAM], time intervals
- aggregations [BAM], measurements
- monitoring business activities [BAM], views
- monitoring business activities [BAM], aggregations
- Excel add-in [BAM], collecting data
- aggregations [BAM], scheduling
- monitoring business activities [BAM], milestone groups
- aggregations [BAM], real-time data
ms.assetid: 501a1c08-3979-4a99-94d9-0d1b5ec4266b
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6acbc0ea1d80ec129d691d6c54b6eefd626d0e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="defining-data-in-bam"></a>定义 BAM 中的数据库
您可以使用 BAM Excel 外接程序来定义需要 BAM 收集的数据，以及数据共享的方式。 您可以使用 BAM 活动来定义数据，还可以使用 BAM 视图来定义其他用户可看到的数据。  
  
## <a name="activities"></a>活动  
 您可以创建 BAM 活动来定义有关要使用 BAM 监视的业务流程的信息。 BAM 活动表示企业中某个具体的业务流程，例如处理采购订单或发运产品。 每个业务流程具有一组定义的里程碑和业务数据。 例如，采购订单流程可能包含 Approved、Denied 和 Delivered 等里程碑，以及“客户名称”和“产品”等业务数据。  
  
 BAM 活动的目的是向信息工作者展示有关流程的历史记录（里程碑）和数据。 BAM 活动为高级抽象概念，它们与 BizTalk Server 的实际实现无关。 有关 BAM 概念的综述，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的主题“业务活动监视”。  
  
 使用 BAM 活动向导可以定义至少包含一个活动项的 BAM 活动。 您可以对活动中的相关活动项进行分组，以及使用活动项来描述在业务流程中可用的数据类型。  
  
 下表介绍了 BAM 提供的活动项类型。  
  
|项类型|Description|  
|---------------|-----------------|  
|业务里程碑|日期/时间值。 例如，采购订单的批准日期。|  
|业务数据的文本|包含任何字母数字的字符串。 例如，交付到： 城市、 省/市/自治区和邮政编码代码。|  
|业务数据 – Integer|一个整数值。 例如，购买的总量。|  
|业务数据的 Float|一个十进制值。 例如，PO 的美元总金额。|  
  
 例如，在采购订单活动中，您可以创建下表中的活动项。  
  
|活动项|项类型|  
|-------------------|---------------|  
|Product|业务数据 — Text|  
|City|业务数据 — Text|  
|State|业务数据 — Text|  
|Amount|业务数据 — Float|  
|数量|业务数据 — Integer|  
|已同意|业务里程碑|  
|Delivered|业务里程碑|  
|拒绝|业务里程碑|  
|Received|业务里程碑|  
  
 请注意，“金额”为浮点型，因为它可能是小数值。 “数量”为整型，因为在本示例中它通常是整数。 Approved、Delivered、Denied 和 Received 都是采购订单流程中的里程碑。  
  
## <a name="views"></a>视图  
 创建视图可以向用户公开活动的数据。 在创建基于采购订单活动的视图时，可以定义活动项背后的数据。 可以将 BAM 中的视图数据定义为维度、度量值、持续时间、里程碑组和进度维度。  
  
 视图包含一个或多个视图项。 您可以创建以下类型的视图项：  
  
-   持续时间  
  
-   里程碑组  
  
-   Aggregations  
  
### <a name="durations"></a>持续时间  
 持续时间为时间间隔。 持续时间是通过定义时间间隔开始和结束时间的里程碑来描述的。 下表显示了可从前一表中列出的里程碑得到的持续时间。  
  
|Duration|开始里程碑|结束里程碑|  
|--------------|---------------------|-------------------|  
|1|Received|已同意|  
|2|Received|Delivered|  
|3|Received|拒绝|  
|4|已同意|Delivered|  
  
 在本表中，可以看到第一个持续时间（持续时间 1）是从 BizTalk Server 收到采购订单到批准采购订单的时间间隔。  
  
### <a name="milestone-groups"></a>里程碑组  
 您可以创建里程碑组，将一组里程碑看作一个简单实体，例如，流程的开始里程碑和结束里程碑。这可以创建一个里程碑来表示整个流程长度。  
  
### <a name="aggregations"></a>Aggregations  
 使用聚合可以缩短刷新数据库数据的响应时间。 Excel 将聚合定义为预先计算的数据汇总，通过在提问之前准备好答案的方式来提高查询响应时间。 例如，在数据仓库事实表中包含数以万计的行时，检索两种特定产品发货计划的查询可能需要很长时间才能完成，因为必须扫描该事实表才能计算出答案。 然而，如果预先计算了答复此查询的汇总数据，则查询几乎可以即时得到响应。  
  
 下图显示的是预先计算的聚合数据的示例。  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
  
 该图汇总了在两个月内发送到特定地点的各种产品的数量。 通常，Excel 将此数据定义为度量值。 Excel 将用于筛选和分类的数据定义为维度。  
  
 在 BAM 工作簿中，可以定义两种类型的聚合：  
  
-   实时聚合  
  
-   计划的聚合  
  
### <a name="real-time-aggregations"></a>实时聚合  
 使用实时聚合 (RTA) 您可以看到业务流程的当前状态，并能够轻松地确定流程瓶颈。  
  
 BAM 数据显示在透视表中。 您可以将 BAM 透视表定义为 RTA 或计划的聚合。 RTA 可为您提供最新的数据视图，例如，特定 PO 在发货流程中所处的位置。 您可以随时刷新屏幕以更新数据视图。  
  
 在某些情况下，多维聚合的特定切片对时间非常敏感，需要它们实时可用。 例如，您的企业出售的是容易腐烂的产品，因而您希望各个交货阶段的产品数量的聚合实时可用。 同时，您还需要在月底获得其他聚合，如典型客户的年龄，以便进行商业智能分析。  
  
> [!IMPORTANT]
>  不要定义使用同一个 BAM 活动的多个 RTA。 否则，当您存档 BAM 数据时，RTA 数据将不正确。  
  
 有关浏览多维数据的信息，请参阅 Excel 帮助中的透视表主题。  
  
### <a name="scheduled-aggregations"></a>计划的聚合  
 默认情况下，所有 BAM 聚合都是计划聚合。 计划聚合表示特定时间的业务快照，例如，今天上午发货活动的摘要。 请询问数据库管理员何时处理聚合，然后您可以查看历史数据。  
  
### <a name="dimensions-and-measures"></a>维度和度量值  
 使用维度和度量值可以创建数据聚合：  
  
-   维度描述事实。  
  
-   度量值为事实的值。  
  
 例如，事实可以是库存中有“3 辆红色轿车”。 产品的说明:"car"和"红色"是维度。 事实的值“3”为度量值。 如果每辆轿车的价格包括在事实中，则轿车价格是维度，而库存中轿车的平均价格是度量值。 Microsoft SQL Server 联机丛书将度量值描述为“经过聚合和分析的中心值”。 换言之，如果可以计算某个值、对其求平均数，或者通过执行数学函数运算来得到值，则该值为度量值。  
  
 您可以创建以下类型的维度：  
  
-   进度维度  
  
-   数据维度  
  
-   时间维度  
  
-   数值范围维度  
  
## <a name="progress-dimensions"></a>进度维度  
 BAM 引入了新的维度类型： 进度维度。 通过创建进度维度，可以创建与正在进行的活动的进度相关的聚合。  
  
 例如，请考虑一个您将接收 1,000 个采购订单的采购业务流程。 可以在行中使用进度维度来创建下表。  
  
|OrderProgress_Level1|Count|  
|---------------------------|-----------|  
|Received|1000|  
  
 然后，可以打开 Received 流程查看有关活动进度的详细信息，例如：  
  
|||Count|  
|------|------|-----------|  
|Received|Evaluating|300|  
||已同意|500|  
||拒绝|200|  
  
 这表示在您收到的 1000 个采购订单中，500 个已批准，200 个已拒绝，其他 300 个当前正在评估。  
  
 Received、Approved 和 Denied 表示里程碑。 “数量”列中的相应数字显示了已通过这些里程碑的订单数。 Evaluating 是一个阶段，指订单从 Received 里程碑到 Approved 里程碑或从 Received 里程碑到 Denied 里程碑的过程。  
  
 可以将进度维度与任何其他维度一起使用。 例如，如果在行中使用名为“订单进度”的进度维度，在列中使用名为“产品”的数据维度，则将出现以下结果：  
  
|||网球 Racquets|足球|  
|------|------|---------------------|------------------|  
|Received|Evaluating|250|50|  
||已同意|200|300|  
||拒绝|150|50|  
  
 进度维度提供图表根据实时聚合 (RTA) 尤其有用的信息。 使用 RTA 您可以看到业务流程的当前状态，并能够轻松地确定流程瓶颈。  
  
 在购买的里程碑排序进度维度可以是连续： 第一步完成之后才开始下一步。 或者，里程碑可以按关联顺序一前一后地完成。 后续步骤是子步骤，关联步骤是同级步骤。 在采购订单流程中，一接收到采购订单，验证就开始了。 由于 verification 里程碑是与 receive 里程碑同时发生的短暂步骤，因此它是 receive 里程碑的同级。 采购订单只有在收到之后才能进行审批，因此 approved 里程碑是 received 里程碑的子级。  
  
## <a name="data-dimension"></a>数据维度  
 通过定义数据维度，可以将 BAM 活动中某些文本项的值用于行或列。 例如，名为“产品”的数据维度可用于创建下表：  
  
|Product|Count|  
|-------------|-----------|  
|网球拍|100|  
|足球|200|  
  
 此外，您可以在 BAM 视图向导中定义多个数据维度。 例如，可以定义名为“位置”，包括“州”和“城市”两个级别的数据维度，使用该数据维度可创建下表：  
  
|Product|Los Angeles|San Francisco|Seattle|  
|-------------|-----------------|-------------------|-------------|  
|网球拍|50|20|30|  
|足球|130|50|20|  
  
 在此表格中，“产品”维度用作行，“位置”维度用作列。  
  
## <a name="time-dimension"></a>时间维度  
 通过创建时间维度，可以创建有关时间的聚合。 例如，时间维度可用于创建下表：  
  
|Year|Month|Count|  
|----------|-----------|-----------|  
|2003|January|120|  
||February|230|  
||March|350|  
||April|280|  
  
 可以将时间维度与任何其他维度一起使用。 例如，您可以对行使用时间维度，对列使用数据维度，以创建下表：  
  
|Month|网球拍|足球|  
|-----------|---------------------|------------------|  
|January|50|70|  
|February|120|110|  
|March|300|50|  
|April|220|60|  
  
## <a name="numeric-range-dimension"></a>数值范围维度  
 使用数值范围维度，可以创建根据友好名称对数值范围进行分类的聚合。 例如，业务分析员可以定义一个名为“PO 大小”的数值范围维度，它具有以下范围：  
  
 小：表示采购订单在 0-$100 之间  
  
 中：表示采购订单在 $100 到 $1,000 之间  
  
 大：表示采购订单超过 $1,000  
  
> [!NOTE]
>  如果采购订单金额不在定义的范围内（例如采购订单金额小于 0），则 BAM 将自动创建“超出范围”行来容纳超出范围的数据。  
  
|PO 大小|Count|  
|-------------|-----------|  
|小|500|  
|Medium|350|  
|大|225|  
  
> [!NOTE]
>  您不能创建引用同一数据别名的两个数值范围维度。