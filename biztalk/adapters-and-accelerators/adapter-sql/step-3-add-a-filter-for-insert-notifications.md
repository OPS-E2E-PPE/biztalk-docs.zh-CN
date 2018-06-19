---
title: 步骤 3： 添加筛选器插入通知 |Microsoft 文档
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
ms.openlocfilehash: 97fc32fe7dd657bb45edca91fda0eddaa537b32a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223261"
---
# <a name="step-3-add-a-filter-for-insert-notifications"></a>步骤 3： 添加筛选器插入通知
![步骤 3 / 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **完成时间：** 5 分钟  
  
 **目标：** 在此步骤中，你可以将确定形状添加到要用于插入操作的通知消息的筛选器业务流程。 仅当所接收的通知属于插入类型执行业务流程中的后续操作。  
  
## <a name="prerequisites"></a>先决条件  
 你必须已完成[步骤 2： 从通知消息中提取通知类型](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)。  
  
### <a name="to-filter-for-notification-messages"></a>若要筛选的通知消息  
  
1.  添加**确定**形状变为业务流程之后,**表达式**形状。 从工具箱中，拖动**确定**形状拖到所连接的正下方线**表达式**形状。  
  
     **确定**形状展开以显示有关分支**如果**语句 **(Rule_1)** 和有关分支**Else**语句。  
  
2.  在设计图面上，右键单击**确定**形状，并依次**属性窗口**。  
  
3.  在**属性**窗格**确定**形状，在**名称**属性中，键入`CheckNotification`。  
  
4.  在设计图面上，右键单击**Rule_1**形状 (内**确定**形状)，然后单击**属性窗口**。  
  
5.  在**属性**窗格**Rule_1**中**名称**属性中，键入**插入**。  
  
6.  右键单击**插入**形状，并依次**编辑布尔表达式**。  
  
7.  在 BizTalk 表达式编辑器中，键入以下命令：  
  
    ```  
    NotificationType.Equals("Insert")  
    ```  
  
     这种情况告诉业务流程，以便才执行后续操作中的值**NotificationType**变量是**插入**。  
  
    > [!NOTE]
    >  添加此变量在[步骤 2： 从通知消息中提取通知类型](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)从 SQL Server 数据库从收到的通知消息中提取通知的类型。  
  
8.  下图显示与正在进行中业务流程**确定**包含的形状。  
  
     ![将确定形状添加到业务流程](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-03-add-filter-orch.gif "sql_adap_tut_03_add_filter_orch")  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 在此步骤中，您将添加**确定**形状来筛选要对于 Insert 操作是在收到通知时，才执行后续操作的通知消息。  
  
## <a name="next-steps"></a>后续步骤  
 在下一步，你添加业务流程形状来调用 UPDATE_EMPLOYE 员工表中，存储过程中所述[第 3 课： 执行存储过程向选择新添加的员工](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 2： 从通知消息中提取通知类型](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)   
 [第 2 课： 接收和筛选器通知](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)