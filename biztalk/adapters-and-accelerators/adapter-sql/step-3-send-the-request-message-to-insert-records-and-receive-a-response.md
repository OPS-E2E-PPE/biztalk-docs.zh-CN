---
title: 步骤 3：发送要插入记录，并接收响应的请求消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a8a8906-7c7d-437c-9f04-345ad4ac460e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0db2560d1ef8db10e68b67eeb34e6531e03afd6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367686"
---
# <a name="step-3-send-the-request-message-to-insert-records-and-receive-a-response"></a>步骤 3：发送要插入记录，并接收响应的请求消息
![步骤 3，共 4 步](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **若要完成的时间：** 10 分钟。  
  
 **目标：** 在此步骤中，将发送要插入到的记录的请求消息**Purchase_Order**表并接收响应。  
  
## <a name="prerequisites"></a>先决条件  
 你必须已完成[步骤 2:将 UPDATE_EMPLOYEE 响应消息插入操作请求消息映射](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)。  
  
### <a name="to-send-the-request-message-and-receive-a-response"></a>若要发送的请求消息并接收响应  
  
1.  将以下形状添加到在业务流程**构造消息**形状。  
  
    |形状|形状类型|属性|  
    |-----------|----------------|----------------|  
    |SendInsertMessage|Send|-设置**消息**到*InsertPO*<br />-设置**名称**到*SendInsertMessage*|  
    |ReceiveInsertResponse|Receive|-设置**激活**到*False*<br />-设置**消息**到*InsertPOResponse*<br />-设置**名称**到*ReceiveInsertResponse*|  
    |SaveInsertResponse|Send|-设置**消息**到*InsertPOResponse*<br />-设置**名称**到*SaveInsertResponse*|  
  
2.  修改**SQLOutboundPort**中创建[步骤 2:请求消息发送到 SQL Server 并接收响应](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)。  
  
    1.  右键单击业务流程设计器中中的端口，然后单击**新的操作**。 添加新操作，使端口形状更改**Operation_1**。  
  
    2.  单击**Operation_1**并在属性窗口中，将更改到的标识符的值**InsertPO**。  
  
3.  将单向发送端口添加到业务流程。 将使用此端口来发送响应消息的插入操作。 设置端口的以下属性。  
  
    |将此属性设置|为此值|  
    |-----------------------|-------------------|  
    |**通信方向**|Send|  
    |**通信模式**|单向|  
    |**Identifier**|SaveResponsePort|  
  
     此外，更改操作名称从为 Operation_1 **InsertPO**。  
  
4.  将端口连接到操作形状。 在业务流程设计器中，在设计图面上，将的操作形状的端口到相应的绿色句柄的绿色箭头状手柄。  
  
    > [!NOTE]
    >  在此步骤中，使用拖放方法将端口连接到操作形状。 您可以改用操作形状的操作属性来操作形状连接到端口。  
  
     按如下所示连接端口和操作形状：  
  
    -   连接**SendInsertMessage**到操作形状**请求**的处理**InsertPO**操作**SQLOutboundPort**。  
  
    -   连接**ReceiveInsertResponse**到操作形状**响应**的处理**InsertPO**操作**SQLOutboundPort**。  
  
    -   连接**SaveInsertResponse**到操作形状**请求**的处理**SaveResponsePort**。  
  
5.  下图显示了正在进行中业务流程。  
  
     ![完成业务流程](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-09-comp-orch.gif "sql_adap_tut_09_comp_orch")  
  
## <a name="what-did-i-just-do"></a>我只需做了什么？  
 发送请求以便将记录到**Purchase_Order**表并接收响应。  
  
## <a name="next-steps"></a>后续步骤  
 在生成项目，如中所述[步骤 4:生成项目](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md)。  
  
## <a name="see-also"></a>请参阅  
 [步骤 2：将 UPDATE_EMPLOYEE 响应消息插入操作请求消息映射](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)   
 [步骤 4：生成项目](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md)   
 [第 4 课：在采购订单表中执行插入操作](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)