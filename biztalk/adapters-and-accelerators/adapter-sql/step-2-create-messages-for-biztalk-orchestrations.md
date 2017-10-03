---
title: "步骤 2： 为 BizTalk 业务流程创建消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 47a4fb98-6085-4aeb-ab39-2f2c3858d4e0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89b121d95992eb30240e38da434d1125df9db681
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-messages-for-biztalk-orchestrations"></a>步骤 2： 为 BizTalk 业务流程创建消息
![步骤 2 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")  
  
 **完成时间：** 5 分钟  
  
 **目标：**在此步骤中，BizTalk 项目中添加业务流程和创建适用于你在中生成各种架构的消息[步骤 1： 为操作生成架构](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)。  
  
## <a name="prerequisites"></a>先决条件  
 你必须已完成[步骤 1： 为操作生成架构](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)。  
  
### <a name="to-create-messages-in-an-orchestration"></a>若要创建业务流程中的消息  
  
1.  将 BizTalk 业务流程添加到中的 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]:  
  
    1.  从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**添加**，然后单击**新项**。  
  
    2.  在**添加新项**对话框中，从**类别**框中，单击**Orchestration 文件**。 从**模板**框中，单击**BizTalk 业务流程**。  
  
    3.  键入 BizTalk 业务流程的名称，然后单击**添加**。 对于本教程中，输入名称`EmployeeOrch.odx`。  
  
2.  打开**业务流程视图**BizTalk 项目，如果尚未打开的窗口。 若要执行此操作，请单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
3.  将消息添加到业务流程。  
  
    1.  在**业务流程视图**，右键单击**消息**，然后单击**新消息**。  
  
    2.  右键单击新创建的消息中，，然后选择**属性窗口**。  
  
    3.  在**属性**窗格**Message_1**，执行以下操作：  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |Identifier|键入 `NotifyReceive`。|  
        |消息类型|从下拉列表中，展开**架构**，然后选择**Employee_PurchaseOrder.Notification**，其中 Employee_PurchaseOrder 是 BizTalk 项目的名称。 通知是为生成的架构**通知**操作。|  
  
    4.  重复上述步骤以添加四个新消息-为调用 UPDATE_EMPLOYEE 存储过程，并且另一个请求-响应消息设置执行的请求-响应消息设置**插入**操作**Purchase_Order**表。  
  
        |设置为标识符|将消息类型设置为|  
        |-----------------------|-------------------------|  
        |UpdateEmployee|*Employee_PurchaseOrder.TypedProcedure_dbo。UPDATE_EMPLOYEE*，其中 TypedProcedure_dbo。UPDATE_EMPLOYEE 是 UPDATE_EMPLOYEE 的架构存储过程。|  
        |UpdateEmployeeResponse|*Employee_PurchaseOrder.TypedProcedure_dbo。UPDATE_EMPLOYEEResponse*|  
        |InsertPO|*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.Insert*，其中 TableOperation_dbo_Purchase_Order.Insert 是 Purchase_Order 表上的插入操作的架构。|  
        |InsertPOResponse|*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.InsertResponse*|  
  
    5.  保存业务流程文件和 BizTalk 项目。  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 在此步骤中，创建用于调用上使用 SQL Server 执行的入站和出站操作的消息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
## <a name="next-steps"></a>后续步骤  
 中所述添加业务流程形状，可以从 SQL Server 和筛选器通知插入操作中接收通知[第 2 课： 接收和筛选器通知](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)。  
  
## <a name="see-also"></a>另请参阅  
 [第 1 课： 生成架构，并创建消息](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)   
 [步骤 1： 为操作生成架构](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)