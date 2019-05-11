---
title: 发送适配器操作 |Microsoft Docs
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
ms.openlocfilehash: 1e4fbc0458fa9c433c585143bcada38e0e25c3c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250868"
---
# <a name="send-adapter-operations"></a><span data-ttu-id="ea5e2-102">发送适配器操作</span><span class="sxs-lookup"><span data-stu-id="ea5e2-102">Send Adapter Operations</span></span>
<span data-ttu-id="ea5e2-103">发送适配器可执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ea5e2-103">Send adapters can perform the following operations:</span></span>  
  
- <span data-ttu-id="ea5e2-104">**重新提交： void Resubmit （IBaseMessage msg，DateTime timeStamp）。**</span><span class="sxs-lookup"><span data-stu-id="ea5e2-104">**Resubmit: void Resubmit(IBaseMessage msg, DateTime timeStamp).**</span></span> <span data-ttu-id="ea5e2-105">在传输后出现故障上一条消息，, 适配器重新提交它在适当的时候。</span><span class="sxs-lookup"><span data-stu-id="ea5e2-105">After a transmission failure occurs on a message, an adapter resubmits it when appropriate.</span></span> <span data-ttu-id="ea5e2-106">这称为每个消息的基础上。</span><span class="sxs-lookup"><span data-stu-id="ea5e2-106">This is called on a per-message basis.</span></span> <span data-ttu-id="ea5e2-107">如果已成功提交一批消息，适配器必须确定导致失败的消息并重新提交中单独调用不会导致批处理失败的那些**重新提交**。</span><span class="sxs-lookup"><span data-stu-id="ea5e2-107">If a batch of messages was submitted unsuccessfully, the adapter must determine the messages causing the failure, and resubmit the ones that did not cause the batch to fail in separate calls to **Resubmit**.</span></span> <span data-ttu-id="ea5e2-108">本主题末尾处提供的有关如何在调用时保留消息上下文属性值的信息**重新提交**。</span><span class="sxs-lookup"><span data-stu-id="ea5e2-108">There is information at the end of this topic about how to preserve message context property values when you call **Resubmit**.</span></span>  
  
- <span data-ttu-id="ea5e2-109">**将移动到下一个传输： void MoveToNextTransport (IBaseMessage msg)。**</span><span class="sxs-lookup"><span data-stu-id="ea5e2-109">**Move to Next Transport: void MoveToNextTransport(IBaseMessage msg).**</span></span> <span data-ttu-id="ea5e2-110">如果一条消息发送操作期间失败，并且其重试尝试次数已用完，适配器可以向重新传输的下一步配置传输发送消息。</span><span class="sxs-lookup"><span data-stu-id="ea5e2-110">If a message fails during a send operation and its retry attempts have been exhausted, the adapter can send the message to the next configured transport for retransmission.</span></span>  
  
- <span data-ttu-id="ea5e2-111">**挂起： void MoveToSuspendQ (IBaseMessage msg)。**</span><span class="sxs-lookup"><span data-stu-id="ea5e2-111">**Suspend: void MoveToSuspendQ(IBaseMessage msg).**</span></span> <span data-ttu-id="ea5e2-112">该适配器将移动失败将消息发送到挂起队列如果配置其他备份传输。</span><span class="sxs-lookup"><span data-stu-id="ea5e2-112">The adapter moves a failed send message to the Suspended queue if no additional backup transport is configured.</span></span> <span data-ttu-id="ea5e2-113">本主题末尾处提供的有关如何在调用时保留消息上下文属性值的信息**挂起**。</span><span class="sxs-lookup"><span data-stu-id="ea5e2-113">There is information at the end of this topic about how to preserve message context property values when you call **Suspend**.</span></span>  
  
- <span data-ttu-id="ea5e2-114">**删除： void DeleteMessage (IBaseMessage msg)。**</span><span class="sxs-lookup"><span data-stu-id="ea5e2-114">**Delete: void DeleteMessage(IBaseMessage msg).**</span></span> <span data-ttu-id="ea5e2-115">适配器通过 BizTalk Server 传输成功的通知后删除一条消息。</span><span class="sxs-lookup"><span data-stu-id="ea5e2-115">The adapter deletes a message after being notified by BizTalk Server of its successful transmission.</span></span> <span data-ttu-id="ea5e2-116">删除一条消息会通知 BizTalk Server 适配器已完成并显示消息。</span><span class="sxs-lookup"><span data-stu-id="ea5e2-116">Deleting a message tells BizTalk Server that the adapter is finished with the message.</span></span> <span data-ttu-id="ea5e2-117">通常**SubmitResponse**操作过程中作为其关联在同一个批处理**删除**操作。</span><span class="sxs-lookup"><span data-stu-id="ea5e2-117">Generally the **SubmitResponse** operation is done in the same batch as its associated **Delete** operation.</span></span>  
  
