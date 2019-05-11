---
title: 第 1 步：添加业务流程形状以接收通知 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4e4c6fa5-81b7-4928-84d5-39533535f862
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 981ab324745840a4ba15e7d552af3f9ff965e3fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367798"
---
# <a name="step-1-add-orchestration-shapes-to-receive-notification"></a>第 1 步：添加业务流程形状以接收通知
![3 的第 1 步](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **若要完成的时间：** 5 分钟  
  
 **目标：** 在此步骤中，添加业务流程形状可以接收的更改通知**员工**表。  
  
## <a name="prerequisites"></a>先决条件  
 你必须完成中的步骤[第 1 课：生成架构并创建消息](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)。  
  
### <a name="to-receive-notification-messages"></a>若要接收通知消息  
  
1.  打开 BizTalk 业务流程， **EmployeeOrch.odx**，你在中添加[步骤 2:为 BizTalk 业务流程创建消息](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)。  
  
2.  添加**接收**向业务流程的形状。 从业务流程工具箱中拖动**接收**形状变为业务流程设计图面上，并将其放入之间指示空间**开始**（绿色圆形） 和**最终**（红色八边形） 形状。  
  
    |将此属性设置|为此值|  
    |-----------------------|-------------------|  
    |**Activate**|True|  
    |**Message**|NotifyReceive|  
    |**名称**|ReceiveNotification|  
  
3.  添加一个单向接收端口与业务流程。 此端口将用于从 SQL Server 数据库中接收通知消息。 设置端口的以下属性。  
  
    |将此属性设置|为此值|  
    |-----------------------|-------------------|  
    |**通信方向**|Receive|  
    |**通信模式**|单向|  
    |**Identifier**|ReceiveNotification|  
  
     此外，更改操作名称从为 Operation_1**通知**。  
  
4.  连接**ReceiveNotification**到端口**ReceiveNotification**操作形状。 在业务流程设计器中，在设计图面上，将的操作形状的端口到相应的绿色句柄的绿色箭头状手柄。  
  
    > [!NOTE]
    >  在此步骤中，使用拖放方法将端口连接到操作形状。 您可以改用操作形状的操作属性来操作形状连接到端口。  
  
5.  下图显示了正在进行中业务流程。  
  
     ![接收通知消息的业务流程](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-01-receive-notification-orch.gif "sql_adap_tut_01_receive_notification_orch")  
  
## <a name="what-did-i-just-do"></a>我只需做了什么？  
 在此步骤中，添加业务流程形状和接收端口以从 SQL Server 数据库中接收通知。  
  
## <a name="next-steps"></a>后续步骤  
 将表达式形状添加到业务流程，以提取 SQL Server 数据库中，从收到的通知的类型，如中所述[步骤 2:从通知消息中提取通知类型](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)。  
  
## <a name="see-also"></a>请参阅  
 [步骤 2：从通知消息中提取通知类型](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)   
 [第 2 课：接收和筛选通知](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)