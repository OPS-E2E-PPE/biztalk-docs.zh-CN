---
title: "如何搜索消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, viewing
- messages, searching
- Query tab [Administration Console], searching
- Query tab [Administration Console], messages
ms.assetid: c751d23f-913a-4325-81da-a36d61c07e8b
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5443cc021bd5f97621f44d295432c99834bdaed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-search-for-messages"></a>如何搜索消息
你可以使用**查询**在 BizTalk Server 管理控制台中搜索特定类的消息的选项卡。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，则必须以 BizTalk Server Operators 组成员的身份登录。  
  
### <a name="to-search-for-messages"></a>要搜索的消息  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”，然后单击“BizTalk 组”。  
  
3.  在详细信息窗格中，单击**新查询**选项卡。  
  
4.  在**查询表达式**组中，在**值**列中，选择**消息**从下拉列表框。  
  
5.  在**字段名称**旁边星号的空下拉列表框中的列，(**\***)，选择一个或多个以下：  
  
    |项|Description|  
    |----------|-----------------|  
    |**创建时间**|找到指定日期之前或之后创建的消息。|  
    |**错误适配器**|可以对其进行分组或筛选由适配器类型的消息： 文件、 FTP、 HTTP、 MQSeries、 MSMQ、 POP3、 SMTP、 SOAP、 或 Windows SharePoint Services。|  
    |**错误代码**|可以对其进行分组或错误代码筛选消息。|  
    |**错误说明**|可以对其进行分组或筛选由错误说明的消息。|  
    |**Host Name**|可以按主机名称对消息进行分组或筛选。|  
    |**实例状态**|引用消息的服务实例的状态。 可以搜索下列所有类型的实例：所有正在运行的实例、所有挂起实例、活动实例、已冻结的实例、准备运行的实例、计划的实例、已挂起但不可恢复的实例或已挂起并可恢复的实例。|  
    |**最大匹配数**|要显示的匹配数。|  
    |**消息 ID**|可以按消息 ID 对消息进行分组或筛选。|  
    |**消息状态**|可以搜索以下状态的消息：已使用、进程内、已挂起、已挂起但不可恢复、已挂起并可恢复、已排队、已排队但等待处理、已排队但计划以后送达、已排队但等待重试。|  
    |**消息类型**|可以按消息类型对消息进行分组或筛选。|  
    |**服务类**|可以搜索以下内容：独立适配器；消息传送；消息传送和独立适配器；MSMQT；业务流程；或路由故障报告。|  
    |**服务实例 ID**|可以按服务实例 ID 对消息进行分组或筛选。|  
    |**服务名称**|可以按服务名对消息进行分组或筛选。|  
    |**服务类型 ID**|可以按服务类型 ID 对消息进行分组或筛选。|  
    |**URI**|可以按 URI 对消息进行分组或筛选。|  
  
6.  完成**值**列的适合于所选内容所做中**字段名称**列。  
  
7.  继续向视情况而定查询添加更多的行，通过完成**字段名称**，**运算符**，和**值**columns 和 then click**运行查询**。  
  
## <a name="see-also"></a>另请参阅  
 [使用管理控制台的查询选项卡](../core/using-the-administration-console-query-tab.md)