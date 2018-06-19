---
title: 为批处理状态报表存储的数据 |Microsoft 文档
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
ms.openlocfilehash: db9831aafce56845fe7b75e91f5369a8860d8996
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238589"
---
# <a name="data-stored-for-batching-status-reports"></a>为批处理状态报告存储的数据
当**打开 ON Reporting**为一个协议，选中属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将存储每个批处理的实例的状态。 此属性是在位于**常规属性**页**常规**选项卡中**协议属性**对话框。 状态可以为以下任意状态：  
  
-   **定义**： 批处理实例配置。 批的激活起始日期时间晚于当前日期时间。 所有批参数均已定义，但批没有运行（没有接受文档）。  
  
-   **Active**： 批处理实例已激活和聚合事务集。 可以查看已接受/已拒绝事务集的数量。  
  
-   **发布**： 批处理满足释放条件和发布到 MessageBox，但尚未释放通过发送管道中，或在处理任何消息之前停止批处理。  
  
-   **完成**: EdiSend 管道发送批处理。  
  
 如果 EdiSend 管道已经发送了批，可以将 UI 中的批记录与所发送 Edi 交换的记录关联在一起，并查看事务集详细信息。  
  
> [!NOTE]
>  批配置可以有多个状态为“已完成”的批实例。  
  
 **关联的批处理的交换**  
  
 通过 BusinessMessageJournal BAM 活动，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以将收到的包含事务集的 EDI 交换与包含相同事务集的传出批交换相关联。 有关如何实现和使用此相关信息的信息，请参阅[关联传出批的传入事务集](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md)。  
  
## <a name="see-also"></a>另请参阅  
 [对于 EDI 和 AS2 状态报表存储的数据](../core/data-stored-for-edi-and-as2-status-reports.md)   
 [对于 EDI 状态报表存储的数据](../core/data-stored-for-edi-status-reports.md)   
 [AS2 状态报告为存储的数据](../core/data-stored-for-as2-status-reports.md)