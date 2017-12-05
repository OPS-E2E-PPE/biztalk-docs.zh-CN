---
title: "配置错误。 消息签名没有 &#39; t 与预期值的匹配。 | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f067351-b6b0-479d-b2ff-81e9f45b5924
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7aaba3aa00b15b3e015cbc010901c6d50818c42
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="configuration-error-the-message-signing-doesn39t-match-the-expected-value"></a>配置错误。 消息签名没有 &#39; t 与预期值的匹配。
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|AS2 引擎|  
|符号名称|AS2DecoderPartySigningConfigurationError|  
|消息正文|配置错误。 消息签名与预期的值不匹配。 请与发送合作伙伴联系，以验证签名使用情况。 AS2-从:"{0}"AS2-到:"\ {1 \}"MessageID:"\ {2 \}"|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道的 AS2 解码器组件无法处理 AS2 消息，因为在参与方设置中指定了签名，但未对 AS2 消息进行签名，或者指定不启用签名但已对消息进行签名。  
  
## <a name="user-action"></a>用户操作  
 要解决此错误，请验证中的方设置未启用消息进行签名，如果签名方设置中指定或如果签名未签名为传入 AS2 消息指定为传入 AS2。 执行以下操作之一：  
  
1.  如果**重写入站的消息属性**方中为 AS2 消息发送方页面在 BizTalk Server 管理控制台中，AS2 属性对话框中选择属性**消息应为签名的**选择属性，但未签名消息、 发送消息的组织联系并要求他们对消息进行签名并重新发送它。 也可以清除**应对消息进行签名**属性，或**重写入站的消息属性**属性。  
  
2.  如果**重写入站的消息属性**选定属性，则**应对消息进行签名**属性处于未选中状态，但消息已签名，请联系发送消息的当事方并不适用于请求对消息进行签名并重新发送它。 也可以选择**应对消息进行签名**属性。