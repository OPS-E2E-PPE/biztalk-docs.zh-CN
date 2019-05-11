---
title: 任务 4：配置构造消息形状 2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43a7b912-0293-41be-b992-309eca550801
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47251eb4d9011c2c0221af75e7190abe2487a440
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399233"
---
# <a name="task-4-configure-the-construct-message-shape"></a><span data-ttu-id="7374b-102">任务 4：配置构造消息形状</span><span class="sxs-lookup"><span data-stu-id="7374b-102">Task 4: Configure the Construct Message Shape</span></span>
<span data-ttu-id="7374b-103">构造消息包含消息赋值与 Begin、 Edit 和 End Doc 代码的说明。</span><span class="sxs-lookup"><span data-stu-id="7374b-103">The Construct Messages hold messages assignments with the instructions for the Begin, Edit, and End Doc code.</span></span>  
  
 <span data-ttu-id="7374b-104">使用以下过程配置构造消息形状。</span><span class="sxs-lookup"><span data-stu-id="7374b-104">Use the following procedure to configure the Construct Message shape.</span></span>  
  
### <a name="to-configure-the-construct-message-shape"></a><span data-ttu-id="7374b-105">若要配置构造消息形状</span><span class="sxs-lookup"><span data-stu-id="7374b-105">To configure the Construct Message shape</span></span>  
  
1. <span data-ttu-id="7374b-106">将构造消息形状在 receivebegindoc 和 sendbegindoc 之间。</span><span class="sxs-lookup"><span data-stu-id="7374b-106">Drag a Construct Message shape inbetween ReceiveBeginDoc and SendBeginDoc.</span></span>  
  
   -   <span data-ttu-id="7374b-107">**构造的消息：** BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="7374b-107">**Messages Constructed:** BeginDocSessionMsg</span></span>  
  
   -   <span data-ttu-id="7374b-108">**名称：** ConstructBeginDocMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="7374b-108">**Name:** ConstructBeginDocMessageWithSession</span></span>  
  
   1.  <span data-ttu-id="7374b-109">将消息赋值形状拖至业务流程你想要创建新的消息。</span><span class="sxs-lookup"><span data-stu-id="7374b-109">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
   2.  <span data-ttu-id="7374b-110">双击内部 MessageAssignment_1 形状。</span><span class="sxs-lookup"><span data-stu-id="7374b-110">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
        <span data-ttu-id="7374b-111">将显示 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="7374b-111">The BizTalk Expression Editor appears.</span></span>  
  
   3.  <span data-ttu-id="7374b-112">键入在代码中，例如：</span><span class="sxs-lookup"><span data-stu-id="7374b-112">Type in your code, for example:</span></span>  
  
   ```  
   BeginDocSessionMsg = BeginDocMsg;  
   BeginDocSessionMsg(JDE.ReserveSession) = true;  
   BeginDocSessionMsg(JDE.SessionID) = 0;  
   ```  
  
    <span data-ttu-id="7374b-113">这将告知适配器您想要启动会话。</span><span class="sxs-lookup"><span data-stu-id="7374b-113">This tells the adapter you want to start a session.</span></span> <span data-ttu-id="7374b-114">SessionID 初始化为 0，但当响应返回将由 J.D.分配 ID</span><span class="sxs-lookup"><span data-stu-id="7374b-114">The SessionID is initialized as 0 but when the response comes back the ID will be assigned by the J.D.</span></span> <span data-ttu-id="7374b-115">Edwards OneWorld 服务器。</span><span class="sxs-lookup"><span data-stu-id="7374b-115">Edwards OneWorld Server.</span></span>  
  
    <span data-ttu-id="7374b-116">![](../core/media/jde-message-expression-editor.gif "JDE_message_expression_editor")</span><span class="sxs-lookup"><span data-stu-id="7374b-116">![](../core/media/jde-message-expression-editor.gif "JDE_message_expression_editor")</span></span>  
  
