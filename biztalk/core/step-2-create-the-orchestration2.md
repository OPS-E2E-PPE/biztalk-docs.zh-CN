---
title: 第 2 步：创建 Orchestration2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 08d65525-77a9-4be2-a509-40ea60fa7401
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2510505e52b336a41578834bbd71d69ede6621c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392738"
---
# <a name="step-2-create-the-orchestration"></a><span data-ttu-id="5fb7e-102">第 2 步：创建业务流程</span><span class="sxs-lookup"><span data-stu-id="5fb7e-102">Step 2: Create the Orchestration</span></span>
<span data-ttu-id="5fb7e-103">业务流程的设置是使用名为 BeginDocTest 的项目按如下所示：</span><span class="sxs-lookup"><span data-stu-id="5fb7e-103">The orchestration setup is as follows using a project called BeginDocTest:</span></span>  
  
 <span data-ttu-id="5fb7e-104">• 端口</span><span class="sxs-lookup"><span data-stu-id="5fb7e-104">• Ports</span></span>  
  
 <span data-ttu-id="5fb7e-105">• 消息</span><span class="sxs-lookup"><span data-stu-id="5fb7e-105">• Messages</span></span>  
  
 <span data-ttu-id="5fb7e-106">• 发送和接收</span><span class="sxs-lookup"><span data-stu-id="5fb7e-106">• Send and Receive</span></span>  
  
 <span data-ttu-id="5fb7e-107">• 构造消息</span><span class="sxs-lookup"><span data-stu-id="5fb7e-107">• Construct Message</span></span>  
  
 <span data-ttu-id="5fb7e-108">• 转换</span><span class="sxs-lookup"><span data-stu-id="5fb7e-108">• Transforms</span></span>  
  
 <span data-ttu-id="5fb7e-109">业务流程不处理任何异常。</span><span class="sxs-lookup"><span data-stu-id="5fb7e-109">The orchestration does not do any exception handling.</span></span> <span data-ttu-id="5fb7e-110">J.D.</span><span class="sxs-lookup"><span data-stu-id="5fb7e-110">J.D.</span></span> <span data-ttu-id="5fb7e-111">Edwards EnterpriseOne 执行 BeginDoc 和后续操作，它将回滚，如果连接超时的隐式事务内。BizTalk 业务流程因此不需要执行任何操作来回滚更改 j.d.</span><span class="sxs-lookup"><span data-stu-id="5fb7e-111">Edwards EnterpriseOne performs the BeginDoc and subsequent operations within an implicit transaction that it will rollback if the connection times out. The BizTalk orchestration thus does not need to do anything to rollback changes J.D.</span></span> <span data-ttu-id="5fb7e-112">所做的更改。</span><span class="sxs-lookup"><span data-stu-id="5fb7e-112">Edwards EnterpriseOne makes.</span></span> <span data-ttu-id="5fb7e-113">但是，超时时间将 BizTalk 业务流程中导致异常。</span><span class="sxs-lookup"><span data-stu-id="5fb7e-113">However, a time out will cause an exception in the BizTalk orchestration.</span></span> <span data-ttu-id="5fb7e-114">BizTalk 将异常记录在事件日志中。</span><span class="sxs-lookup"><span data-stu-id="5fb7e-114">BizTalk will record the exception in the event log.</span></span> <span data-ttu-id="5fb7e-115">如果你想要向业务流程添加异常处理，请参阅"如何添加捕获异常块"和"如何添加补偿块"在 Microsoft BizTalk 2006 主帮助。</span><span class="sxs-lookup"><span data-stu-id="5fb7e-115">If you want to add exception handling to the orchestration, see "How to Add a Catch Exception Block" and "How to Add a Compensation Block" in the Microsoft BizTalk 2006 main help.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5fb7e-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="5fb7e-116">In This Section</span></span>  
  
-   [<span data-ttu-id="5fb7e-117">任务 1:创建端口</span><span class="sxs-lookup"><span data-stu-id="5fb7e-117">Task 1: Create the Ports</span></span>](../core/task-1-create-the-ports1.md)  
  
-   [<span data-ttu-id="5fb7e-118">任务 2:创建消息</span><span class="sxs-lookup"><span data-stu-id="5fb7e-118">Task 2: Create the Messages</span></span>](../core/task-2-create-the-messages2.md)  
  
-   [<span data-ttu-id="5fb7e-119">任务 3:配置发送和接收形状</span><span class="sxs-lookup"><span data-stu-id="5fb7e-119">Task 3: Configure the Send and Receive Shapes</span></span>](../core/task-3-configure-the-send-and-receive-shapes2.md)  
  
-   [<span data-ttu-id="5fb7e-120">任务 4:配置构造消息形状</span><span class="sxs-lookup"><span data-stu-id="5fb7e-120">Task 4: Configure the Construct Message Shape</span></span>](../core/task-4-configure-the-construct-message-shape1.md)  
  
-   [<span data-ttu-id="5fb7e-121">任务 5:配置转换形状</span><span class="sxs-lookup"><span data-stu-id="5fb7e-121">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape2.md)