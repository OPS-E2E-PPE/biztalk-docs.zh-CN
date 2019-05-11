---
title: 如何搜索消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, viewing
- messages, searching
- Query tab [Administration Console], searching
- Query tab [Administration Console], messages
ms.assetid: c751d23f-913a-4325-81da-a36d61c07e8b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f91fef5667ab5e5cc3426ac5a6ef89a32021cbf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334811"
---
# <a name="how-to-search-for-messages"></a>如何搜索消息
可以使用**查询**要搜索特定类型的消息在 BizTalk Server 管理控制台中的选项卡。  

## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须以 BizTalk Server Operators 组的成员的身份登录。  

### <a name="to-search-for-messages"></a>若要搜索的消息  

1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后单击 BizTalk 组。  

3. 在详细信息窗格中，单击**新查询**选项卡。  

4. 在中**查询表达式**组中，在**值**列中，选择**消息**从下拉列表框。  

5. 在中**字段名**列，星号旁边的空下拉列表框中 (* *\\* * *)，选择一个或多项操作：  


   |          项           |                                                                                                                                                                Description                                                                                                                                                                |
   |-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |    **创建时间**    |                                                                                                                                         查找指定日期之前或之后创建的消息。                                                                                                                                         |
   |    **适配器错误**    |                                                                                                   可以对其进行分组或筛选按适配器类型的消息：文件、 FTP、 HTTP、 MQSeries、 MSMQ、 POP3、 SMTP、 SOAP、 或 Windows SharePoint Services。                                                                                                    |
   |     **错误代码**      |                                                                                                                                              可以对其进行分组或筛选消息按错误代码。                                                                                                                                              |
   |  **错误说明**  |                                                                                                                                          可以对其进行分组或筛选的错误说明的消息。                                                                                                                                           |
   |      **Host Name**      |                                                                                                                                              可以对其进行分组或筛选消息按主机名。                                                                                                                                               |
   |   **实例状态**   | 引用消息的服务实例的状态。 您可以搜索所有以下类型的实例： 所有正在运行的实例、 所有挂起的实例、 活动实例、 已冻结的实例、 准备运行的实例、 计划的实例，但不可恢复的实例已挂起或已挂起并可恢复实例。 |
   |   **最大匹配数**   |                                                                                                                                                     若要显示的匹配项的数目。                                                                                                                                                     |
   |     **消息 ID**      |                                                                                                                                              可以对其进行分组或筛选消息的消息 id。                                                                                                                                              |
   |   **消息状态**    |                                                 您可以搜索的消息的使用过程中，已挂起、 已挂起，但不是可恢复、 挂起和恢复，排队、 已排队但等待处理、 已排队但计划以后送达、 已排队但等待重试。                                                 |
   |    **消息类型**     |                                                                                                                                             可以对其进行分组或筛选按消息类型的消息。                                                                                                                                             |
   |    **服务类**    |                                                                                                    您可以搜索独立适配器;消息传送;消息传送和独立的适配器;MSMQT;业务流程;或路由故障报告。                                                                                                    |
   | **服务实例 ID** |                                                                                                                                         您可以进行分组或筛选由服务的消息实例 id。                                                                                                                                          |
   |    **服务名称**     |                                                                                                                                             可以对其进行分组或筛选消息的服务名称。                                                                                                                                             |
   |   **服务类型 ID**   |                                                                                                                                           您可以进行分组或筛选由服务的消息类型 id。                                                                                                                                            |
   |         **URI**         |                                                                                                                                                 可以对其进行分组或筛选由 URI 的消息。                                                                                                                                                  |


6. 完成**值**根据需要将所选内容中所做的列**字段名**列。  

7. 继续将其他行添加到查询根据需要，通过完成**字段名**，**运算符**，并**值**列，并单击**运行查询**。  

## <a name="see-also"></a>请参阅  
 [使用管理控制台的“查询”选项卡](../core/using-the-administration-console-query-tab.md)