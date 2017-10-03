---
title: "任务 4： 配置构造消息 Shape1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3e66a9d-c549-42d0-849b-9e1744056429
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f781e03f83223f7d82628ee9c01728a0754b149f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="task-4-configure-the-construct-message-shape"></a><span data-ttu-id="18dab-102">任务 4： 配置构造消息形状</span><span class="sxs-lookup"><span data-stu-id="18dab-102">Task 4: Configure the Construct Message Shape</span></span>
<span data-ttu-id="18dab-103">构造消息将消息赋值与 Begin、Edit 和 End Doc 代码的指令保存在一起。</span><span class="sxs-lookup"><span data-stu-id="18dab-103">The Construct Messages hold messages assignments with the instructions for the Begin, Edit, and End Doc code.</span></span>  
  
 <span data-ttu-id="18dab-104">使用以下过程配置构造消息形状。</span><span class="sxs-lookup"><span data-stu-id="18dab-104">Use the following procedure to configure the Construct Message shape.</span></span>  
  
### <a name="to-configure-the-construct-message-shape"></a><span data-ttu-id="18dab-105">若要配置构造消息形状</span><span class="sxs-lookup"><span data-stu-id="18dab-105">To configure the Construct Message shape</span></span>  
  
1.  <span data-ttu-id="18dab-106">在 ReceiveBeginDoc 和 SendBeginDoc 之间拖动构造消息形状。</span><span class="sxs-lookup"><span data-stu-id="18dab-106">Drag a Construct Message shape inbetween ReceiveBeginDoc and SendBeginDoc.</span></span>  
  
    -   <span data-ttu-id="18dab-107">**构造的消息：** BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="18dab-107">**Messages Constructed:** BeginDocSessionMsg</span></span>  
  
    -   <span data-ttu-id="18dab-108">**名称：** ConstructBeginDocMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="18dab-108">**Name:** ConstructBeginDocMessageWithSession</span></span>  
  
    1.  <span data-ttu-id="18dab-109">将消息赋值形状拖入要在其中创建新消息的业务流程中。</span><span class="sxs-lookup"><span data-stu-id="18dab-109">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
    2.  <span data-ttu-id="18dab-110">双击内部 MessageAssignment_1 形状。</span><span class="sxs-lookup"><span data-stu-id="18dab-110">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
         <span data-ttu-id="18dab-111">随即将显示 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="18dab-111">The BizTalk Expression Editor appears.</span></span>  
  
    3.  <span data-ttu-id="18dab-112">键入代码，例如：</span><span class="sxs-lookup"><span data-stu-id="18dab-112">Type in your code, for example:</span></span>  
  
        ```  
        BeginDocSessionMsg = BeginDocMsg;  
        BeginDocSessionMsg(JDE.ReserveSession) = true;  
        BeginDocSessionMsg(JDE.SessionID) = 0;  
        ```  
  
         <span data-ttu-id="18dab-113">此操作将告知适配器您要启动一个会话。</span><span class="sxs-lookup"><span data-stu-id="18dab-113">This tells the adapter you want to start a session.</span></span> <span data-ttu-id="18dab-114">SessionID 初始化为 0，但 J.D.回响应时将分配的 ID</span><span class="sxs-lookup"><span data-stu-id="18dab-114">The SessionID is initialized as 0 but when the response comes back the ID will be assigned by the J.D.</span></span> <span data-ttu-id="18dab-115">Edwards EnterpriseOne 服务器。</span><span class="sxs-lookup"><span data-stu-id="18dab-115">Edwards EnterpriseOne Server.</span></span>  
  
     <span data-ttu-id="18dab-116">![消息表达式编辑器](../core/media/message-expression-editor.gif "message_expression_editor")</span><span class="sxs-lookup"><span data-stu-id="18dab-116">![Message Expression Editor](../core/media/message-expression-editor.gif "message_expression_editor")</span></span>  
  
