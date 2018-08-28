---
title: 如何搜索跟踪的消息事件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18df4cf7-c307-4175-926c-9be9f30b29ed
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a49ae9793c38746d965c75dc9da902cfe6b6da3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989286"
---
# <a name="how-to-search-for-tracked-message-events"></a>跟踪的消息事件
可以使用**新查询**选项卡中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来搜索跟踪消息事件。  在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，您可以启用消息正文和消息属性跟踪。 在“查询结果”窗格中，您可以查看有关消息事件的信息（包括架构信息、事件类型、服务实例 ID，以及生成消息的所有升级属性）。  

> [!NOTE]
>  若要查看实际消息正文，可以调用**消息的详细信息**上下文菜单，然后转到"消息部分"选项卡，或保存该消息从结果列表中查看通过调用**将保存到文件**从上下文菜单。  

## <a name="prerequisites"></a>必要條件  
 若要执行此过程，必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators 组成员的身份登录。  

### <a name="to-search-for-tracked-message-items"></a>搜索跟踪的消息项  

1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。  

2. 在控制台树中，展开**BizTalk Server 管理**，然后单击 BizTalk 组。  

3. 在详细信息窗格中，单击**新查询**选项卡。  

4. 在中**查询表达式**组中，在**值**列中，选择**跟踪的消息事件**从下拉列表框。  

5. 在中**字段名**列，星号旁边的空下拉列表框中 (* *\\* * *)，选择一个或多项操作：  


   |                        项                         |                                              Description                                               |
   |-----------------------------------------------------|--------------------------------------------------------------------------------------------------------|
   |                  **创建时间**                  |                                   创建消息的时间。                                    |
   |                   **事件类型**                    |                                    被跟踪的事件的类型。                                    |
   |                 **最大匹配数**                 |                                   要显示的匹配数。                                    |
   |                      **参与方**                      |                                发送消息的组织。                                 |
   |                      **端口**                       |                                 用于处理消息的端口。                                  |
   |                   **架构名称**                   |                                消息所用的架构的名称。                                 |
   |               **服务实例 ID**               |                             用于消息的服务实例 ID。                              |
   |                       **URI**                       |                                     用于消息的 URI。                                      |
   | **\<选择跟踪的属性的架构名称\>** | 当选择架构时，该架构中的任何升级属性都有资格用在查询中。 |


6. 完成**值**根据需要将所选内容中所做的列**字段名**列。  

7. 继续将其他行添加到作为相应的查询，通过完成**字段名**，**运算符**，并**值**列，并单击**运行查询**。  

## <a name="see-also"></a>请参阅  
 [使用管理控制台的“查询”选项卡](../core/using-the-administration-console-query-tab.md)