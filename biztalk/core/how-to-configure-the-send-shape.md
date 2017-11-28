---
title: "如何配置发送形状 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Send shape [Orchestration Designer], delivery notification
- send ports, delivery notifications
- configuring [Orchestration Designer], Send shapes
- Send shape [Orchestration Designer], configuring
- delivery notification
- messages, delivery notification
ms.assetid: 2cf4755b-1cfc-484e-bd9c-c9f3855af556
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c32711b841b915d793e5c8a22ffe9513e2ec28d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-send-shape"></a><span data-ttu-id="c0cef-102">如何配置发送形状</span><span class="sxs-lookup"><span data-stu-id="c0cef-102">How to Configure the Send Shape</span></span>
![](../core/media/ebiz-orch-send.gif "ebiz_orch_send")  
<span data-ttu-id="c0cef-103">发送形状</span><span class="sxs-lookup"><span data-stu-id="c0cef-103">Send shape</span></span>  
  
 <span data-ttu-id="c0cef-104">对于已发送的消息，如果希望接收到间接或异步响应（不使用请求-响应端口），则需要将该消息与当前正在运行的业务流程实例相关联，以便响应者可以获得对正确实例的响应。</span><span class="sxs-lookup"><span data-stu-id="c0cef-104">If you expect to receive an indirect or asynchronous response (not using a request-response port) to the message that you have sent, you need to correlate the message with the currently running instance of the orchestration, so that the respondent can get the response to the correct instance.</span></span> <span data-ttu-id="c0cef-105">你可以将应用设置为以下相关**发送**形状以前初始化的相关，或者你可以将应用初始化相关集。</span><span class="sxs-lookup"><span data-stu-id="c0cef-105">You can apply a following correlation set to the **Send** shape for a previously initialized correlation, or you can apply an initializing correlation set.</span></span> <span data-ttu-id="c0cef-106">有关详细信息，请参阅[在业务流程中使用相关性](../core/using-correlations-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="c0cef-106">For more information, see [Using Correlations in Orchestrations](../core/using-correlations-in-orchestrations.md).</span></span>  
  
### <a name="to-configure-a-send-shape"></a><span data-ttu-id="c0cef-107">配置发送形状</span><span class="sxs-lookup"><span data-stu-id="c0cef-107">To configure a Send shape</span></span>  
  
1.  <span data-ttu-id="c0cef-108">设置消息和端口操作。</span><span class="sxs-lookup"><span data-stu-id="c0cef-108">Set a message and a port operation.</span></span>  
  
    1.  <span data-ttu-id="c0cef-109">在“业务流程视图”窗口中，确认您的业务流程具有消息以及为要发送的多部分消息类型定义的端口操作。</span><span class="sxs-lookup"><span data-stu-id="c0cef-109">In the Orchestration View window, verify that your orchestration has both a message and a port operation defined for the multi-part message type being sent.</span></span>  
  
    2.  <span data-ttu-id="c0cef-110">在属性窗口中，选择要从发送的消息**消息**属性下拉列表。</span><span class="sxs-lookup"><span data-stu-id="c0cef-110">In the Properties window, select the message to send from the **Message** property drop-down list.</span></span>  
  
    3.  <span data-ttu-id="c0cef-111">在属性窗口中，选择将从消息发送的端口操作**端口操作**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="c0cef-111">In the Properties window, select the port operation that sends the message from the **Port Operation** drop-down list.</span></span>  
  
         <span data-ttu-id="c0cef-112">-或者-</span><span class="sxs-lookup"><span data-stu-id="c0cef-112">—Or—</span></span>  
  
         <span data-ttu-id="c0cef-113">将从发送连接线**发送**于端口套接字的发送消息的形状。</span><span class="sxs-lookup"><span data-stu-id="c0cef-113">Drag the send connector from the **Send** shape to the port socket that sends the message.</span></span>  
  
2.  <span data-ttu-id="c0cef-114">指定相关设置来限制的消息**发送**形状将发送或初始化相关集内的值。</span><span class="sxs-lookup"><span data-stu-id="c0cef-114">Specify correlation sets to restrict the messages the **Send** shape will send or to initialize the values in a correlation set.</span></span>  
  
    1.  <span data-ttu-id="c0cef-115">你想要使用每个关联集，请检查关联集从下拉列表上**以下相关集**属性。</span><span class="sxs-lookup"><span data-stu-id="c0cef-115">For each correlation set you want to use, check a correlation set from the drop-down on the **Following Correlation Sets** property.</span></span>  
  
    2.  <span data-ttu-id="c0cef-116">每个相关设置你想要初始化，请从下拉列表设置上一个相关性**初始化关联集**属性。</span><span class="sxs-lookup"><span data-stu-id="c0cef-116">For each correlation set that you want to initialize, check a correlation set from the drop-down on the **Initializing Correlation Sets** property.</span></span>  
  
## <a name="delivery-notification"></a><span data-ttu-id="c0cef-117">传递通知</span><span class="sxs-lookup"><span data-stu-id="c0cef-117">Delivery Notification</span></span>  
 <span data-ttu-id="c0cef-118">若要测试是否成功通过发送端口发送了某一消息，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c0cef-118">To test whether you have successfully sent a message over a send port, complete the following steps:</span></span>  
  
1.  <span data-ttu-id="c0cef-119">将发送形状放置于非事务性、长期或原子作用域中。</span><span class="sxs-lookup"><span data-stu-id="c0cef-119">Put your Send shape in a non-transactional, long-running or atomic scope.</span></span>  
  
2.  <span data-ttu-id="c0cef-120">在你发送端口，将 DeliveryNotification 属性设置为**传输**。</span><span class="sxs-lookup"><span data-stu-id="c0cef-120">On your send port, set the DeliveryNotification property to **Transmitted**.</span></span>  
  
3.  <span data-ttu-id="c0cef-121">将某一 catch 处理程序添加到您的作用域中，以便处理 DeliveryFailureException。</span><span class="sxs-lookup"><span data-stu-id="c0cef-121">Add a catch handler to your scope to handle a DeliveryFailureException.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c0cef-122">如果发送形状包含在原子作用域内，DeliveryFailureException 仍可捕获，但是它将需要是外部范围形状添加事务类型设置为**运行长时间**或**无**.</span><span class="sxs-lookup"><span data-stu-id="c0cef-122">If the Send shape is contained within an atomic scope, the DeliveryFailureException can still be caught, but will require an outer scope shape be added with a Transaction Type set to **Long Running** or **None**.</span></span> <span data-ttu-id="c0cef-123">原子作用域不能直接捕获异常。</span><span class="sxs-lookup"><span data-stu-id="c0cef-123">Atomic scopes are not able to catch exceptions directly.</span></span>  
  
 <span data-ttu-id="c0cef-124">业务流程等待封闭式非原子作用域结束时（或业务流程结束时）的确认，以便接收该确认。</span><span class="sxs-lookup"><span data-stu-id="c0cef-124">The orchestration waits for acknowledgment at the end of the enclosing non-atomic scope, or the end of the orchestration, to receive the acknowledgment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0cef-125">这只适用于单向操作；双向（请求-响应）操作中的失败将导致 SoapException（否定确认），即使未设置端口属性时也是如此。</span><span class="sxs-lookup"><span data-stu-id="c0cef-125">This applies only to one-way operations; failure in two-way (request-response) operations results in a SoapException (negative acknowledgement) even without the port attribute being set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0cef-126">对于直接绑定，不支持送达通知。</span><span class="sxs-lookup"><span data-stu-id="c0cef-126">Delivery notification is not supported for direct binding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0cef-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0cef-127">See Also</span></span>  
 [<span data-ttu-id="c0cef-128">错误处理</span><span class="sxs-lookup"><span data-stu-id="c0cef-128">Error Handling</span></span>](../core/error-handling.md)