---
title: 第 4 课：执行采购订单表上的插入操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66fc64c5-a3da-4014-8545-f34e6577bd73
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8da95d9e06c2aadfa293e54d1fb7c71321577d5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368796"
---
# <a name="lesson-4-perform-an-insert-operation-on-the-purchase-order-table"></a>第 4 课：执行采购订单表上的插入操作
在[第 3 课：执行存储过程，以选择新添加员工](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)，则执行**UPDATE_EMPLOYEE**存储过程，并收到一条包含新插入的员工记录的详细信息的响应消息。 在本课中，将在上一课上构建，并更新业务流程，以执行以下步骤：  
  
1.  在业务流程内生成要在执行插入操作的消息**Purchase_Order**表。 此步骤是类似于[步骤 1:创建请求消息为 UPDATE_EMPLOYEE 存储过程](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)。  
  
2.  生成请求消息后，您将映射的响应消息**UPDATE_EMPLOYEE**存储过程到插入操作的请求消息**Purchase_Order**表。 通过消息映射，你将传递到插入操作的请求消息收到从响应消息的值。  
  
3.  发送要插入的记录中的消息**Purchase_Order**表并接收响应。  
  
4.  发送到发送端口的响应。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1：在 Purchase_Order 表中创建插入操作的请求消息](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md)  
  
-   [步骤 2：将 UPDATE_EMPLOYEE 响应消息映射到插入操作请求消息](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)  
  
-   [步骤 3：向插入记录发送请求消息并接收响应](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)  
  
-   [步骤 4：生成项目](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md)