---
title: 步骤 3：为插入通知添加筛选器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53a1e9ef-a179-42a7-b4ae-b1170181053b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e49f4f914771a26618dd92126b49143492d627b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367929"
---
# <a name="step-3-add-a-filter-for-insert-notifications"></a>步骤 3：为插入通知添加筛选器
![第 3 部分，共 3 步](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **若要完成的时间：** 5 分钟  
  
 **目标：** 在此步骤中，您将判定形状添加到业务流程，以筛选用于插入操作的通知消息。 仅当所接收的通知是插入类型，会执行业务流程中的后续操作。  
  
## <a name="prerequisites"></a>先决条件  
 你必须已完成[步骤 2:从通知消息中提取通知类型](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)。  
  
### <a name="to-filter-for-notification-messages"></a>若要筛选的通知消息  
  
1.  添加**判定**到该业务流程形状后面**表达式**形状。 从工具箱拖动**判定**下方的连接线上的形状**表达式**形状。  
  
     **判定**形状将展开以显示对应于的分支**如果**语句 **(Rule_1)** 分支和**Else**语句。  
  
2.  在设计图面上，右键单击**判定**形状，然后依次**属性窗口**。  
  
3.  在中**属性**窗格**判定**形状，在**名称**属性中，键入`CheckNotification`。  
  
4.  在设计图面上，右键单击**Rule_1**形状 (内**判定**形状)，然后单击**属性窗口**。  
  
5.  在中**属性**窗格**Rule_1**，在**名称**属性中，键入**插入**。  
  
6.  右键单击**插入**形状，然后依次**编辑布尔表达式**。  
  
7.  在 BizTalk 表达式编辑器中，键入以下内容：  
  
    ```  
    NotificationType.Equals("Insert")  
    ```  
  
     这种情况告诉业务流程以便才执行后续操作中的值**NotificationType**变量是**插入**。  
  
    > [!NOTE]
    >  添加此变量在[步骤 2:从通知消息中提取通知类型](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)从收到从 SQL Server 数据库的通知消息中提取的通知类型。  
  
8.  下图显示了与正在进行中业务流程**判定**包含的形状。  
  
     ![将判定形状添加到业务流程](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-03-add-filter-orch.gif "sql_adap_tut_03_add_filter_orch")  
  
## <a name="what-did-i-just-do"></a>我只需做了什么？  
 在此步骤中，您添加了**判定**形状来筛选要接收通知所针对的插入操作时，才执行后续操作的通知消息。  
  
## <a name="next-steps"></a>后续步骤  
 在下一步，您添加业务流程形状来调用 UPDATE_EMPLOYE 员工表中，在存储过程中所述[第 3 课：执行存储的过程以选择新添加的员工](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)。  
  
## <a name="see-also"></a>请参阅  
 [步骤 2：从通知消息中提取通知类型](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)   
 [第 2 课：接收和筛选通知](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)