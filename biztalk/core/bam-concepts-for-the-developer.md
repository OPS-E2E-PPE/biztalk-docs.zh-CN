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
ms.openlocfilehash: 9fc6d74eb8b14479776febea1530e142e6897729
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967446"
---
# <a name="bam-concepts-for-the-developer"></a>适用于开发人员的 BAM 概念
作为 BAM 开发人员，您需要熟悉重要的 BAM 概念，如活动、继续符和引用， 还应该了解跟踪和事务性处理之间的区别。  
  
## <a name="what-is-a-bam-activity"></a>什么是 BAM 活动？  
 BAM 活动定义了哪些数据对于业务流程中的项是目标数据（如单个 PO）。 它定义了 BAM 数据库中包括的列。  
  
 活动实例代表业务中的工作单位，例如采购订单或贷款申请。 活动指定了里程碑（活动的历史记录）列表和目标数据。 活动实例表现为 BAM 主导入数据库中的单个行。 对于活动实例的任何数据项，有一个且只有一个值。  
  
 活动用于向业务最终用户或信息工作者显示有关此工作单位的里程碑和数据。 例如，在 BAM SDK 示例中定义的活动包含诸如“已支付”和“发送”这样的里程碑以及诸如“总额”这样的目标数据。  
  
 BAM 活动常常直接映射到业务流程，尽管作为高级抽象概念，活动独立于 IT 基础结构的实际实现。  
  
 开发人员可以只在特定活动的上下文公开实现的相关里程碑和数据，以此来维护这种抽象概念。  
  
## <a name="what-is-a-continuation"></a>什么是继续符？  
 继续符为 BAM 基础结构提供有关以下信息的指导：  
  
- 事件应按何种顺序发生  
  
- 对与事件项关联的唯一 ID 中的任何更改进行处理的方法  
  
  有关继续符及其使用方式的详细信息，请参阅[Continuation 和 ContinuationID 节点](../core/continuation-and-continuationid-nodes.md)。  
  
## <a name="what-is-a-reference"></a>什么是引用？  
 引用（也称为相关活动）指定了活动和其他某个项之间的关系。 可能相关的项的示例为另一个活动或文档位置。  
  
> [!NOTE]
>  将活动指定为相关活动时，与继续符活动不同的是，如果相关活动尚未完成，不妨碍完成当前活动。  
  
## <a name="tracking-and-transactional-processing"></a>跟踪和事务性处理  
 通过编写 BAM 代码，您可以控制跟踪数据的方式，也就是说，通过跟踪还是事务性处理。 默认情况下，BAM 为跟踪和处理分配同等的重要性。 这意味着，如果跟踪功能或事务性处理失败，都不能继续进行。 在跟踪数据库中不记录任何数据，同时事务回滚。 对于您的解决方案而言，这可能不是首选的跟踪方法。 通过用于 BAM 的开发，您可以确定跟踪还是事务性处理这二者哪个优先。  
  
 下表对 BAM 中跟踪数据的模式进行了说明。  
  
|应用场景|“说明”|  
|--------------|------------------|  
|跟踪优于处理|如果流程成功，则写入跟踪信息。<br /><br /> 如果流程失败，则写入关于故障的信息。|  
|处理等于跟踪|如果跟踪或处理失败，则回滚所有内容。|  
|处理优于跟踪|如果流程成功而跟踪功能失败，则继续处理。|