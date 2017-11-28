---
title: "第 4 课： 执行插入操作上采购订单表 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 66fc64c5-a3da-4014-8545-f34e6577bd73
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c966e3c10f18424b2cfb1fde0235caedbb5f58f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-4-perform-an-insert-operation-on-the-purchase-order-table"></a><span data-ttu-id="cb0af-102">第 4 课： 执行插入操作上采购订单表</span><span class="sxs-lookup"><span data-stu-id="cb0af-102">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>
<span data-ttu-id="cb0af-103">在[第 3 课： 执行存储过程向选择新添加的员工](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)，你执行**UPDATE_EMPLOYEE**存储过程并收到一条包含的详细信息的响应消息新插入员工记录。</span><span class="sxs-lookup"><span data-stu-id="cb0af-103">In [Lesson 3: Execute a Stored Procedure to Select New Employees Added](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md), you executed the **UPDATE_EMPLOYEE** stored procedure and received a response message that contains the details of the newly inserted employee record.</span></span> <span data-ttu-id="cb0af-104">在本课程中，你将在上一课上生成并更新业务流程执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cb0af-104">In this lesson, you will build on the previous lesson and update the orchestration to perform the following steps:</span></span>  
  
1.  <span data-ttu-id="cb0af-105">业务流程，在生成要在执行插入操作的消息**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="cb0af-105">Within the orchestration, you build the message to perform an Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="cb0af-106">此步骤是类似于[步骤 1： 为 UPDATE_EMPLOYEE 存储过程创建请求消息](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)。</span><span class="sxs-lookup"><span data-stu-id="cb0af-106">This step is similar to [Step 1: Create the Request Message for UPDATE_EMPLOYEE Stored Procedure](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md).</span></span>  
  
2.  <span data-ttu-id="cb0af-107">生成请求消息后，你将响应消息映射的**UPDATE_EMPLOYEE**存储插入操作的请求消息的过程**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="cb0af-107">After you build the request message, you map the response message of the **UPDATE_EMPLOYEE** stored procedure to the request message for the Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="cb0af-108">通过将消息映射，你将传递到插入操作的请求消息接收响应消息中的值。</span><span class="sxs-lookup"><span data-stu-id="cb0af-108">By mapping the messages, you pass the values received from the response messages to the request message for Insert operation.</span></span>  
  
3.  <span data-ttu-id="cb0af-109">发送要插入中的记录的消息**Purchase_Order**表和接收响应。</span><span class="sxs-lookup"><span data-stu-id="cb0af-109">You send the message to insert a record in the **Purchase_Order** table and receive a response.</span></span>  
  
4.  <span data-ttu-id="cb0af-110">发送对发送端口的响应。</span><span class="sxs-lookup"><span data-stu-id="cb0af-110">You send the response to a send port.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cb0af-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="cb0af-111">In This Section</span></span>  
  
-   [<span data-ttu-id="cb0af-112">步骤 1： 为 Purchase_Order 表上插入操作创建的请求消息</span><span class="sxs-lookup"><span data-stu-id="cb0af-112">Step 1: Create the Request Message for Insert Operation on Purchase_Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md)  
  
-   [<span data-ttu-id="cb0af-113">步骤 2： 映射要插入操作的请求消息的 UPDATE_EMPLOYEE 响应消息</span><span class="sxs-lookup"><span data-stu-id="cb0af-113">Step 2: Map the UPDATE_EMPLOYEE Response Message to Insert Operation Request Message</span></span>](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)  
  
-   [<span data-ttu-id="cb0af-114">步骤 3： 发送要插入记录和接收响应的请求消息</span><span class="sxs-lookup"><span data-stu-id="cb0af-114">Step 3: Send the Request Message to Insert Records and Receive a Response</span></span>](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)  
  
-   [<span data-ttu-id="cb0af-115">步骤 4： 生成项目</span><span class="sxs-lookup"><span data-stu-id="cb0af-115">Step 4: Build the Project</span></span>](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md)