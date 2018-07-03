---
title: 显示 EDI 或 AS2 状态报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60968c3d-6329-411f-9f10-1dd4a6cc9d79
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a729e089c3d833d7bf8d8b87ebabeec0743b358a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018631"
---
# <a name="displaying-an-edi-or-as2-status-report"></a>显示 EDI 或 AS2 状态报告
EDI 和 AS2 状态报告启用后，您可访问以下状态报告：  
  
|报告类型|级别更高的状态报告|级别更低的状态报告|  
|--------------------|---------------------------------|--------------------------------|  
|EDI|EDI 交换和相关 ACK 状态|-交换状态和确认详细信息<br /><br /> --事务集详细信息<br /><br /> EDI 消息内容|  
|EDI|批状态|-|  
|EDI|交换聚合报告|-|  
|EDI|事务集聚合报告|-|  
|AS2|AS2 消息和相关 MDN 状态|AS2 消息内容|  
  
## <a name="prerequisites"></a>必要條件  
 以下为执行本主题中的过程的前提条件：  
  
- 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录，才能自定义任何状态报告。  
  
- 如果以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 操作员组成员的身份登录，可以显示只读状态报告。  
  
## <a name="display-an-edi-or-as2-status-report"></a>显示 EDI 或 AS2 状态报告  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**BizTalk 组**节点。  
  
2. 在中**组中心**选项卡**组概述**页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，转到页面底部。  
  
3. 若要显示**EDI 交换和相关 ACK 状态**报告，则会继续，如下所示：  
  
   1.  单击**EDI 交换和相关 ACK 状态**中**EDI 状态报告**区域**组中心**选项卡。  
  
   2.  若要显示交换及其相关的确认的详细信息，请右键单击查询结果中的条目**EDI 交换和相关 ACK 状态**报告，然后依次**交换状态和确认详细信息**。  
  
   3.  若要显示事务集的详细信息，请关闭交换状态和确认详细信息报告，返回到**EDI 交换和相关 ACK 状态**的详细信息报表。 右键单击查询结果中的条目，然后单击**事务集详细信息**。  
  
   4.  若要显示有关的标头和负载的事务集的详细信息，请右键单击中的条目**事务集详细信息**报告，然后依次**查看事务集内容**。  
  
   5.  若要显示包含事务集的交换有关的数据，请右键单击中的条目**事务集详细信息**报告，然后依次**交换 /ACK 状态**。 包含事务集的交换会在“交换/ACK 状态”报告中突出显示。  
  
4. 若要显示**批状态**报告，则会继续，如下所示：  
  
   1.  单击**批状态**中**EDI 状态报告**区域**组中心**选项卡。  
  
   2.  若要显示与中的批处理条目相关联的已完成的批处理**批状态**报告，右键单击该条目，然后单击**完成批处理**。  
  
   3.  若要显示有关已完成的批处理交换的数据，请右键单击中的交换**已完成的批处理**报告，然后依次**交换 /ACK 状态**。 批处理交换的条目会在“交换/ACK 状态”报告中突出显示。  
  
5. 若要显示**交换聚合报告**，继续操作，如下所示：  
  
   -   单击**交换聚合报告**中**EDI 状态报告**区域**组中心**选项卡。  
  
6. 若要显示**事务集聚合报告**，继续操作，如下所示：  
  
   -   单击**事务集聚合报告**中**EDI 状态报告**区域**组中心**选项卡。  
  
7. 若要显示**AS2 消息和相关 MDN 状态**报告，则会继续，如下所示：  
  
   1.  单击**AS2 消息和相关 MDN 状态**中**EDIINT 状态报告**区域**组中心**选项卡。  
  
   2.  若要显示 AS2 消息中的 EDI 交换的状态，请右键单击中的条目**AS2 消息和相关 MDN 状态**报告，然后依次**交换 /ACK 状态**。  
  
       > [!NOTE]
       >  有关如何关联起来 EDI 及 AS2 的状态的详细信息，请参阅的"关联 AS2 消息与其 EDI 负载"部分[AS2 消息和相关 MDN 状态报告](../core/as2-message-and-correlated-mdn-status-report.md)。  
  
   3.  要以传输格式显示 AS2 消息，请右键单击 AS2/MDN 状态报告中中的条目，然后单击**消息传输格式**。  
  
   4.  若要显示 AS2 消息解码格式中，右键单击 AS2/MDN 状态报告中中的条目，然后单击**消息解码格式**。  
  
   5.  要显示 MDN 消息，请右键单击 AS2/MDN 状态报告中中的条目，然后单击**Mdn 消息**。  
  
## <a name="see-also"></a>请参阅  
 [监视 EDI 和 AS2 解决方案](../core/monitoring-edi-and-as2-solutions.md)   
 [EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)   
 [启用 EDI 和 AS2 状态报告](../core/enabling-edi-and-as2-status-reports.md)   
 [配置 EDI 和 AS2 状态报告](../core/configuring-an-edi-and-as2-status-report.md)