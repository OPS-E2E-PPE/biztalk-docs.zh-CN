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
# <a name="send-adapter-operations"></a>发送适配器操作
发送适配器可执行以下操作：  
  
- **重新提交： void Resubmit （IBaseMessage msg，DateTime timeStamp）。** 在传输后出现故障上一条消息，, 适配器重新提交它在适当的时候。 这称为每个消息的基础上。 如果已成功提交一批消息，适配器必须确定导致失败的消息并重新提交中单独调用不会导致批处理失败的那些**重新提交**。 本主题末尾处提供的有关如何在调用时保留消息上下文属性值的信息**重新提交**。  
  
- **将移动到下一个传输： void MoveToNextTransport (IBaseMessage msg)。** 如果一条消息发送操作期间失败，并且其重试尝试次数已用完，适配器可以向重新传输的下一步配置传输发送消息。  
  
- **挂起： void MoveToSuspendQ (IBaseMessage msg)。** 该适配器将移动失败将消息发送到挂起队列如果配置其他备份传输。 本主题末尾处提供的有关如何在调用时保留消息上下文属性值的信息**挂起**。  
  
- **删除： void DeleteMessage (IBaseMessage msg)。** 适配器通过 BizTalk Server 传输成功的通知后删除一条消息。 删除一条消息会通知 BizTalk Server 适配器已完成并显示消息。 通常**SubmitResponse**操作过程中作为其关联在同一个批处理**删除**操作。  
  
- **提交响应： void SubmitResponseMessage （IBaseMessage solicitMsgSent，IBaseMessage responseMsgToSubmit）。** 适配器提交回 BizTalk Server 发送的批处理的响应。 此操作包括原始消息响应和调用中，因此 BizTalk Server 可以将它们关联起来。  
  
- **取消响应： void 的 CancelResponseMessages (string correlationToken)。** 如果响应消息的发送需要提交批处理之前, 取消**CancelResponseMessages**使用方法，传入要删除的关联的响应消息的相关标记。  
  
  调用时**重新提交**或**挂起**上一条消息你可能想要保留某些消息上下文属性的值。 可以通过以 XML 格式保存属性值来执行此操作。 重新提交或挂起消息时保持消息上下文中可用的相应属性。  
  
  以下 XML 字符串中介绍的信息存储在其中的格式：  
  
```  
<PropertiesToUpdate>  
<Property name="StringProperty" nameSpace="http://MyNamespace1" vt="8">SomeString</Property>  
<Property name="IntProperty" nameSpace="http://schemas.microsoft.com/BizTalk/2005/test-properties" vt="3">4</Property>  
<Property name="BoolProperty" nameSpace="http://schemas.microsoft.com/BizTalk/2005/test-properties" vt="11">0</Property>  
</PropertiesToUpdate>  
```  
  
 下面的代码生成此 XML 字符串：  
  
```  
private string GetPropsToUpdateXml(int nextRetryAttempt)  
{  
string result = "<PropertiesToUpdate><Property name=\"RetryAttempts\" nameSpace=\"http://schemas.microsoft.com/BizTalk/2005/test-properties\" vt=\"3\">" + nextRetryAttempt.ToString() + "</Property></PropertiesToUpdate>";  
return result;  
}  
```  
  
 此字符串将随后保存到消息上下文中，使用以下代码：  
  
```  
Message.Context.Write("PropertiesToUpdate", "http://schemas.microsoft.com/BizTalk/2003/system-properties", GetPropsToUpdateXml(++retryAttempt));  
```  
  
 时重新提交消息，适配器可以读取此属性，使用以下代码行：  
  
```  
propValue = inmsg.Context.Read("RetryAttempts", "http://schemas.microsoft.com/BizTalk/2005/test-properties");  
```