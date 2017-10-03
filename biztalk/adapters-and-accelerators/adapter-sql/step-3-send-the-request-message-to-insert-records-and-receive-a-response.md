---
title: "步骤 3： 发送要插入记录和接收响应的请求消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a8a8906-7c7d-437c-9f04-345ad4ac460e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db97afa0de19e15e5005e5647279365ea6ba023b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-send-the-request-message-to-insert-records-and-receive-a-response"></a>步骤 3： 发送要插入记录和接收响应的请求消息
![步骤 3 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **完成时间：** 10 分钟  
  
 **目标：**在此步骤中，你将发送要插入记录合并到的请求消息**Purchase_Order**表和接收响应。  
  
## <a name="prerequisites"></a>先决条件  
 你必须已完成[步骤 2： 将 UPDATE_EMPLOYEE 响应消息映射到插入操作请求消息](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)。  
  
### <a name="to-send-the-request-message-and-receive-a-response"></a>若要发送的请求消息和接收响应  
  
1.  向下业务流程中添加以下形状**构造消息**形状。  
  
    |形状|形状类型|属性|  
    |-----------|----------------|----------------|  
    |SendInsertMessage|Send|-将设置**消息**到*InsertPO*<br />-将设置**名称**到*SendInsertMessage*|  
    |ReceiveInsertResponse|Receive|-将设置**激活**到*False*<br />-将设置**消息**到*InsertPOResponse*<br />-将设置**名称**到*ReceiveInsertResponse*|  
    |SaveInsertResponse|Send|-将设置**消息**到*InsertPOResponse*<br />-将设置**名称**到*SaveInsertResponse*|  
  
2.  修改**SQLOutboundPort**中创建[步骤 2： 将请求消息发送到 SQL Server 和接收响应](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)。  
  
    1.  右键单击业务流程设计器中的端口，然后单击**新操作**。 若要添加新操作的端口形状更改**Operation_1**。  
  
    2.  单击**Operation_1**并在属性窗口中，将更改到的标识符的值**InsertPO**。  
  
3.  将单向发送端口添加到业务流程。 你将使用此端口发送插入操作的响应消息。 设置以下属性的端口。  
  
    |将此属性设置|为此值|  
    |-----------------------|-------------------|  
    |**通信方向**|Send|  
    |**通信模式**|单向|  
    |**Identifier**|SaveResponsePort|  
  
     此外，从到 Operation_1 更改操作名称**InsertPO**。  
  
4.  端口连接到操作形状。 业务流程设计器中，在设计图面上拖动绿色箭头调整控点的操作形状的端口到相应的绿色句柄。  
  
    > [!NOTE]
    >  在此步骤中，使用拖放方法将端口连接到操作形状。 您可以改用操作形状的操作属性，将操作形状连接到端口。  
  
     连接的端口和操作形状，如下所示：  
  
    -   连接**SendInsertMessage**操作形状上的与**请求**的 handle **InsertPO**操作**SQLOutboundPort**。  
  
    -   连接**ReceiveInsertResponse**操作形状上的与**响应**的 handle **InsertPO**操作**SQLOutboundPort**。  
  
    -   连接**SaveInsertResponse**操作形状上的与**请求**的 handle **SaveResponsePort**。  
  
5.  下图显示正在进行中业务流程。  
  
     ![完成业务流程](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-09-comp-orch.gif "sql_adap_tut_09_comp_orch")  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 发送请求以插入记录合并到**Purchase_Order**表和接收响应。  
  
## <a name="next-steps"></a>后续步骤  
 中所述生成项目时，[步骤 4： 生成项目](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md)。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 2： 映射要插入操作的请求消息的 UPDATE_EMPLOYEE 响应消息](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)   
 [步骤 4： 生成项目](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md)   
 [第 4 课： 执行插入操作上采购订单表](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)