---
title: 任务 4： 配置构造消息形状 2 |Microsoft 文档
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
ms.openlocfilehash: 6616fec48eb0915527a95f94992e4bda838e9d37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279037"
---
# <a name="task-4-configure-the-construct-message-shape"></a><span data-ttu-id="e0872-102">任务 4： 配置构造消息形状</span><span class="sxs-lookup"><span data-stu-id="e0872-102">Task 4: Configure the Construct Message Shape</span></span>
<span data-ttu-id="e0872-103">构造消息将消息赋值与 Begin、Edit 和 End Doc 代码的指令保存在一起。</span><span class="sxs-lookup"><span data-stu-id="e0872-103">The Construct Messages hold messages assignments with the instructions for the Begin, Edit, and End Doc code.</span></span>  
  
 <span data-ttu-id="e0872-104">使用以下过程配置构造消息形状。</span><span class="sxs-lookup"><span data-stu-id="e0872-104">Use the following procedure to configure the Construct Message shape.</span></span>  
  
### <a name="to-configure-the-construct-message-shape"></a><span data-ttu-id="e0872-105">若要配置构造消息形状</span><span class="sxs-lookup"><span data-stu-id="e0872-105">To configure the Construct Message shape</span></span>  
  
1.  <span data-ttu-id="e0872-106">在 ReceiveBeginDoc 和 SendBeginDoc 之间拖动构造消息形状。</span><span class="sxs-lookup"><span data-stu-id="e0872-106">Drag a Construct Message shape inbetween ReceiveBeginDoc and SendBeginDoc.</span></span>  
  
    -   <span data-ttu-id="e0872-107">**构造的消息：** BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="e0872-107">**Messages Constructed:** BeginDocSessionMsg</span></span>  
  
    -   <span data-ttu-id="e0872-108">**名称：** ConstructBeginDocMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="e0872-108">**Name:** ConstructBeginDocMessageWithSession</span></span>  
  
    1.  <span data-ttu-id="e0872-109">将消息赋值形状拖入要在其中创建新消息的业务流程中。</span><span class="sxs-lookup"><span data-stu-id="e0872-109">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
    2.  <span data-ttu-id="e0872-110">双击内部 MessageAssignment_1 形状。</span><span class="sxs-lookup"><span data-stu-id="e0872-110">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
         <span data-ttu-id="e0872-111">随即将显示 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="e0872-111">The BizTalk Expression Editor appears.</span></span>  
  
    3.  <span data-ttu-id="e0872-112">键入代码，例如：</span><span class="sxs-lookup"><span data-stu-id="e0872-112">Type in your code, for example:</span></span>  
  
    ```  
    BeginDocSessionMsg = BeginDocMsg;  
    BeginDocSessionMsg(JDE.ReserveSession) = true;  
    BeginDocSessionMsg(JDE.SessionID) = 0;  
    ```  
  
     <span data-ttu-id="e0872-113">此操作将告知适配器您要启动一个会话。</span><span class="sxs-lookup"><span data-stu-id="e0872-113">This tells the adapter you want to start a session.</span></span> <span data-ttu-id="e0872-114">SessionID 初始化为 0，但 J.D.回响应时将分配的 ID</span><span class="sxs-lookup"><span data-stu-id="e0872-114">The SessionID is initialized as 0 but when the response comes back the ID will be assigned by the J.D.</span></span> <span data-ttu-id="e0872-115">Edwards OneWorld 服务器。</span><span class="sxs-lookup"><span data-stu-id="e0872-115">Edwards OneWorld Server.</span></span>  
  
     ![](../core/media/jde-message-expression-editor.gif "JDE_message_expression_editor")  
  
