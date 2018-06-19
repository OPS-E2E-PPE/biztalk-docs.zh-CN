---
title: 第 3 课： 执行存储的过程以选择新添加的员工 |Microsoft 文档
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
ms.openlocfilehash: 7af49c026b443fb1ca6a0fb7f35b64cdf1e377f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222621"
---
# <a name="lesson-3-execute-a-stored-procedure-to-select-new-employees-added"></a>第 3 课： 执行存储的过程以选择新添加的员工
在本课程中了解任务执行之前，你必须首先了解为什么所需的这些任务。 **员工**到记录插入要添加新员工的表定义的方式，**状态**列始终设置为"0"，每次添加新员工。 以便你可以使用此列的新添加的员工查询，还将获得通知，则是完成此操作。 在 SQL Server，你需要查询这通过运行以下 SQL 语句：  
  
```  
SELECT Employee_ID, Name, Designation FROM Employee WHERE Status = 0  
```  
  
 新接收的列表添加员工后，你还必须更新**状态**列添加到"1"，因此，下一次添加新员工和你运行相同的查询，不会记录以及旧员工。 若要确保上述 Select 语句为仅新添加的员工提供了，你将更新**员工**表使用以下 SQL 语句：  
  
```  
UPDATE Employee SET Status = 1 WHERE Status = 0  
```  
  
 因此，**状态**旧员工的列设置为"1"，而新员工将始终为"0"。  
  
 在本课程中，将执行存储的过程、 **UPDATE_EMPLOYEE**，其中又执行选择和更新语句。 完成本课程中后，您的业务流程将执行以下操作：  
  
1.  接收对的任何更改的通知**员工**表。  
  
2.  收到的通知消息中提取通知的类型。  
  
3.  如果通知消息是针对插入操作，业务流程执行**UPDATE_EMPLOYEE**存储过程。  
  
4.  存储的过程会读取中的新输入的记录**员工**表。 在读取新记录后, 存储的过程还将**状态**"1。 这些记录的列  
  
 现在您知道您需要执行存储的过程。 你现在需要考虑如何执行此业务流程的一部分。 业务流程需要的请求消息**UPDATE_EMPLOYEE**存储过程。 在本教程中，你将创建一个自定义类库，将动态创建消息，然后将其提供给业务流程。 业务流程收到消息后，它将消息发送到 SQL Server 使用的 SQL 适配器和接收响应。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1： 为 UPDATE_EMPLOYEE 创建请求消息存储过程](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)  
  
-   [步骤 2： 将请求消息发送到 SQL Server，并接收响应](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)