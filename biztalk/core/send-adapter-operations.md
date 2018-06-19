---
title: 发送适配器操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf4e0430-e3dc-4884-8411-bbcb579bd21e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 444cf4ab7958b0d44838a8331b4b9e6a467baedc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270917"
---
# <a name="send-adapter-operations"></a><span data-ttu-id="f180a-102">发送适配器操作</span><span class="sxs-lookup"><span data-stu-id="f180a-102">Send Adapter Operations</span></span>
<span data-ttu-id="f180a-103">发送适配器可执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f180a-103">Send adapters can perform the following operations:</span></span>  
  
-   <span data-ttu-id="f180a-104">**重新提交： void Resubmit （IBaseMessage msg，DateTime timeStamp）。**</span><span class="sxs-lookup"><span data-stu-id="f180a-104">**Resubmit: void Resubmit(IBaseMessage msg, DateTime timeStamp).**</span></span> <span data-ttu-id="f180a-105">消息发生传输失败后，适配器会在适当的时候重新提交消息。</span><span class="sxs-lookup"><span data-stu-id="f180a-105">After a transmission failure occurs on a message, an adapter resubmits it when appropriate.</span></span> <span data-ttu-id="f180a-106">该操作对每条消息调用一次。</span><span class="sxs-lookup"><span data-stu-id="f180a-106">This is called on a per-message basis.</span></span> <span data-ttu-id="f180a-107">如果已成功提交一批消息，适配器必须确定导致该错误的消息，并重新提交到单独的调用中不会导致批处理失败的**重新提交**。</span><span class="sxs-lookup"><span data-stu-id="f180a-107">If a batch of messages was submitted unsuccessfully, the adapter must determine the messages causing the failure, and resubmit the ones that did not cause the batch to fail in separate calls to **Resubmit**.</span></span> <span data-ttu-id="f180a-108">没有在本主题末尾若要了解如何在调用时保留消息上下文属性值**重新提交**。</span><span class="sxs-lookup"><span data-stu-id="f180a-108">There is information at the end of this topic about how to preserve message context property values when you call **Resubmit**.</span></span>  
  
-   <span data-ttu-id="f180a-109">**将移动到下一个传输： void MoveToNextTransport (IBaseMessage msg)。**</span><span class="sxs-lookup"><span data-stu-id="f180a-109">**Move to Next Transport: void MoveToNextTransport(IBaseMessage msg).**</span></span> <span data-ttu-id="f180a-110">如果某个消息在发送操作中失败，并已重试了允许的最大尝试次数，则适配器会将该消息发送到配置的下一次传输，以便重新传输。</span><span class="sxs-lookup"><span data-stu-id="f180a-110">If a message fails during a send operation and its retry attempts have been exhausted, the adapter can send the message to the next configured transport for retransmission.</span></span>  
  
-   <span data-ttu-id="f180a-111">**挂起： void MoveToSuspendQ (IBaseMessage msg)。**</span><span class="sxs-lookup"><span data-stu-id="f180a-111">**Suspend: void MoveToSuspendQ(IBaseMessage msg).**</span></span> <span data-ttu-id="f180a-112">如果未配置其他备份传输，则适配器会将失败的发送消息移至挂起队列。</span><span class="sxs-lookup"><span data-stu-id="f180a-112">The adapter moves a failed send message to the Suspended queue if no additional backup transport is configured.</span></span> <span data-ttu-id="f180a-113">没有在本主题末尾若要了解如何在调用时保留消息上下文属性值**挂起**。</span><span class="sxs-lookup"><span data-stu-id="f180a-113">There is information at the end of this topic about how to preserve message context property values when you call **Suspend**.</span></span>  
  
-   <span data-ttu-id="f180a-114">**删除： void DeleteMessage (IBaseMessage msg)。**</span><span class="sxs-lookup"><span data-stu-id="f180a-114">**Delete: void DeleteMessage(IBaseMessage msg).**</span></span> <span data-ttu-id="f180a-115">收到 BizTalk Server 关于消息传输成功的通知后，适配器会删除该消息。</span><span class="sxs-lookup"><span data-stu-id="f180a-115">The adapter deletes a message after being notified by BizTalk Server of its successful transmission.</span></span> <span data-ttu-id="f180a-116">删除消息的操作会通知 BizTalk Server 适配器已完成处理该消息。</span><span class="sxs-lookup"><span data-stu-id="f180a-116">Deleting a message tells BizTalk Server that the adapter is finished with the message.</span></span> <span data-ttu-id="f180a-117">通常**SubmitResponse**操作在其关联，因此同一批中完成**删除**操作。</span><span class="sxs-lookup"><span data-stu-id="f180a-117">Generally the **SubmitResponse** operation is done in the same batch as its associated **Delete** operation.</span></span>  
  