2.  <span data-ttu-id="e0872-116">将构造消息拖至 SendEditLine 之前。</span><span class="sxs-lookup"><span data-stu-id="e0872-116">Drag a Construct Message before SendEditLine.</span></span>  
  
    -   <span data-ttu-id="e0872-117">**构造的消息：** EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="e0872-117">**Messages Constructed:** EditLineSessionMsg</span></span>  
  
    -   <span data-ttu-id="e0872-118">**名称：** ConstructEditLineMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="e0872-118">**Name:** ConstructEditLineMessageWithSession</span></span>  
  
     ![](../core/media/jde-constructoreditlinemessagewithsession.gif "JDE_constructoreditlinemessagewithsession")  
  
    1.  <span data-ttu-id="e0872-119">将消息赋值形状拖入要在其中创建新消息的业务流程中。</span><span class="sxs-lookup"><span data-stu-id="e0872-119">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
    2.  <span data-ttu-id="e0872-120">双击内部 MessageAssignment_1 形状。</span><span class="sxs-lookup"><span data-stu-id="e0872-120">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
         <span data-ttu-id="e0872-121">随即将显示 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="e0872-121">The BizTalk Expression Editor appears.</span></span>  
  
    3.  <span data-ttu-id="e0872-122">键入代码，例如：</span><span class="sxs-lookup"><span data-stu-id="e0872-122">Type in your code, for example:</span></span>  
  
    ```  
    EditLineSessionMsg = EditLineMsg;  
    EditLineSessionMsg(JDE.ReserveSession) = true;  
    EditLineSessionMsg(JDE.SessionID) =  
       BeginDocResponseMsg(JDE.SessionID);  
    ```  
  
     ![](../core/media/jde-editline-editor.gif "JDE_editline_editor")  
  
3.  <span data-ttu-id="e0872-123">将构造消息拖至 SendEndDoc 之前。</span><span class="sxs-lookup"><span data-stu-id="e0872-123">Drag a Construct Message before SendEndDoc.</span></span>  
  
    -   <span data-ttu-id="e0872-124">**构造的消息：** EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="e0872-124">**Messages Constructed:** EndDocSessionMsg</span></span>  
  
    -   <span data-ttu-id="e0872-125">**名称：** ConstructEndDocMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="e0872-125">**Name:** ConstructEndDocMessageWithSession</span></span>  
  
    1.  <span data-ttu-id="e0872-126">将消息赋值形状拖入要在其中创建新消息的业务流程中。</span><span class="sxs-lookup"><span data-stu-id="e0872-126">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
    2.  <span data-ttu-id="e0872-127">双击内部 MessageAssignment_1 形状。</span><span class="sxs-lookup"><span data-stu-id="e0872-127">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
         <span data-ttu-id="e0872-128">随即将显示 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="e0872-128">The BizTalk Expression Editor appears.</span></span>  
  
    3.  <span data-ttu-id="e0872-129">键入代码，例如：</span><span class="sxs-lookup"><span data-stu-id="e0872-129">Type in your code, for example:</span></span>  
  
    ```  
    EndDocSessionMsg = EndDocMsg;  
    EndDocSessionMsg(JDE.ReserveSession) = false;  
    EndDocSessionMsg(JDE.SessionID) =  
       BeginDocResponseMsg(JDE.SessionID);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e0872-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0872-130">See Also</span></span>  
 <span data-ttu-id="e0872-131">[任务 1： 创建端口](../core/task-1-create-the-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="e0872-131">[Task 1: Create the Ports](../core/task-1-create-the-ports2.md) </span></span>  
 <span data-ttu-id="e0872-132">[任务 2： 创建消息](../core/task-2-create-the-messages1.md) </span><span class="sxs-lookup"><span data-stu-id="e0872-132">[Task 2: Create the Messages](../core/task-2-create-the-messages1.md) </span></span>  
 <span data-ttu-id="e0872-133">[任务 3： 配置发送和接收形状](../core/task-3-configure-the-send-and-receive-shapes1.md) </span><span class="sxs-lookup"><span data-stu-id="e0872-133">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes1.md) </span></span>  
 [<span data-ttu-id="e0872-134">任务 5： 配置转换形状</span><span class="sxs-lookup"><span data-stu-id="e0872-134">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape1.md)