2.  <span data-ttu-id="18dab-117">将构造消息拖至 SendEditLine 之前。</span><span class="sxs-lookup"><span data-stu-id="18dab-117">Drag a Construct Message before SendEditLine.</span></span>  
  
    -   <span data-ttu-id="18dab-118">**构造的消息：** EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="18dab-118">**Messages Constructed:** EditLineSessionMsg</span></span>  
  
    -   <span data-ttu-id="18dab-119">**名称：** ConstructEditLineMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="18dab-119">**Name:** ConstructEditLineMessageWithSession</span></span>  
  
     <span data-ttu-id="18dab-120">![发送编辑行](../core/media/constructoreditlinemessagewithsession.gif "constructoreditlinemessagewithsession")</span><span class="sxs-lookup"><span data-stu-id="18dab-120">![Send Edit Line](../core/media/constructoreditlinemessagewithsession.gif "constructoreditlinemessagewithsession")</span></span>  
  
    1.  <span data-ttu-id="18dab-121">将消息赋值形状拖入要在其中创建新消息的业务流程中。</span><span class="sxs-lookup"><span data-stu-id="18dab-121">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
    2.  <span data-ttu-id="18dab-122">双击内部 MessageAssignment_1 形状。</span><span class="sxs-lookup"><span data-stu-id="18dab-122">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
         <span data-ttu-id="18dab-123">随即将显示 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="18dab-123">The BizTalk Expression Editor appears.</span></span>  
  
    3.  <span data-ttu-id="18dab-124">键入代码，例如：</span><span class="sxs-lookup"><span data-stu-id="18dab-124">Type in your code, for example:</span></span>  
  
        ```  
        EditLineSessionMsg = EditLineMsg;  
        EditLineSessionMsg(JDE.ReserveSession) = true;  
        EditLineSessionMsg(JDE.SessionID) =  
        BeginDocResponseMsg(JDE.SessionID);  
        ```  
  
     <span data-ttu-id="18dab-125">![编辑行编辑器](../core/media/editline-editor.gif "editline_editor")</span><span class="sxs-lookup"><span data-stu-id="18dab-125">![Edit Line Editor](../core/media/editline-editor.gif "editline_editor")</span></span>  
  
3.  <span data-ttu-id="18dab-126">将构造消息形状拖至 SendEndDoc 之前。</span><span class="sxs-lookup"><span data-stu-id="18dab-126">Drag a Construct Message shape before SendEndDoc.</span></span>  
  
    -   <span data-ttu-id="18dab-127">**构造的消息：** EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="18dab-127">**Messages Constructed:** EndDocSessionMsg</span></span>  
  
    -   <span data-ttu-id="18dab-128">**名称：** ConstructEndDocMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="18dab-128">**Name:** ConstructEndDocMessageWithSession</span></span>  
  
    1.  <span data-ttu-id="18dab-129">将消息赋值形状拖入要在其中创建新消息的业务流程中。</span><span class="sxs-lookup"><span data-stu-id="18dab-129">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
    2.  <span data-ttu-id="18dab-130">双击内部 MessageAssignment_1 形状。</span><span class="sxs-lookup"><span data-stu-id="18dab-130">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
         <span data-ttu-id="18dab-131">随即将显示 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="18dab-131">The BizTalk Expression Editor appears.</span></span>  
  
    3.  <span data-ttu-id="18dab-132">键入代码，例如：</span><span class="sxs-lookup"><span data-stu-id="18dab-132">Type in your code, for example:</span></span>  
  
        ```  
        EndDocSessionMsg = EndDocMsg;  
        EndDocSessionMsg(JDE.ReserveSession) = false;  
        EndDocSessionMsg(JDE.SessionID) =  
           BeginDocResponseMsg(JDE.SessionID);  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="18dab-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18dab-133">See Also</span></span>  
 <span data-ttu-id="18dab-134">[任务 1： 创建端口](../core/task-1-create-the-ports1.md) </span><span class="sxs-lookup"><span data-stu-id="18dab-134">[Task 1: Create the Ports](../core/task-1-create-the-ports1.md) </span></span>  
 <span data-ttu-id="18dab-135">[任务 2： 创建消息](../core/task-2-create-the-messages2.md) </span><span class="sxs-lookup"><span data-stu-id="18dab-135">[Task 2: Create the Messages](../core/task-2-create-the-messages2.md) </span></span>  
 <span data-ttu-id="18dab-136">[任务 3： 配置发送和接收形状](../core/task-3-configure-the-send-and-receive-shapes2.md) </span><span class="sxs-lookup"><span data-stu-id="18dab-136">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes2.md) </span></span>  
 [<span data-ttu-id="18dab-137">任务 5： 配置转换形状</span><span class="sxs-lookup"><span data-stu-id="18dab-137">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape2.md)