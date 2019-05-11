---
title: 第 2 步：从通知消息中提取通知类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72f3e805-0f5f-42fa-8fe3-78ccbb375f74
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cca1b44daa45f5502957fa783cdf5e4e2ebca1e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367785"
---
# <a name="step-2-extract-notification-type-from-notification-message"></a>第 2 步：从通知消息中提取通知类型
![步骤 2 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **若要完成的时间：** 5 分钟  
  
 **目标：** 在此步骤中，添加表达式形状中提取的 SQL Server 数据库从收到的通知类型。  
  
## <a name="prerequisites"></a>先决条件  
 你必须已完成[步骤 1:添加业务流程形状以接收通知](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)。  
  
### <a name="to-extract-the-notification-type-from-the-notification-message"></a>若要从通知消息中提取通知类型  
  
1.  将变量添加到 BizTalk 业务流程中创建[步骤 1:添加业务流程形状以接收通知](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)。  
  
    1.  从业务流程视图中，右键单击**变量**，然后单击**新变量**。  
  
    2.  右键单击该新变量**Variable_1**，然后单击**属性窗口**。 设置变量的以下属性。  
  
        |将此属性设置|为此值|  
        |-----------------------|-------------------|  
        |**Identifier**|NotificationType|  
        |**类型**|System.String|  
  
2.  添加**表达式**到 BizTalk 业务流程的形状。 从业务流程工具箱中拖动**表达式**形状变为业务流程设计图面上，然后将其放置**接收**形状  
  
     内**表达式**形状，您将添加 xpath 查询来提取从 SQL Server 收到的通知消息的类型。 然后再创建 xpath 查询，让我们看一下通知消息的格式。 典型的通知消息如下所示：  
  
    ```  
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Insert</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
3.  正如您看到的通知类型有关的信息中有可用`<info>`标记，在父级内的`<Notification>`标记。 因此，添加以下 xpath 查询中的**表达式**形状：  
  
    ```  
    NotificationType = xpath(NotifyReceive,"string(/*[local-name()='Notification']/*[local-name()='Info']/text())");  
    ```  
  
     在这里， **NotificationType**是你创建用于存储提取由 xpath 查询的值的变量。 **NotifyReceive**是你在中创建的消息[步骤 2:为 BizTalk 业务流程创建消息](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)以接收通知消息。  
  
4.  下图显示了与正在进行中业务流程**表达式**包含的形状。  
  
     ![将表达式形状添加到业务流程](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-02-add-expression-orch.gif "sql_adap_tut_02_add_expression_orch")  
  
## <a name="what-did-i-just-do"></a>我只需做了什么？  
 在此步骤中，您添加了**表达式**形状以提取 SQL Server 数据库从收到的通知的类型。  
  
## <a name="next-steps"></a>后续步骤  
 如中所述添加判定形状来为插入通知筛选[步骤 3:为插入通知添加筛选器](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md)。  
  
## <a name="see-also"></a>请参阅  
 [步骤 1：添加业务流程形状以接收通知](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)   
 [步骤 3：为插入通知添加筛选器](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md)   
 [第 2 课：接收和筛选通知](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)