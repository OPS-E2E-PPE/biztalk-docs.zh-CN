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
# <a name="lesson-4-perform-an-insert-operation-on-the-purchase-order-table"></a><span data-ttu-id="4c9b1-102">第 4 课：执行采购订单表上的插入操作</span><span class="sxs-lookup"><span data-stu-id="4c9b1-102">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>
<span data-ttu-id="4c9b1-103">在[第 3 课：执行存储过程，以选择新添加员工](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)，则执行**UPDATE_EMPLOYEE**存储过程，并收到一条包含新插入的员工记录的详细信息的响应消息。</span><span class="sxs-lookup"><span data-stu-id="4c9b1-103">In [Lesson 3: Execute a Stored Procedure to Select New Employees Added](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md), you executed the **UPDATE_EMPLOYEE** stored procedure and received a response message that contains the details of the newly inserted employee record.</span></span> <span data-ttu-id="4c9b1-104">在本课中，将在上一课上构建，并更新业务流程，以执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4c9b1-104">In this lesson, you will build on the previous lesson and update the orchestration to perform the following steps:</span></span>  
  
1.  <span data-ttu-id="4c9b1-105">在业务流程内生成要在执行插入操作的消息**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="4c9b1-105">Within the orchestration, you build the message to perform an Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="4c9b1-106">此步骤是类似于[步骤 1:创建请求消息为 UPDATE_EMPLOYEE 存储过程](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)。</span><span class="sxs-lookup"><span data-stu-id="4c9b1-106">This step is similar to [Step 1: Create the Request Message for UPDATE_EMPLOYEE Stored Procedure](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md).</span></span>  
  
2.  <span data-ttu-id="4c9b1-107">生成请求消息后，您将映射的响应消息**UPDATE_EMPLOYEE**存储过程到插入操作的请求消息**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="4c9b1-107">After you build the request message, you map the response message of the **UPDATE_EMPLOYEE** stored procedure to the request message for the Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="4c9b1-108">通过消息映射，你将传递到插入操作的请求消息收到从响应消息的值。</span><span class="sxs-lookup"><span data-stu-id="4c9b1-108">By mapping the messages, you pass the values received from the response messages to the request message for Insert operation.</span></span>  
  
3.  <span data-ttu-id="4c9b1-109">发送要插入的记录中的消息**Purchase_Order**表并接收响应。</span><span class="sxs-lookup"><span data-stu-id="4c9b1-109">You send the message to insert a record in the **Purchase_Order** table and receive a response.</span></span>  
  
4.  <span data-ttu-id="4c9b1-110">发送到发送端口的响应。</span><span class="sxs-lookup"><span data-stu-id="4c9b1-110">You send the response to a send port.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4c9b1-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="4c9b1-111">In This Section</span></span>  
  
-   [<span data-ttu-id="4c9b1-112">步骤 1：在 Purchase_Order 表中创建插入操作的请求消息</span><span class="sxs-lookup"><span data-stu-id="4c9b1-112">Step 1: Create the Request Message for Insert Operation on Purchase_Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md)  
  
-   [<span data-ttu-id="4c9b1-113">步骤 2：将 UPDATE_EMPLOYEE 响应消息映射到插入操作请求消息</span><span class="sxs-lookup"><span data-stu-id="4c9b1-113">Step 2: Map the UPDATE_EMPLOYEE Response Message to Insert Operation Request Message</span></span>](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)  
  
-   [<span data-ttu-id="4c9b1-114">步骤 3：向插入记录发送请求消息并接收响应</span><span class="sxs-lookup"><span data-stu-id="4c9b1-114">Step 3: Send the Request Message to Insert Records and Receive a Response</span></span>](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)  
  
-   [<span data-ttu-id="4c9b1-115">步骤 4：生成项目</span><span class="sxs-lookup"><span data-stu-id="4c9b1-115">Step 4: Build the Project</span></span>](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md)