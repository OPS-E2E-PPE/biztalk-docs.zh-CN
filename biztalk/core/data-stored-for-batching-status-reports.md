---
title: 为批处理状态报告存储的数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d55aa0e1-095f-434e-8530-f1a946ad4430
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f42d503177e3b00ce418913e66948eb813575ab1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006854"
---
# <a name="data-stored-for-batching-status-reports"></a>为批处理状态报告存储的数据
当**打开报告**协议，选择属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将存储每个批处理实例的状态。 此属性中提供**常规属性**页**常规**选项卡中**协议属性**对话框。 状态可以为以下任意状态：  
  
- **定义**： 配置了批实例。 批的激活起始日期时间晚于当前日期时间。 所有批参数均已定义，但批没有运行（没有接受文档）。  
  
- **Active**： 批实例已激活并且正在聚合事务集。 可以查看已接受/已拒绝事务集的数量。  
  
- **发布**： 批满足发布条件和发布到 MessageBox 中，但尚未由发送管道发布或处理任何消息前停止了批处理。  
  
- **完成**: 批发送出去 EdiSend 管道。  
  
  如果 EdiSend 管道已经发送了批，可以将 UI 中的批记录与所发送 Edi 交换的记录关联在一起，并查看事务集详细信息。  
  
> [!NOTE]
>  批配置可以有多个状态为“已完成”的批实例。  
  
 **将一批交换相关联**  
  
 通过 BusinessMessageJournal BAM 活动，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以将收到的包含事务集的 EDI 交换与包含相同事务集的传出批交换相关联。 有关如何实现和使用此相关信息的信息，请参阅[关联与传出批的传入事务集](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md)。  
  
## <a name="see-also"></a>请参阅  
 [为 EDI 和 AS2 状态报告存储的数据](../core/data-stored-for-edi-and-as2-status-reports.md)   
 [为 EDI 状态报告存储的数据](../core/data-stored-for-edi-status-reports.md)   
 [为 AS2 状态报告存储的数据](../core/data-stored-for-as2-status-reports.md)