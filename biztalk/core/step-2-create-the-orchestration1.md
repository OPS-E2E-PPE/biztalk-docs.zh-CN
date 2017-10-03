---
title: "步骤 2： 创建 Orchestration1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a88cafbb-3b6f-4d27-8516-79a2391b4e31
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1989fe18d9c9c81741ac83bd2f96627ea818eb91
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-the-orchestration"></a><span data-ttu-id="f5b73-102">步骤 2： 创建业务流程</span><span class="sxs-lookup"><span data-stu-id="f5b73-102">Step 2: Create the Orchestration</span></span>
<span data-ttu-id="f5b73-103">使用名为 BeginDocTest 的项目时，业务流程的设置如下所示：</span><span class="sxs-lookup"><span data-stu-id="f5b73-103">The orchestration setup is as follows using a project called BeginDocTest:</span></span>  
  
-   <span data-ttu-id="f5b73-104">端口</span><span class="sxs-lookup"><span data-stu-id="f5b73-104">Ports</span></span>  
  
-   <span data-ttu-id="f5b73-105">消息</span><span class="sxs-lookup"><span data-stu-id="f5b73-105">Messages</span></span>  
  
-   <span data-ttu-id="f5b73-106">发送和接收</span><span class="sxs-lookup"><span data-stu-id="f5b73-106">Send and Receive</span></span>  
  
-   <span data-ttu-id="f5b73-107">构造消息</span><span class="sxs-lookup"><span data-stu-id="f5b73-107">Construct Message</span></span>  
  
-   <span data-ttu-id="f5b73-108">转换</span><span class="sxs-lookup"><span data-stu-id="f5b73-108">Transforms</span></span>  
  
 <span data-ttu-id="f5b73-109">业务流程不处理任何异常。</span><span class="sxs-lookup"><span data-stu-id="f5b73-109">The orchestration does not do any exception handling.</span></span> <span data-ttu-id="f5b73-110">如果连接超时，</span><span class="sxs-lookup"><span data-stu-id="f5b73-110">J.D.</span></span> <span data-ttu-id="f5b73-111">如果连接超时，Edwards OneWorld 会执行它将回滚的隐式事务内的 BeginDoc 和随后操作。这样，BizTalk 业务流程无需执行任何操作来回滚 J.D.Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="f5b73-111">Edwards OneWorld performs the BeginDoc and subsequent operations within an implicit transaction that it will rollback if the connection times out. The BizTalk orchestration thus does not need to do anything to rollback changes J.D.</span></span> <span data-ttu-id="f5b73-112">Edwards OneWorld 所做的更改。</span><span class="sxs-lookup"><span data-stu-id="f5b73-112">Edwards OneWorld makes.</span></span> <span data-ttu-id="f5b73-113">不过，超时会导致 BizTalk 业务流程中出现异常。</span><span class="sxs-lookup"><span data-stu-id="f5b73-113">However, a time out will cause an exception in the BizTalk orchestration.</span></span> <span data-ttu-id="f5b73-114">BizTalk 将异常记录在事件日志中。</span><span class="sxs-lookup"><span data-stu-id="f5b73-114">BizTalk will record the exception in the event log.</span></span> <span data-ttu-id="f5b73-115">如果你要向业务流程添加异常处理，请参阅 Microsoft BizTalk Server 帮助中的“如何添加捕获异常块”和“如何添加补偿块”。</span><span class="sxs-lookup"><span data-stu-id="f5b73-115">If you want to add exception handling to the orchestration, see "How to Add a Catch Exception Block" and "How to Add a Compensation Block" in the Microsoft BizTalk Server Help.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f5b73-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="f5b73-116">In This Section</span></span>  
  
-   [<span data-ttu-id="f5b73-117">任务 1： 创建端口</span><span class="sxs-lookup"><span data-stu-id="f5b73-117">Task 1: Create the Ports</span></span>](../core/task-1-create-the-ports2.md)  
  
-   [<span data-ttu-id="f5b73-118">任务 2： 创建消息</span><span class="sxs-lookup"><span data-stu-id="f5b73-118">Task 2: Create the Messages</span></span>](../core/task-2-create-the-messages1.md)  
  
-   [<span data-ttu-id="f5b73-119">任务 3： 配置发送和接收形状</span><span class="sxs-lookup"><span data-stu-id="f5b73-119">Task 3: Configure the Send and Receive Shapes</span></span>](../core/task-3-configure-the-send-and-receive-shapes1.md)  
  
-   [<span data-ttu-id="f5b73-120">任务 4： 配置构造消息形状</span><span class="sxs-lookup"><span data-stu-id="f5b73-120">Task 4: Configure the Construct Message Shape</span></span>](../core/task-4-configure-the-construct-message-shape2.md)  
  
-   [<span data-ttu-id="f5b73-121">任务 5： 配置转换形状</span><span class="sxs-lookup"><span data-stu-id="f5b73-121">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape1.md)