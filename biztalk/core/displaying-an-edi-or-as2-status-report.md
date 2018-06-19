---
title: 显示的 EDI 或 AS2 状态报告 |Microsoft 文档
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
ms.openlocfilehash: 0564a5c5d904a217ac406befebd3d7c742dc00c1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22242333"
---
# <a name="displaying-an-edi-or-as2-status-report"></a>显示 EDI 或 AS2 状态报告
EDI 和 AS2 状态报告启用后，您可访问以下状态报告：  
  
|报告类型|级别更高的状态报告|级别更低的状态报告|  
|--------------------|---------------------------------|--------------------------------|  
|EDI|EDI 交换和相关 ACK 状态|-交换状态和 ACK 详细信息<br /><br /> 事务集详细信息<br /><br /> EDI 消息内容|  
|EDI|批状态|-|  
|EDI|交换聚合报表|-|  
|EDI|事务集聚合报告|-|  
|AS2|AS2 消息和相关 MDN 状态|AS2 消息内容|  
  
## <a name="prerequisites"></a>先决条件  
 以下为执行本主题中的过程的前提条件：  
  
-   必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录，才能自定义任何状态报告。  
  
-   如果以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 操作员组成员的身份登录，可以显示只读状态报告。  
  
## <a name="display-an-edi-or-as2-status-report"></a>显示 EDI 或 AS2 状态报表  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**BizTalk 组**节点。  
  
2.  在**组中心数据库**选项卡**组概述**页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，移动到页面底部。  
  
3.  若要显示**EDI 交换和关联 ACK 状态**报告，则会继续，如下所示：  
  
    1.  单击**EDI 交换和关联 ACK 状态**中**EDI 状态报告**区域**组中心数据库**选项卡。  
  
    2.  若要显示将交换和其关联的确认的详细信息，请右键单击的查询结果中某个条目**EDI 交换和关联的 ACK 状态**报告，并依次**交换状态和 ack详细信息**。  
  
    3.  若要显示的事务集的详细信息，请关闭交换状态和 ack 的详细信息报表，将返回到**EDI 交换和关联 ACK 状态**的详细信息报表。 右键单击在查询结果中，某个条目，然后单击**设置事务的详细信息**。  
  
    4.  若要显示的标头和负载的事务集详细信息，请右键单击中的条目**设置事务的详细信息**报告，并依次**查看事务设置内容**。  
  
    5.  若要显示有关该交换包含事务集数据，右键单击中的条目**设置事务的详细信息**报告，并依次**交换/ACK 状态**。 包含事务集的交换会在“交换/ACK 状态”报告中突出显示。  
  
4.  若要显示**批处理状态**报告，则会继续，如下所示：  
  
    1.  单击**批处理状态**中**EDI 状态报告**区域**组中心数据库**选项卡。  
  
    2.  若要显示与中的批处理项关联的已完成的批**批处理状态**报告，右键单击该条目，然后单击**完成批**。  
  
    3.  若要显示有关已完成的批处理的交换的数据，右键单击在交换**完成批处理**报告，并依次**交换/ACK 状态**。 批处理交换的条目会在“交换/ACK 状态”报告中突出显示。  
  
5.  若要显示**交换聚合报表**，继续，如下所示：  
  
    -   单击**交换聚合报表**中**EDI 状态报告**区域**组中心数据库**选项卡。  
  
6.  若要显示**事务组聚合报表**，继续，如下所示：  
  
    -   单击**事务组聚合报表**中**EDI 状态报告**区域**组中心数据库**选项卡。  
  
7.  若要显示**AS2 消息和相关 MDN 状态**报告，则会继续，如下所示：  
  
    1.  单击**AS2 消息和相关 MDN 状态**中**EDIINT 状态报告**区域**组中心数据库**选项卡。  
  
    2.  若要显示的状态的 EDI 交换 AS2 消息中，右键单击中的条目**AS2 消息和相关 MDN 状态**报告，并依次**交换/ACK 状态**。  
  
        > [!NOTE]
        >  有关如何关联起来 EDI 状态和 AS2 状态的详细信息，请参阅的"关联 AS2 消息与及其 EDI 负载"部分的[AS2 消息和相关 MDN 状态报表](../core/as2-message-and-correlated-mdn-status-report.md)。  
  
    3.  要显示 AS2 消息中的连网格式，请右键单击 AS2/MDN 状态报表中中的条目，然后单击**消息连网格式**。  
  
    4.  要显示格式为已解码 AS2 消息，请右键单击 AS2/MDN 状态报表中中的条目，然后单击**消息已解码格式**。  
  
    5.  要显示 MDN 消息，请右键单击 AS2/MDN 状态报表中中的条目，然后单击**Mdn 消息**。  
  
## <a name="see-also"></a>另请参阅  
 [监视 EDI 和 AS2 解决方案](../core/monitoring-edi-and-as2-solutions.md)   
 [EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)   
 [启用 EDI 和 AS2 状态报表](../core/enabling-edi-and-as2-status-reports.md)   
 [配置 EDI 和 AS2 状态报表](../core/configuring-an-edi-and-as2-status-report.md)