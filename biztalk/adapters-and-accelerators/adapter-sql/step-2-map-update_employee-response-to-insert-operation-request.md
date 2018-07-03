---
title: 步骤 2： 将 UPDATE_EMPLOYEE 响应消息插入操作请求消息映射 |Microsoft Docs
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
ms.openlocfilehash: 1d158e0f7eed50a40d2696712bacee65a8de946a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009014"
---
# <a name="step-2-map-the-updateemployee-response-message-to-insert-operation-request-message"></a>步骤 2： 将 UPDATE_EMPLOYEE 响应消息插入操作请求消息映射
![步骤 2，共 4 步](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  

 **完成时间：** 10 分钟  

 **目标：** 在此步骤中，创建要在执行插入操作的请求消息**Purchase_Order**表，然后将映射的响应消息**UPDATE_EMPLOYEE**存储为插入操作的请求消息的过程。 这样做之后，您传递响应消息中要插入的值**Purchase_Order**表。  

## <a name="prerequisites"></a>必要條件  
 你必须已完成[步骤 1： 在 Purchase_Order 表的插入操作的创建请求消息](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md)。  

### <a name="to-map-the-messages"></a>若要将消息映射  

1. 向现有业务流程中**插入**块**判定**形状，在**ReceiveUpdateResponse**形状中，添加**消息赋值**形状。 从工具箱拖动**消息赋值**到空间形状表示。  

   > [!NOTE]
   >  放置**消息赋值**形状拖到设计图面上，业务流程设计器创建封闭**构造消息**为你的形状。  

2. 在设计图面上，右键单击**ConstructMessage_1**形状，然后依次**属性窗口**。  

3. 在中**属性**窗格**ConstructMessage_1**形状中，指定以下值。  


   |    将此属性设置     |     为此值      |
   |--------------------------|------------------------|
   | **构造的消息** |        InsertPO        |
   |         **名称**         | ConstructInsertMessage |


4. 双击**MessageAssignment**形状以打开**BizTalk 表达式编辑器**。  

5. 在中**BizTalk 表达式编辑器**，添加以下：  

   ```  
   InsertPO = UpdatePOMessageCreator.UpdatePOMessageCreator.XMLMessageCreator();  
   InsertPO(WCF.Action) = "TableOp/Insert/dbo/Purchase_Order";  
   ```  

    在这里， **InsertPO**是你在中创建的消息[步骤 2： 创建 BizTalk 业务流程的消息](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)用于插入操作的请求消息发送**Purchase_Order**表。 在中**MessageAssignment**形状中，调用**UpdatePOMessageCreator**类，以创建请求消息。 此外，您设置请求消息的 WCF 操作。  

6. 内**构造消息**形状及**消息赋值**形状中，添加**转换**形状。  

7. 在中**转换配置**对话框中，从左窗格中，在**转换**标记中，单击**源**。  

8. 从**源转换**在右侧框中，单击下的空间**变量的名称**，然后选择**UpdateEmployeeResponse**。  

    ![选择用于映射的源架构](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-source-map.gif "sql_adap_tut_05_source_map")  

9. 在中**转换配置**对话框中，从左窗格中，在**转换**标记中，单击**目标**。  

10. 从**目标转换**在右侧框中，单击下的空间**变量的名称**，然后选择**InsertPO**。  

     ![选择用于映射的目标架构](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-dest-map.gif "sql_adap_tut_05_dest_map")  

11. 单击“确定” 。 打开该映射文件。  

12. 展开的源和目标架构中的节点。  

13. 映射 Employee_ID 并命名为这两个架构中的字段。  

    - 地图**Employee_ID**源架构 (UPDATE_EMPLOYEEResponse) 中的节点**Employee_ID**目标架构 (Insert) 中的节点。  

    - 地图**名称**到源架构中的节点**Employee_Name**目标架构中。  

      下图显示了映射的架构。  

      ![映射源和目标架构](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-07-dest-map.gif "sql_adap_tut_07_dest_map")  

      保存并关闭该映射。  

14. 下图显示了正在进行中业务流程。  

     ![具有转换形状的业务流程](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-08-map-orch.gif "sql_adap_tut_08_map_orch")  

## <a name="what-did-i-just-do"></a>内容回顾  
 在此步骤中，创建要插入到的记录的消息**Purchase_Order**表并已进行映射的响应消息**UPDATE_EMPLOYEE**为插入存储过程的请求消息操作。  

## <a name="next-steps"></a>后续步骤  
 发送请求消息上执行插入操作**Purchase_Order**表并接收响应，如中所述[步骤 3： 将请求消息发送到插入记录和接收响应](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)。  

## <a name="see-also"></a>请参阅  
 [步骤 1： 在 Purchase_Order 表的插入操作创建请求消息](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md)   
 [第 4 课：在采购订单表中执行插入操作](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)