-   <span data-ttu-id="f180a-118">**提交响应： void SubmitResponseMessage （IBaseMessage solicitMsgSent，IBaseMessage responseMsgToSubmit）。**</span><span class="sxs-lookup"><span data-stu-id="f180a-118">**Submit Response: void SubmitResponseMessage(IBaseMessage solicitMsgSent, IBaseMessage responseMsgToSubmit).**</span></span> <span data-ttu-id="f180a-119">适配器向要发回至 BizTalk Server 的批提交响应。</span><span class="sxs-lookup"><span data-stu-id="f180a-119">The adapter submits a response to the batch to be sent back to BizTalk Server.</span></span> <span data-ttu-id="f180a-120">此操作在调用中包括原始消息以及响应，以便 BizTalk Server 可以将它们关联起来。</span><span class="sxs-lookup"><span data-stu-id="f180a-120">This operation includes the original message in the call along with the response so that BizTalk Server can correlate them.</span></span>  
  
-   <span data-ttu-id="f180a-121">**取消响应： void 的 CancelResponseMessages (string correlationToken)。**</span><span class="sxs-lookup"><span data-stu-id="f180a-121">**Cancel Response: void CancelResponseMessages(string correlationToken).**</span></span> <span data-ttu-id="f180a-122">如果发送响应消息需要之前提交批语句后，会取消**CancelResponseMessages**方法使用中，并传入要删除关联的响应消息的相关令牌。</span><span class="sxs-lookup"><span data-stu-id="f180a-122">If the sending of a response message needs to be canceled before the batch is submitted, the **CancelResponseMessages** method is used, passing in the correlation token for the associated response message to be deleted.</span></span>  
  
 <span data-ttu-id="f180a-123">在调用时**重新提交**或**挂起**上一条消息，你可能想要保留的某些消息上下文属性值。</span><span class="sxs-lookup"><span data-stu-id="f180a-123">When calling **Resubmit** or **Suspend** on a message you may want to preserve the values of certain message context properties.</span></span> <span data-ttu-id="f180a-124">这可以通过以 XML 格式保存属性值得以实现。</span><span class="sxs-lookup"><span data-stu-id="f180a-124">You can do this by saving property values in XML format.</span></span> <span data-ttu-id="f180a-125">在重新提交或挂起消息时，消息上下文中仍可以使用相应的属性。</span><span class="sxs-lookup"><span data-stu-id="f180a-125">When the message is resubmitted or suspended the corresponding properties remain available in the message context.</span></span>  
  
 <span data-ttu-id="f180a-126">以下 XML 字符串说明了存储信息的格式：</span><span class="sxs-lookup"><span data-stu-id="f180a-126">The following XML string describes the format in which the information is stored:</span></span>  
  
```  
<PropertiesToUpdate>  
<Property name="StringProperty" nameSpace="http://MyNamespace1" vt="8">SomeString</Property>  
<Property name="IntProperty" nameSpace="http://schemas.microsoft.com/BizTalk/2005/test-properties" vt="3">4</Property>  
<Property name="BoolProperty" nameSpace="http://schemas.microsoft.com/BizTalk/2005/test-properties" vt="11">0</Property>  
</PropertiesToUpdate>  
```  
  
 <span data-ttu-id="f180a-127">此 XML 字符串由以下代码生成：</span><span class="sxs-lookup"><span data-stu-id="f180a-127">This XML string is generated by the following code:</span></span>  
  
```  
private string GetPropsToUpdateXml(int nextRetryAttempt)  
{  
string result = "<PropertiesToUpdate><Property name=\"RetryAttempts\" nameSpace=\"http://schemas.microsoft.com/BizTalk/2005/test-properties\" vt=\"3\">" + nextRetryAttempt.ToString() + "</Property></PropertiesToUpdate>";  
return result;  
}  
```  
  
 <span data-ttu-id="f180a-128">然后使用以下代码将此字符串保存到消息上下文中：</span><span class="sxs-lookup"><span data-stu-id="f180a-128">This string is then saved to the message context by using this code:</span></span>  
  
```  
Message.Context.Write("PropertiesToUpdate", "http://schemas.microsoft.com/BizTalk/2003/system-properties", GetPropsToUpdateXml(++retryAttempt));  
```  
  
 <span data-ttu-id="f180a-129">重新提交消息时，适配器可以通过使用以下代码行读取此属性：</span><span class="sxs-lookup"><span data-stu-id="f180a-129">When the message is resubmitted, the adapter can read this property by using the following line of code:</span></span>  
  
```  
propValue = inmsg.Context.Read("RetryAttempts", "http://schemas.microsoft.com/BizTalk/2005/test-properties");  
```