---
title: 第 3 课： 执行存储的过程以选择新添加的员工 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec7897e9-0c77-41b2-8cc2-61745bd3b028
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3021a5e3ead821a0f3c8d0372d48ae469a834c1c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001854"
---
# <a name="lesson-3-execute-a-stored-procedure-to-select-new-employees-added"></a>第 3 课： 执行存储的过程以选择新添加的员工
在本课程中了解任务执行之前，必须首先了解为什么这些任务所需。 **员工**向其插入记录来添加新员工的表定义的方式，**状态**列始终设置为"0"，每次添加新员工。 这样，以便此列可用于查询的新添加的员工，还将获得通知。 在 SQL Server 中，您将查询这通过运行以下 SQL 语句：  
  
```  
SELECT Employee_ID, Name, Designation FROM Employee WHERE Status = 0  
```  
  
 接收新的列表添加员工后，还必须更新**状态**为"1"，因此，下一次添加新员工和您运行同一查询的列，则不会收到记录以及旧员工。 若要确保上述 Select 语句提供了只有新添加的员工，你将更新**员工**表可使用以下 SQL 语句：  
  
```  
UPDATE Employee SET Status = 1 WHERE Status = 0  
```  
  
 因此，**状态**旧员工的列设置为"1"，而新员工将始终为"0"。  
  
 在本课程中，将执行存储的过程**UPDATE_EMPLOYEE**，这将执行 Select 和 Update 语句。 完成本课程后，您的业务流程将执行以下操作：  
  
1. 接收到任何更改通知**员工**表。  
  
2. 从收到的通知消息中提取通知的类型。  
  
3. 如果通知消息是针对插入操作，业务流程将执行**UPDATE_EMPLOYEE**存储过程。  
  
4. 存储的过程读取中的新输入的记录**员工**表。 阅读完后的新记录，该存储的过程还设置**状态**为"1。 这些记录的列  
  
   现在您了解为何需要执行存储的过程。 现在需要考虑如何执行此业务流程的一部分。 业务流程需要的请求消息**UPDATE_EMPLOYEE**存储过程。 在本教程中，将创建一个自定义的类库，用于将动态创建消息并将其提供给业务流程。 业务流程收到消息后，它将消息发送到 SQL Server 使用 SQL 适配器和接收响应。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1：为 UPDATE_EMPLOYEE 存储过程创建请求消息](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)  
  
-   [步骤 2：向 SQL Server 发送请求消息并接收响应](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)