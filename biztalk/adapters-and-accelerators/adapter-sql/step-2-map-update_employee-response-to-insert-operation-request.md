---
title: 步骤 2： 映射要插入操作的请求消息的 UPDATE_EMPLOYEE 响应消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d12014a-0147-4227-88fa-0b290eff4cce
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29a7cef00860f32aa2a493cc401e5d49d223ad3a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224821"
---
# <a name="step-2-map-the-updateemployee-response-message-to-insert-operation-request-message"></a>步骤 2： 映射要插入操作的请求消息的 UPDATE_EMPLOYEE 响应消息
![步骤 2 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **完成时间：** 10 分钟  
  
 **目标：** 在此步骤中，创建要在执行插入操作的请求消息**Purchase_Order**表，然后将映射的响应消息**UPDATE_EMPLOYEE**存储插入操作的请求消息的过程。 通过这样做，你要插入的响应消息中的值将传递**Purchase_Order**表。  
  
## <a name="prerequisites"></a>先决条件  
 你必须已完成[步骤 1： 为 Purchase_Order 表的插入操作创建请求消息](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md)。  
  
### <a name="to-map-the-messages"></a>若要将消息映射  
  
1.  与现有的业务流程，在**插入**块**确定**形状下, **ReceiveUpdateResponse**形状，添加**消息分配**形状。 从工具箱中，拖动**消息分配**到空间形状指示。  
  
    > [!NOTE]
    >  当删除**消息分配**形状拖到设计图面，业务流程设计器创建封闭**构造消息**为你的形状。  
  
2.  在设计图面上，右键单击**ConstructMessage_1**形状，并依次**属性窗口**。  
  
3.  在**属性**窗格**ConstructMessage_1**形状，指定以下值。  
  
    |将此属性设置|为此值|  
    |-----------------------|-------------------|  
    |**构造的消息**|InsertPO|  
    |**名称**|ConstructInsertMessage|  
  
4.  双击**MessageAssignment**形状以打开**BizTalk 表达式编辑器**。  
  
5.  在**BizTalk 表达式编辑器**，添加以下：  
  
    ```  
    InsertPO = UpdatePOMessageCreator.UpdatePOMessageCreator.XMLMessageCreator();  
    InsertPO(WCF.Action) = "TableOp/Insert/dbo/Purchase_Order";  
    ```  
  
     在这里， **InsertPO**是你在中创建一条消息[步骤 2： 创建 BizTalk 业务流程的消息](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)发送的插入操作的请求消息**Purchase_Order**表。 在**MessageAssignment**调用形状， **UpdatePOMessageCreator**类以创建的请求消息。 此外，你将设置请求消息的 WCF 操作。  
  
6.  在**构造消息**形状和后**消息分配**形状，添加**转换**形状。  
  
7.  在**转换配置**对话框中，从左窗格中，在**转换**标签，请单击**源**。  
  
8.  从**源转换**在右侧框中，单击下的空间**变量名称**，然后选择**UpdateEmployeeResponse**。  
  
     ![选取源架构的映射](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-source-map.gif "sql_adap_tut_05_source_map")  
  
9. 在**转换配置**对话框中，从左窗格中，在**转换**标签，请单击**目标**。  
  
10. 从**目标转换**在右侧框中，单击下的空间**变量名称**，然后选择**InsertPO**。  
  
     ![选取映射目标架构](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-dest-map.gif "sql_adap_tut_05_dest_map")  
  
11. 单击 **“确定”**。 打开该映射文件。  
  
12. 展开源和目标架构中的节点。  
  
13. 映射 Employee_ID 并重命名这两个架构中的字段。  
  
    -   映射**Employee_ID**源架构 (UPDATE_EMPLOYEEResponse) 中的节点**Employee_ID**目标架构 (Insert) 中的节点。  
  
    -   映射**名称**到源架构中的节点**Employee_Name**目标架构中。  
  
     下图显示的映射的架构。  
  
     ![映射源和目标架构](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-07-dest-map.gif "sql_adap_tut_07_dest_map")  
  
     保存并关闭该映射。  
  
14. 下图显示正在进行中业务流程。  
  
     ![与转换形状的协调](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-08-map-orch.gif "sql_adap_tut_08_map_orch")  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 在此步骤中，创建要插入记录合并到的消息**Purchase_Order**表，并随后将映射从响应消息**UPDATE_EMPLOYEE**存储为插入的请求消息的过程操作。  
  
## <a name="next-steps"></a>后续步骤  
 发送请求消息上执行插入操作**Purchase_Order**表和中所述接收响应，[步骤 3： 将请求消息发送到插入的记录和接收响应](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 1： 为 Purchase_Order 表上插入操作创建的请求消息](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md)   
 [第 4 课： 执行插入操作上采购订单表](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)