2. <span data-ttu-id="7374b-117">将拖至 SendEditLine 之前构造消息。</span><span class="sxs-lookup"><span data-stu-id="7374b-117">Drag a Construct Message before SendEditLine.</span></span>  
  
   - <span data-ttu-id="7374b-118">**构造的消息：** EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="7374b-118">**Messages Constructed:** EditLineSessionMsg</span></span>  
  
   - <span data-ttu-id="7374b-119">**名称：** ConstructEditLineMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="7374b-119">**Name:** ConstructEditLineMessageWithSession</span></span>  
  
     <span data-ttu-id="7374b-120">![](../core/media/jde-constructoreditlinemessagewithsession.gif "JDE_constructoreditlinemessagewithsession")</span><span class="sxs-lookup"><span data-stu-id="7374b-120">![](../core/media/jde-constructoreditlinemessagewithsession.gif "JDE_constructoreditlinemessagewithsession")</span></span>  
  
   1.  <span data-ttu-id="7374b-121">将消息赋值形状拖至业务流程你想要创建新的消息。</span><span class="sxs-lookup"><span data-stu-id="7374b-121">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
   2.  <span data-ttu-id="7374b-122">双击内部 MessageAssignment_1 形状。</span><span class="sxs-lookup"><span data-stu-id="7374b-122">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
        <span data-ttu-id="7374b-123">将显示 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="7374b-123">The BizTalk Expression Editor appears.</span></span>  
  
   3.  <span data-ttu-id="7374b-124">键入在代码中，例如：</span><span class="sxs-lookup"><span data-stu-id="7374b-124">Type in your code, for example:</span></span>  
  
   ```  
   EditLineSessionMsg = EditLineMsg;  
   EditLineSessionMsg(JDE.ReserveSession) = true;  
   EditLineSessionMsg(JDE.SessionID) =  
      BeginDocResponseMsg(JDE.SessionID);  
   ```  
  
    <span data-ttu-id="7374b-125">![](../core/media/jde-editline-editor.gif "JDE_editline_editor")</span><span class="sxs-lookup"><span data-stu-id="7374b-125">![](../core/media/jde-editline-editor.gif "JDE_editline_editor")</span></span>  
  
3. <span data-ttu-id="7374b-126">将拖至 SendEndDoc 之前构造消息。</span><span class="sxs-lookup"><span data-stu-id="7374b-126">Drag a Construct Message before SendEndDoc.</span></span>  
  
   -   <span data-ttu-id="7374b-127">**构造的消息：** EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="7374b-127">**Messages Constructed:** EndDocSessionMsg</span></span>  
  
   -   <span data-ttu-id="7374b-128">**名称：** ConstructEndDocMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="7374b-128">**Name:** ConstructEndDocMessageWithSession</span></span>  
  
   1.  <span data-ttu-id="7374b-129">将消息赋值形状拖至业务流程你想要创建新的消息。</span><span class="sxs-lookup"><span data-stu-id="7374b-129">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
   2.  <span data-ttu-id="7374b-130">双击内部 MessageAssignment_1 形状。</span><span class="sxs-lookup"><span data-stu-id="7374b-130">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
        <span data-ttu-id="7374b-131">将显示 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="7374b-131">The BizTalk Expression Editor appears.</span></span>  
  
   3.  <span data-ttu-id="7374b-132">键入在代码中，例如：</span><span class="sxs-lookup"><span data-stu-id="7374b-132">Type in your code, for example:</span></span>  
  
   ```  
   EndDocSessionMsg = EndDocMsg;  
   EndDocSessionMsg(JDE.ReserveSession) = false;  
   EndDocSessionMsg(JDE.SessionID) =  
      BeginDocResponseMsg(JDE.SessionID);  
   ```  
  
## <a name="see-also"></a><span data-ttu-id="7374b-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="7374b-133">See Also</span></span>  
 <span data-ttu-id="7374b-134">[任务 1:创建端口](../core/task-1-create-the-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="7374b-134">[Task 1: Create the Ports](../core/task-1-create-the-ports2.md) </span></span>  
 <span data-ttu-id="7374b-135">[任务 2:创建消息](../core/task-2-create-the-messages1.md) </span><span class="sxs-lookup"><span data-stu-id="7374b-135">[Task 2: Create the Messages](../core/task-2-create-the-messages1.md) </span></span>  
 <span data-ttu-id="7374b-136">[任务 3:配置发送和接收形状](../core/task-3-configure-the-send-and-receive-shapes1.md) </span><span class="sxs-lookup"><span data-stu-id="7374b-136">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes1.md) </span></span>  
 [<span data-ttu-id="7374b-137">任务 5:配置转换形状</span><span class="sxs-lookup"><span data-stu-id="7374b-137">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape1.md)