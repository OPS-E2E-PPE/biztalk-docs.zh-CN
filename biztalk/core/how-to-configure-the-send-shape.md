---
title: 如何配置发送形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Send shape [Orchestration Designer], delivery notification
- send ports, delivery notifications
- configuring [Orchestration Designer], Send shapes
- Send shape [Orchestration Designer], configuring
- delivery notification
- messages, delivery notification
ms.assetid: 2cf4755b-1cfc-484e-bd9c-c9f3855af556
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbfedd5067be1de443c20ce522cbe30f27395db1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989958"
---
# <a name="how-to-configure-the-send-shape"></a><span data-ttu-id="f3f72-102">如何配置发送形状</span><span class="sxs-lookup"><span data-stu-id="f3f72-102">How to Configure the Send Shape</span></span>
<span data-ttu-id="f3f72-103">![](../core/media/ebiz-orch-send.gif "ebiz_orch_send")</span><span class="sxs-lookup"><span data-stu-id="f3f72-103">![](../core/media/ebiz-orch-send.gif "ebiz_orch_send")</span></span>  
<span data-ttu-id="f3f72-104">发送形状</span><span class="sxs-lookup"><span data-stu-id="f3f72-104">Send shape</span></span>  
  
 <span data-ttu-id="f3f72-105">对于已发送的消息，如果希望接收到间接或异步响应（不使用请求-响应端口），则需要将该消息与当前正在运行的业务流程实例相关联，以便响应者可以获得对正确实例的响应。</span><span class="sxs-lookup"><span data-stu-id="f3f72-105">If you expect to receive an indirect or asynchronous response (not using a request-response port) to the message that you have sent, you need to correlate the message with the currently running instance of the orchestration, so that the respondent can get the response to the correct instance.</span></span> <span data-ttu-id="f3f72-106">您可以应用沿用相关集**发送**形状以前初始化的相关，或者你可以应用初始化相关集。</span><span class="sxs-lookup"><span data-stu-id="f3f72-106">You can apply a following correlation set to the **Send** shape for a previously initialized correlation, or you can apply an initializing correlation set.</span></span> <span data-ttu-id="f3f72-107">有关详细信息，请参阅[业务流程中使用相关性](../core/using-correlations-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="f3f72-107">For more information, see [Using Correlations in Orchestrations](../core/using-correlations-in-orchestrations.md).</span></span>  
  
### <a name="to-configure-a-send-shape"></a><span data-ttu-id="f3f72-108">配置发送形状</span><span class="sxs-lookup"><span data-stu-id="f3f72-108">To configure a Send shape</span></span>  
  
1.  <span data-ttu-id="f3f72-109">设置消息和端口操作。</span><span class="sxs-lookup"><span data-stu-id="f3f72-109">Set a message and a port operation.</span></span>  
  
    1.  <span data-ttu-id="f3f72-110">在“业务流程视图”窗口中，确认您的业务流程具有消息以及为要发送的多部分消息类型定义的端口操作。</span><span class="sxs-lookup"><span data-stu-id="f3f72-110">In the Orchestration View window, verify that your orchestration has both a message and a port operation defined for the multi-part message type being sent.</span></span>  
  
    2.  <span data-ttu-id="f3f72-111">在属性窗口中，选择要从发送的消息**消息**属性下拉列表。</span><span class="sxs-lookup"><span data-stu-id="f3f72-111">In the Properties window, select the message to send from the **Message** property drop-down list.</span></span>  
  
    3.  <span data-ttu-id="f3f72-112">在属性窗口中，选择将消息从发送端口操作**端口操作**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="f3f72-112">In the Properties window, select the port operation that sends the message from the **Port Operation** drop-down list.</span></span>  
  
         <span data-ttu-id="f3f72-113">-或-</span><span class="sxs-lookup"><span data-stu-id="f3f72-113">—Or—</span></span>  
  
         <span data-ttu-id="f3f72-114">将从发送连接器拖**发送**发送消息的端口套接字的形状。</span><span class="sxs-lookup"><span data-stu-id="f3f72-114">Drag the send connector from the **Send** shape to the port socket that sends the message.</span></span>  
  
2.  <span data-ttu-id="f3f72-115">指定相关集来限制的消息**发送**将发送形状或初始化相关集中的值。</span><span class="sxs-lookup"><span data-stu-id="f3f72-115">Specify correlation sets to restrict the messages the **Send** shape will send or to initialize the values in a correlation set.</span></span>  
  
    1.  <span data-ttu-id="f3f72-116">你想要使用每个相关集，请检查该相关集从下拉列表**沿用相关集**属性。</span><span class="sxs-lookup"><span data-stu-id="f3f72-116">For each correlation set you want to use, check a correlation set from the drop-down on the **Following Correlation Sets** property.</span></span>  
  
    2.  <span data-ttu-id="f3f72-117">有关每个相关集要用于初始化，检查该相关集从下拉列表**初始化相关集**属性。</span><span class="sxs-lookup"><span data-stu-id="f3f72-117">For each correlation set that you want to initialize, check a correlation set from the drop-down on the **Initializing Correlation Sets** property.</span></span>  
  
## <a name="delivery-notification"></a><span data-ttu-id="f3f72-118">送达通知</span><span class="sxs-lookup"><span data-stu-id="f3f72-118">Delivery Notification</span></span>  
 <span data-ttu-id="f3f72-119">若要测试是否成功通过发送端口发送了某一消息，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f3f72-119">To test whether you have successfully sent a message over a send port, complete the following steps:</span></span>  
  
1. <span data-ttu-id="f3f72-120">将发送形状放置于非事务性、长期或原子作用域中。</span><span class="sxs-lookup"><span data-stu-id="f3f72-120">Put your Send shape in a non-transactional, long-running or atomic scope.</span></span>  
  
2. <span data-ttu-id="f3f72-121">在您的发送端口，将 DeliveryNotification 属性设置为**传输**。</span><span class="sxs-lookup"><span data-stu-id="f3f72-121">On your send port, set the DeliveryNotification property to **Transmitted**.</span></span>  
  
3. <span data-ttu-id="f3f72-122">将某一 catch 处理程序添加到您的作用域中，以便处理 DeliveryFailureException。</span><span class="sxs-lookup"><span data-stu-id="f3f72-122">Add a catch handler to your scope to handle a DeliveryFailureException.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f3f72-123">如果发送形状包含在原子作用域中，将 DeliveryFailureException 仍可以捕获，但需要在外部作用域形状添加事务类型设置为**长期**或**None**.</span><span class="sxs-lookup"><span data-stu-id="f3f72-123">If the Send shape is contained within an atomic scope, the DeliveryFailureException can still be caught, but will require an outer scope shape be added with a Transaction Type set to **Long Running** or **None**.</span></span> <span data-ttu-id="f3f72-124">原子作用域不能直接捕获异常。</span><span class="sxs-lookup"><span data-stu-id="f3f72-124">Atomic scopes are not able to catch exceptions directly.</span></span>  
  
   <span data-ttu-id="f3f72-125">业务流程等待封闭式非原子作用域结束时（或业务流程结束时）的确认，以便接收该确认。</span><span class="sxs-lookup"><span data-stu-id="f3f72-125">The orchestration waits for acknowledgment at the end of the enclosing non-atomic scope, or the end of the orchestration, to receive the acknowledgment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3f72-126">这只适用于单向操作；双向（请求-响应）操作中的失败将导致 SoapException（否定确认），即使未设置端口属性时也是如此。</span><span class="sxs-lookup"><span data-stu-id="f3f72-126">This applies only to one-way operations; failure in two-way (request-response) operations results in a SoapException (negative acknowledgement) even without the port attribute being set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3f72-127">对于直接绑定，不支持送达通知。</span><span class="sxs-lookup"><span data-stu-id="f3f72-127">Delivery notification is not supported for direct binding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3f72-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="f3f72-128">See Also</span></span>  
 [<span data-ttu-id="f3f72-129">错误处理</span><span class="sxs-lookup"><span data-stu-id="f3f72-129">Error Handling</span></span>](../core/error-handling.md)