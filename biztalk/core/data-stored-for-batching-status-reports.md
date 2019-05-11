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
ms.openlocfilehash: 2c0306ca5a0d8f3d4e9fb688c747bc77ba9eb5c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389795"
---
# <a name="data-stored-for-batching-status-reports"></a>为批处理状态报告存储的数据
当**打开报告**协议，选择属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将存储每个批处理实例的状态。 此属性中提供**常规属性**页**常规**选项卡中**协议属性**对话框。 状态可以是以下任一项：  
  
- **定义**:配置了批实例。 批处理激活开始日期时间晚于当前日期时间。 定义所有批参数，但批没有运行 （没有接受文档）。  
  
- **活动**：批处理实例已激活并且正在聚合事务集。 可以查看已接受/拒绝事务集数目。  
  
- **发布**:批满足发布条件和发布到 MessageBox 中，但尚未由发送管道发布或处理任何前停止了批处理消息。  
  
- **完成**:将批 EdiSend 管道发送。  
  
  如果将批 EdiSend 管道发送，可以将 UI 中记录的发送的 Edi 交换，并查看事务集详细信息的批处理记录相关联。  
  
> [!NOTE]
>  可能有多个状态的批配置的已完成的批实例。  
  
 **将一批交换相关联**  
  
 BusinessMessageJournal BAM 活动，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要将包含事务集与包含在同一个事务的传出批交换将接收的 EDI 交换的关联设置。 有关如何实现和使用此相关信息的信息，请参阅[关联与传出批的传入事务集](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md)。  
  
## <a name="see-also"></a>请参阅  
 [为 EDI 和 AS2 状态报告存储的数据](../core/data-stored-for-edi-and-as2-status-reports.md)   
 [为 EDI 状态报告存储的数据](../core/data-stored-for-edi-status-reports.md)   
 [为 AS2 状态报告存储的数据](../core/data-stored-for-as2-status-reports.md)