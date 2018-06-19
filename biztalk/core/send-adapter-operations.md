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
# <a name="send-adapter-operations"></a>发送适配器操作
发送适配器可执行以下操作：  
  
-   **重新提交： void Resubmit （IBaseMessage msg，DateTime timeStamp）。** 消息发生传输失败后，适配器会在适当的时候重新提交消息。 该操作对每条消息调用一次。 如果已成功提交一批消息，适配器必须确定导致该错误的消息，并重新提交到单独的调用中不会导致批处理失败的**重新提交**。 没有在本主题末尾若要了解如何在调用时保留消息上下文属性值**重新提交**。  
  
-   **将移动到下一个传输： void MoveToNextTransport (IBaseMessage msg)。** 如果某个消息在发送操作中失败，并已重试了允许的最大尝试次数，则适配器会将该消息发送到配置的下一次传输，以便重新传输。  
  
-   **挂起： void MoveToSuspendQ (IBaseMessage msg)。** 如果未配置其他备份传输，则适配器会将失败的发送消息移至挂起队列。 没有在本主题末尾若要了解如何在调用时保留消息上下文属性值**挂起**。  
  
-   **删除： void DeleteMessage (IBaseMessage msg)。** 收到 BizTalk Server 关于消息传输成功的通知后，适配器会删除该消息。 删除消息的操作会通知 BizTalk Server 适配器已完成处理该消息。 通常**SubmitResponse**操作在其关联，因此同一批中完成**删除**操作。  
  
-   **提交响应： void SubmitResponseMessage （IBaseMessage solicitMsgSent，IBaseMessage responseMsgToSubmit）。** 适配器向要发回至 BizTalk Server 的批提交响应。 此操作在调用中包括原始消息以及响应，以便 BizTalk Server 可以将它们关联起来。  
  
-   **取消响应： void 的 CancelResponseMessages (string correlationToken)。** 如果发送响应消息需要之前提交批语句后，会取消**CancelResponseMessages**方法使用中，并传入要删除关联的响应消息的相关令牌。  
  
 在调用时**重新提交**或**挂起**上一条消息，你可能想要保留的某些消息上下文属性值。 这可以通过以 XML 格式保存属性值得以实现。 在重新提交或挂起消息时，消息上下文中仍可以使用相应的属性。  
  
 以下 XML 字符串说明了存储信息的格式：  
  
```  
<PropertiesToUpdate>  
<Property name="StringProperty" nameSpace="http://MyNamespace1" vt="8">SomeString</Property>  
<Property name="IntProperty" nameSpace="http://schemas.microsoft.com/BizTalk/2005/test-properties" vt="3">4</Property>  
<Property name="BoolProperty" nameSpace="http://schemas.microsoft.com/BizTalk/2005/test-properties" vt="11">0</Property>  
</PropertiesToUpdate>  
```  
  
 此 XML 字符串由以下代码生成：  
  
```  
private string GetPropsToUpdateXml(int nextRetryAttempt)  
{  
string result = "<PropertiesToUpdate><Property name=\"RetryAttempts\" nameSpace=\"http://schemas.microsoft.com/BizTalk/2005/test-properties\" vt=\"3\">" + nextRetryAttempt.ToString() + "</Property></PropertiesToUpdate>";  
return result;  
}  
```  
  
 然后使用以下代码将此字符串保存到消息上下文中：  
  
```  
Message.Context.Write("PropertiesToUpdate", "http://schemas.microsoft.com/BizTalk/2003/system-properties", GetPropsToUpdateXml(++retryAttempt));  
```  
  
 重新提交消息时，适配器可以通过使用以下代码行读取此属性：  
  
```  
propValue = inmsg.Context.Read("RetryAttempts", "http://schemas.microsoft.com/BizTalk/2005/test-properties");  
```