- <span data-ttu-id="ea5e2-118">**提交响应： void SubmitResponseMessage （IBaseMessage solicitMsgSent，IBaseMessage responseMsgToSubmit）。**</span><span class="sxs-lookup"><span data-stu-id="ea5e2-118">**Submit Response: void SubmitResponseMessage(IBaseMessage solicitMsgSent, IBaseMessage responseMsgToSubmit).**</span></span> <span data-ttu-id="ea5e2-119">适配器提交回 BizTalk Server 发送的批处理的响应。</span><span class="sxs-lookup"><span data-stu-id="ea5e2-119">The adapter submits a response to the batch to be sent back to BizTalk Server.</span></span> <span data-ttu-id="ea5e2-120">此操作包括原始消息响应和调用中，因此 BizTalk Server 可以将它们关联起来。</span><span class="sxs-lookup"><span data-stu-id="ea5e2-120">This operation includes the original message in the call along with the response so that BizTalk Server can correlate them.</span></span>  
  
- <span data-ttu-id="ea5e2-121">**取消响应： void 的 CancelResponseMessages (string correlationToken)。**</span><span class="sxs-lookup"><span data-stu-id="ea5e2-121">**Cancel Response: void CancelResponseMessages(string correlationToken).**</span></span> <span data-ttu-id="ea5e2-122">如果响应消息的发送需要提交批处理之前, 取消**CancelResponseMessages**使用方法，传入要删除的关联的响应消息的相关标记。</span><span class="sxs-lookup"><span data-stu-id="ea5e2-122">If the sending of a response message needs to be canceled before the batch is submitted, the **CancelResponseMessages** method is used, passing in the correlation token for the associated response message to be deleted.</span></span>  
  
  <span data-ttu-id="ea5e2-123">调用时**重新提交**或**挂起**上一条消息你可能想要保留某些消息上下文属性的值。</span><span class="sxs-lookup"><span data-stu-id="ea5e2-123">When calling **Resubmit** or **Suspend** on a message you may want to preserve the values of certain message context properties.</span></span> <span data-ttu-id="ea5e2-124">可以通过以 XML 格式保存属性值来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="ea5e2-124">You can do this by saving property values in XML format.</span></span> <span data-ttu-id="ea5e2-125">重新提交或挂起消息时保持消息上下文中可用的相应属性。</span><span class="sxs-lookup"><span data-stu-id="ea5e2-125">When the message is resubmitted or suspended the corresponding properties remain available in the message context.</span></span>  
  
  <span data-ttu-id="ea5e2-126">以下 XML 字符串中介绍的信息存储在其中的格式：</span><span class="sxs-lookup"><span data-stu-id="ea5e2-126">The following XML string describes the format in which the information is stored:</span></span>  
  
```  
<PropertiesToUpdate>  
<Property name="StringProperty" nameSpace="http://MyNamespace1" vt="8">SomeString</Property>  
<Property name="IntProperty" nameSpace="http://schemas.microsoft.com/BizTalk/2005/test-properties" vt="3">4</Property>  
<Property name="BoolProperty" nameSpace="http://schemas.microsoft.com/BizTalk/2005/test-properties" vt="11">0</Property>  
</PropertiesToUpdate>  
```  
  
 <span data-ttu-id="ea5e2-127">下面的代码生成此 XML 字符串：</span><span class="sxs-lookup"><span data-stu-id="ea5e2-127">This XML string is generated by the following code:</span></span>  
  
```  
private string GetPropsToUpdateXml(int nextRetryAttempt)  
{  
string result = "<PropertiesToUpdate><Property name=\"RetryAttempts\" nameSpace=\"http://schemas.microsoft.com/BizTalk/2005/test-properties\" vt=\"3\">" + nextRetryAttempt.ToString() + "</Property></PropertiesToUpdate>";  
return result;  
}  
```  
  
 <span data-ttu-id="ea5e2-128">此字符串将随后保存到消息上下文中，使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="ea5e2-128">This string is then saved to the message context by using this code:</span></span>  
  
```  
Message.Context.Write("PropertiesToUpdate", "http://schemas.microsoft.com/BizTalk/2003/system-properties", GetPropsToUpdateXml(++retryAttempt));  
```  
  
 <span data-ttu-id="ea5e2-129">时重新提交消息，适配器可以读取此属性，使用以下代码行：</span><span class="sxs-lookup"><span data-stu-id="ea5e2-129">When the message is resubmitted, the adapter can read this property by using the following line of code:</span></span>  
  
```  
propValue = inmsg.Context.Read("RetryAttempts", "http://schemas.microsoft.com/BizTalk/2005/test-properties");  
```