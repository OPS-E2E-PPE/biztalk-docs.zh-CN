---
title: "第 3 课： 执行存储的过程以选择新添加的员工 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec7897e9-0c77-41b2-8cc2-61745bd3b028
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7af49c026b443fb1ca6a0fb7f35b64cdf1e377f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-3-execute-a-stored-procedure-to-select-new-employees-added"></a><span data-ttu-id="bee8f-102">第 3 课： 执行存储的过程以选择新添加的员工</span><span class="sxs-lookup"><span data-stu-id="bee8f-102">Lesson 3: Execute a Stored Procedure to Select New Employees Added</span></span>
<span data-ttu-id="bee8f-103">在本课程中了解任务执行之前，你必须首先了解为什么所需的这些任务。</span><span class="sxs-lookup"><span data-stu-id="bee8f-103">Before understanding the tasks performed in this lesson, you must first understand why these tasks are required.</span></span> <span data-ttu-id="bee8f-104">**员工**到记录插入要添加新员工的表定义的方式，**状态**列始终设置为"0"，每次添加新员工。</span><span class="sxs-lookup"><span data-stu-id="bee8f-104">The **Employee** table to which the records are inserted to add a new employee is defined in such a way that a **Status** column is always set to “0” every time a new employee is added.</span></span> <span data-ttu-id="bee8f-105">以便你可以使用此列的新添加的员工查询，还将获得通知，则是完成此操作。</span><span class="sxs-lookup"><span data-stu-id="bee8f-105">This is done so that you can use this column to query for newly added employees and also get notifications.</span></span> <span data-ttu-id="bee8f-106">在 SQL Server，你需要查询这通过运行以下 SQL 语句：</span><span class="sxs-lookup"><span data-stu-id="bee8f-106">In SQL Server, you would query this by running the following SQL statement:</span></span>  
  
```  
SELECT Employee_ID, Name, Designation FROM Employee WHERE Status = 0  
```  
  
 <span data-ttu-id="bee8f-107">新接收的列表添加员工后，你还必须更新**状态**列添加到"1"，因此，下一次添加新员工和你运行相同的查询，不会记录以及旧员工。</span><span class="sxs-lookup"><span data-stu-id="bee8f-107">After receiving the list of newly added employees, you must also update the **Status** column to “1” so that the next time new employees are added and you run the same query, you do not get records for old employees as well.</span></span> <span data-ttu-id="bee8f-108">若要确保上述 Select 语句为仅新添加的员工提供了，你将更新**员工**表使用以下 SQL 语句：</span><span class="sxs-lookup"><span data-stu-id="bee8f-108">To make sure that the above Select statement gives only the newly added employees, you will update the **Employee** table using the following SQL statement:</span></span>  
  
```  
UPDATE Employee SET Status = 1 WHERE Status = 0  
```  
  
 <span data-ttu-id="bee8f-109">因此，**状态**旧员工的列设置为"1"，而新员工将始终为"0"。</span><span class="sxs-lookup"><span data-stu-id="bee8f-109">So, the **Status** column for the old employees is set to “1” while new employees will always be “0.”</span></span>  
  
 <span data-ttu-id="bee8f-110">在本课程中，将执行存储的过程、 **UPDATE_EMPLOYEE**，其中又执行选择和更新语句。</span><span class="sxs-lookup"><span data-stu-id="bee8f-110">In this lesson, you will execute a stored procedure, **UPDATE_EMPLOYEE**, which in turn executes the Select and Update statements.</span></span> <span data-ttu-id="bee8f-111">完成本课程中后，您的业务流程将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bee8f-111">After you have finished this lesson, your orchestration will do the following:</span></span>  
  
1.  <span data-ttu-id="bee8f-112">接收对的任何更改的通知**员工**表。</span><span class="sxs-lookup"><span data-stu-id="bee8f-112">Receives notification for any changes to the **Employee** table.</span></span>  
  
2.  <span data-ttu-id="bee8f-113">收到的通知消息中提取通知的类型。</span><span class="sxs-lookup"><span data-stu-id="bee8f-113">Extracts the type of notification from the notification message received.</span></span>  
  
3.  <span data-ttu-id="bee8f-114">如果通知消息是针对插入操作，业务流程执行**UPDATE_EMPLOYEE**存储过程。</span><span class="sxs-lookup"><span data-stu-id="bee8f-114">If the notification message is for an Insert operation, the orchestration executes the **UPDATE_EMPLOYEE** stored procedure.</span></span>  
  
4.  <span data-ttu-id="bee8f-115">存储的过程会读取中的新输入的记录**员工**表。</span><span class="sxs-lookup"><span data-stu-id="bee8f-115">The stored procedure reads the newly entered records in the **Employee** table.</span></span> <span data-ttu-id="bee8f-116">在读取新记录后, 存储的过程还将**状态**"1。 这些记录的列</span><span class="sxs-lookup"><span data-stu-id="bee8f-116">After reading the new records, the stored procedure also sets the **Status** column for those records to “1.”</span></span>  
  
 <span data-ttu-id="bee8f-117">现在您知道您需要执行存储的过程。</span><span class="sxs-lookup"><span data-stu-id="bee8f-117">Now you know why you need to execute the stored procedure.</span></span> <span data-ttu-id="bee8f-118">你现在需要考虑如何执行此业务流程的一部分。</span><span class="sxs-lookup"><span data-stu-id="bee8f-118">You now need to think about how to execute this as part of the orchestration.</span></span> <span data-ttu-id="bee8f-119">业务流程需要的请求消息**UPDATE_EMPLOYEE**存储过程。</span><span class="sxs-lookup"><span data-stu-id="bee8f-119">The orchestration needs a request message for the **UPDATE_EMPLOYEE** stored procedure.</span></span> <span data-ttu-id="bee8f-120">在本教程中，你将创建一个自定义类库，将动态创建消息，然后将其提供给业务流程。</span><span class="sxs-lookup"><span data-stu-id="bee8f-120">In this tutorial, you will create a custom class library that will create the message on the fly and then provide it to the orchestration.</span></span> <span data-ttu-id="bee8f-121">业务流程收到消息后，它将消息发送到 SQL Server 使用的 SQL 适配器和接收响应。</span><span class="sxs-lookup"><span data-stu-id="bee8f-121">After the orchestration receives the message, it will send the message to the SQL Server using the SQL adapter and receive the response.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bee8f-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="bee8f-122">In This Section</span></span>  
  
-   [<span data-ttu-id="bee8f-123">步骤 1： 为 UPDATE_EMPLOYEE 创建请求消息存储过程</span><span class="sxs-lookup"><span data-stu-id="bee8f-123">Step 1: Create the Request Message for UPDATE_EMPLOYEE Stored Procedure</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)  
  
-   [<span data-ttu-id="bee8f-124">步骤 2： 将请求消息发送到 SQL Server，并接收响应</span><span class="sxs-lookup"><span data-stu-id="bee8f-124">Step 2: Send the Request Message to SQL Server and Receive Response</span></span>](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)