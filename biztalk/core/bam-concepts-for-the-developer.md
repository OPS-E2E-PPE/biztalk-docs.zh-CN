---
title: 开发人员的 BAM 概念 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c26d0aed-821c-4e1f-9cc9-9375a2ba28de
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec027ef80ebaa9f1c8954e09722156a48c843a70
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358607"
---
# <a name="bam-concepts-for-the-developer"></a>开发人员的 BAM 概念
作为 BAM 开发人员，您需要熟悉重要的 BAM 概念，如活动、 继续符和引用。 您还应该了解跟踪和事务性处理之间的差异。  
  
## <a name="what-is-a-bam-activity"></a>什么是 BAM 活动？  
 BAM 活动是哪些数据是业务流程 （如单个 PO) 中的项有趣的定义。 它定义了 BAM 数据库中包括的列。  
  
 活动的实例表示在企业中，例如采购订单或贷款申请的工作单元。 活动指定了里程碑 （活动的历史记录） 和感兴趣的数据的列表。 活动实例表现为 BAM 主导入数据库中的单个行。 没有为该实例的活动的任何数据项的一个且只有一个值。  
  
 活动用于向业务最终用户或信息工作者显示里程碑和有关此工作单位的数据。 例如，BAM SDK 示例中定义的活动以及如"Total Amount"。 所需的数据作为包含"已支付"和"发送"等里程碑  
  
 BAM 活动常常直接映射到业务流程，尽管作为高级抽象活动是独立于你的 IT 基础结构的实际实现。  
  
 您作为开发人员的工作是通过公开的相关里程碑和上下文中的特定活动的实现中的数据来保持这种抽象。  
  
## <a name="what-is-a-continuation"></a>延续是什么？  
 延续任务提供指导到 BAM 基础结构有关的以下信息：  
  
- 事件预期发生的顺序  
  
- 一种方法来处理任何更改的项对与事件相关联的唯一 ID  
  
  有关继续符及其使用方式的详细信息，请参阅[Continuation 和 ContinuationID 节点](../core/continuation-and-continuationid-nodes.md)。  
  
## <a name="what-is-a-reference"></a>什么是引用？  
 （也称为相关活动） 的引用指定一个活动，还有一些其他项之间的关系。 可以与相关的项的示例为另一个活动或文档位置。  
  
> [!NOTE]
>  当活动指定为相关活动时，当前活动是不是，与继续符活动，不同妨碍完成如果相关的活动尚未完成。  
  
## <a name="tracking-and-transactional-processing"></a>跟踪和事务性处理  
 编写 BAM 代码，您可以控制数据的方式被跟踪，即，通过跟踪还是事务性处理。 默认情况下，BAM 为跟踪和处理分配同等的重要性。 这意味着，如果跟踪功能或事务过程失败，既不允许继续执行。 跟踪数据库中记录执行任何操作并回滚事务。 这可能不是跟踪的你的解决方案的首选的方法。 通过用于 BAM 的开发可以确定是否跟踪或事务处理优先。  
  
 下表描述了 BAM 中跟踪数据的模式。  
  
|应用场景|“说明”|  
|--------------|------------------|  
|跟踪优于处理|如果该过程成功，则写入跟踪信息。<br /><br /> 如果该进程将失败，写入与失败有关的信息。|  
|处理等于跟踪|如果跟踪或处理失败，则回滚所有内容。|  
|处理优于跟踪|如果流程成功而跟踪功能失败，继续进行处理。|