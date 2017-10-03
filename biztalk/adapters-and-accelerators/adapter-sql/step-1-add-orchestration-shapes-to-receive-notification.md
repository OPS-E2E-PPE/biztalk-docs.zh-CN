---
title: "步骤 1： 添加业务流程形状可以接收通知 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e4c6fa5-81b7-4928-84d5-39533535f862
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a33693a09d89acc5d1ad9e4514c7907b789cc75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-add-orchestration-shapes-to-receive-notification"></a>步骤 1： 添加业务流程形状可以接收通知
![步骤 1，共 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **完成时间：** 5 分钟  
  
 **目标：**在此步骤中，添加业务流程形状可以接收的更改通知**员工**表。  
  
## <a name="prerequisites"></a>先决条件  
 你必须已完成中的步骤[第 1 课： 生成架构和创建消息](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)。  
  
### <a name="to-receive-notification-messages"></a>若要接收通知消息  
  
1.  打开 BizTalk 业务流程， **EmployeeOrch.odx**，你在中添加[步骤 2： 创建 BizTalk 业务流程的消息](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)。  
  
2.  添加**接收**形状上的与业务流程。 从工具箱的业务流程，将拖动**接收**形状变为业务流程设计图面，并将其放到指示之间的空间**开始**（绿色圆圈） 和**结束**（红色八边形） 形状。  
  
    |将此属性设置|为此值|  
    |-----------------------|-------------------|  
    |**Activate**|True|  
    |**消息**|NotifyReceive|  
    |**名称**|ReceiveNotification|  
  
3.  添加单向接收端口与业务流程。 将使用此端口以接收通知消息从 SQL Server 数据库。 设置以下属性的端口。  
  
    |将此属性设置|为此值|  
    |-----------------------|-------------------|  
    |**通信方向**|Receive|  
    |**通信模式**|单向|  
    |**Identifier**|ReceiveNotification|  
  
     此外，从到 Operation_1 更改操作名称**通知**。  
  
4.  连接**ReceiveNotification**端口到**ReceiveNotification**操作形状。 业务流程设计器中，在设计图面上拖动绿色箭头调整控点的操作形状的端口到相应的绿色句柄。  
  
    > [!NOTE]
    >  在此步骤中，使用拖放方法将端口连接到操作形状。 您可以改用操作形状的操作属性，将操作形状连接到端口。  
  
5.  下图显示正在进行中业务流程。  
  
     ![业务流程以接收通知消息](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-01-receive-notification-orch.gif "sql_adap_tut_01_receive_notification_orch")  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 在此步骤中，你将添加业务流程形状，并接收端口从 SQL Server 数据库中接收通知。  
  
## <a name="next-steps"></a>后续步骤  
 将表达式形状添加到业务流程中所述提取的一种从 SQL Server 数据库中，接收的通知[步骤 2： 从通知消息中提取通知类型](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 2： 从通知消息中提取通知类型](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)   
 [第 2 课： 接收和筛选器通知](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)