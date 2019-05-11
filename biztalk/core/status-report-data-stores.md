---
title: 状态报告数据存储 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6cd40ce8-1ac6-43b4-9cef-7cd045e8893c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0cb1d8d2a85cc88364da5bb43131213903b37d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392879"
---
# <a name="status-report-data-stores"></a>状态报告数据存储区
状态报告跟踪数据存储在 BAM 主导入数据库。 在此数据库中的表数用于 EDI 和 AS2 消息数据，包括开头 dbo.bam_AS2、 dbo.bam.batching、 这些表和其他人的表。 状态数据存储在主导入数据库，即使禁用 EDI 报告。 您将只能查看和查询这些数据在状态报告 UI，激活状态报告。  
  
 如果出于不可否认，启用消息数据的存储[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将 EDI 和/或 AS2 数据存储在 BizTalk 跟踪数据库 (BizTalkDTADb) 的 EDI Message Content 表中。 如果启用消息内容存储以查看负载的详细信息 (通过选择**存储消息负载以用于报告**协议属性中的**常规属性**页**常规**选项卡中**协议属性**对话框中)，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]还会在此表中存储的事务集。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 存档和清除数据从 BAM 主导入和 BizTalkDTADb 数据库。 数据库中的表将定期清除。  
  
> [!NOTE]
>  BAM 主导入和 DTA DB 数据库可能是同步如果每个都有不同的时间间隔进行存档。  
  
 EDI 和 AS2 状态报告可能会对性能影响。 详细信息，请参阅"性能注意事项为 EDI 和 AS2 状态报告"中[EDI 和 AS2 性能的已知问题](../core/known-issues-with-edi-and-as2-performance.md)。  
  
## <a name="see-also"></a>请参阅  
 [如何为 EDI 和 AS2 状态报告存储数据](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)