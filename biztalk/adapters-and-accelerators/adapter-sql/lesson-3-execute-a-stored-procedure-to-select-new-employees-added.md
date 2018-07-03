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
# <a name="lesson-3-execute-a-stored-procedure-to-select-new-employees-added"></a><span data-ttu-id="70275-102">第 3 课： 执行存储的过程以选择新添加的员工</span><span class="sxs-lookup"><span data-stu-id="70275-102">Lesson 3: Execute a Stored Procedure to Select New Employees Added</span></span>
<span data-ttu-id="70275-103">在本课程中了解任务执行之前，必须首先了解为什么这些任务所需。</span><span class="sxs-lookup"><span data-stu-id="70275-103">Before understanding the tasks performed in this lesson, you must first understand why these tasks are required.</span></span> <span data-ttu-id="70275-104">**员工**向其插入记录来添加新员工的表定义的方式，**状态**列始终设置为"0"，每次添加新员工。</span><span class="sxs-lookup"><span data-stu-id="70275-104">The **Employee** table to which the records are inserted to add a new employee is defined in such a way that a **Status** column is always set to “0” every time a new employee is added.</span></span> <span data-ttu-id="70275-105">这样，以便此列可用于查询的新添加的员工，还将获得通知。</span><span class="sxs-lookup"><span data-stu-id="70275-105">This is done so that you can use this column to query for newly added employees and also get notifications.</span></span> <span data-ttu-id="70275-106">在 SQL Server 中，您将查询这通过运行以下 SQL 语句：</span><span class="sxs-lookup"><span data-stu-id="70275-106">In SQL Server, you would query this by running the following SQL statement:</span></span>  
  
```  
SELECT Employee_ID, Name, Designation FROM Employee WHERE Status = 0  
```  
  
 <span data-ttu-id="70275-107">接收新的列表添加员工后，还必须更新**状态**为"1"，因此，下一次添加新员工和您运行同一查询的列，则不会收到记录以及旧员工。</span><span class="sxs-lookup"><span data-stu-id="70275-107">After receiving the list of newly added employees, you must also update the **Status** column to “1” so that the next time new employees are added and you run the same query, you do not get records for old employees as well.</span></span> <span data-ttu-id="70275-108">若要确保上述 Select 语句提供了只有新添加的员工，你将更新**员工**表可使用以下 SQL 语句：</span><span class="sxs-lookup"><span data-stu-id="70275-108">To make sure that the above Select statement gives only the newly added employees, you will update the **Employee** table using the following SQL statement:</span></span>  
  
```  
UPDATE Employee SET Status = 1 WHERE Status = 0  
```  
  
 <span data-ttu-id="70275-109">因此，**状态**旧员工的列设置为"1"，而新员工将始终为"0"。</span><span class="sxs-lookup"><span data-stu-id="70275-109">So, the **Status** column for the old employees is set to “1” while new employees will always be “0.”</span></span>  
  
 <span data-ttu-id="70275-110">在本课程中，将执行存储的过程**UPDATE_EMPLOYEE**，这将执行 Select 和 Update 语句。</span><span class="sxs-lookup"><span data-stu-id="70275-110">In this lesson, you will execute a stored procedure, **UPDATE_EMPLOYEE**, which in turn executes the Select and Update statements.</span></span> <span data-ttu-id="70275-111">完成本课程后，您的业务流程将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="70275-111">After you have finished this lesson, your orchestration will do the following:</span></span>  
  
1. <span data-ttu-id="70275-112">接收到任何更改通知**员工**表。</span><span class="sxs-lookup"><span data-stu-id="70275-112">Receives notification for any changes to the **Employee** table.</span></span>  
  
2. <span data-ttu-id="70275-113">从收到的通知消息中提取通知的类型。</span><span class="sxs-lookup"><span data-stu-id="70275-113">Extracts the type of notification from the notification message received.</span></span>  
  
3. <span data-ttu-id="70275-114">如果通知消息是针对插入操作，业务流程将执行**UPDATE_EMPLOYEE**存储过程。</span><span class="sxs-lookup"><span data-stu-id="70275-114">If the notification message is for an Insert operation, the orchestration executes the **UPDATE_EMPLOYEE** stored procedure.</span></span>  
  
4. <span data-ttu-id="70275-115">存储的过程读取中的新输入的记录**员工**表。</span><span class="sxs-lookup"><span data-stu-id="70275-115">The stored procedure reads the newly entered records in the **Employee** table.</span></span> <span data-ttu-id="70275-116">阅读完后的新记录，该存储的过程还设置**状态**为"1。 这些记录的列</span><span class="sxs-lookup"><span data-stu-id="70275-116">After reading the new records, the stored procedure also sets the **Status** column for those records to “1.”</span></span>  
  
   <span data-ttu-id="70275-117">现在您了解为何需要执行存储的过程。</span><span class="sxs-lookup"><span data-stu-id="70275-117">Now you know why you need to execute the stored procedure.</span></span> <span data-ttu-id="70275-118">现在需要考虑如何执行此业务流程的一部分。</span><span class="sxs-lookup"><span data-stu-id="70275-118">You now need to think about how to execute this as part of the orchestration.</span></span> <span data-ttu-id="70275-119">业务流程需要的请求消息**UPDATE_EMPLOYEE**存储过程。</span><span class="sxs-lookup"><span data-stu-id="70275-119">The orchestration needs a request message for the **UPDATE_EMPLOYEE** stored procedure.</span></span> <span data-ttu-id="70275-120">在本教程中，将创建一个自定义的类库，用于将动态创建消息并将其提供给业务流程。</span><span class="sxs-lookup"><span data-stu-id="70275-120">In this tutorial, you will create a custom class library that will create the message on the fly and then provide it to the orchestration.</span></span> <span data-ttu-id="70275-121">业务流程收到消息后，它将消息发送到 SQL Server 使用 SQL 适配器和接收响应。</span><span class="sxs-lookup"><span data-stu-id="70275-121">After the orchestration receives the message, it will send the message to the SQL Server using the SQL adapter and receive the response.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="70275-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="70275-122">In This Section</span></span>  
  
-   [<span data-ttu-id="70275-123">步骤 1：为 UPDATE_EMPLOYEE 存储过程创建请求消息</span><span class="sxs-lookup"><span data-stu-id="70275-123">Step 1: Create the Request Message for UPDATE_EMPLOYEE Stored Procedure</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)  
  
-   [<span data-ttu-id="70275-124">步骤 2：向 SQL Server 发送请求消息并接收响应</span><span class="sxs-lookup"><span data-stu-id="70275-124">Step 2: Send the Request Message to SQL Server and Receive Response</span></span>](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)