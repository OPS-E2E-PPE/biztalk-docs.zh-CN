---
title: 第 2 步：为 BizTalk 业务流程创建消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47a4fb98-6085-4aeb-ab39-2f2c3858d4e0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 026dd9f832ee0422a49c520db65f0d3b1cd79de7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367826"
---
# <a name="step-2-create-messages-for-biztalk-orchestrations"></a>第 2 步：为 BizTalk 业务流程创建消息
![步骤 2 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")  
  
 **若要完成的时间：** 5 分钟  
  
 **目标：** 在此步骤中，将向 BizTalk 项目添加业务流程和为在生成的架构创建消息[步骤 1:为操作生成架构](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)。  
  
## <a name="prerequisites"></a>先决条件  
 你必须已完成[步骤 1:为操作生成架构](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)。  
  
### <a name="to-create-messages-in-an-orchestration"></a>若要在业务流程中创建消息  
  
1. 将 BizTalk 业务流程添加到 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]:  
  
   1.  从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**外**，然后单击**新项**。  
  
   2.  在中**添加新项**对话框中，从**类别**框中，单击**业务流程文件**。 从**模板**框中，单击**BizTalk 业务流程**。  
  
   3.  键入 BizTalk 业务流程的名称，然后单击**添加**。 对于本教程中，输入名称`EmployeeOrch.odx`。  
  
2. 打开**业务流程视图**BizTalk 项目，如果已打开的窗口。 若要执行此操作，请单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  
  
3. 将消息添加到业务流程。  
  
   1.  在中**业务流程视图**，右键单击**消息**，然后单击**新消息**。  
  
   2.  右键单击新创建的消息，然后依次**属性窗口**。  
  
   3.  在中**属性**窗格**Message_1**，执行以下操作：  
  
       |使用此选项|执行的操作|  
       |--------------|----------------|  
       |Identifier|键入 `NotifyReceive`。|  
       |消息类型|从下拉列表中，展开**架构**，然后选择**Employee_PurchaseOrder.Notification**，其中 Employee_PurchaseOrder 是 BizTalk 项目的名称。 通知是为生成的架构**通知**操作。|  
  
   4.  重复上述步骤添加四个新消息，请求-响应消息设置为调用 UPDATE_EMPLOYEE 存储过程和为执行设置的另一个请求-响应消息**插入**上的操作**Purchase_Order**表。  
  
       |将标识符设置为|将消息类型设置为|  
       |-----------------------|-------------------------|  
       |UpdateEmployee|*Employee_PurchaseOrder.TypedProcedure_dbo。UPDATE_EMPLOYEE*，其中 TypedProcedure_dbo。UPDATE_EMPLOYEE 是 UPDATE_EMPLOYEE 的架构存储过程。|  
       |UpdateEmployeeResponse|*Employee_PurchaseOrder.TypedProcedure_dbo.UPDATE_EMPLOYEEResponse*|  
       |InsertPO|*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.Insert*TableOperation_dbo_Purchase_Order.Insert 所在 Purchase_Order 表上的插入操作的架构。|  
       |InsertPOResponse|*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.InsertResponse*|  
  
   5.  保存业务流程文件和 BizTalk 项目。  
  
## <a name="what-did-i-just-do"></a>我只需做了什么？  
 在此步骤中，创建用于调用上使用 SQL Server 执行入站和出站操作消息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
## <a name="next-steps"></a>后续步骤  
 您将添加业务流程形状从 SQL Server 和筛选器的插入操作的通知接收通知，如中所述[第 2 课：接收和筛选通知](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)。  
  
## <a name="see-also"></a>请参阅  
 [第 1 课：生成架构并创建消息](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)   
 [步骤 1：为操作生成架构](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)