---
title: "配置错误。 消息加密不 &#39; 与预期值匹配的 t |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99c37c7d-6654-4004-8345-9d7bfc3659b6
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4920a4c26cb60c3215f58297445dc49551b1befe
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="configuration-error-the-message-encryption-doesn39t-match-the-expected-value"></a>配置错误。 消息加密不 &#39; t 匹配预期值
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|AS2 引擎|  
|符号名称|AS2DecoderPartyEncryptionConfigurationError|  
|消息正文|配置错误。 消息加密与预期值不匹配。 请与发送合作伙伴联系，以验证加密使用情况。 AS2-从:"{0}"AS2-到:"\ {1 \}"MessageID:"\ {2 \}"|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件指示接收管道的 AS2 解码器组件无法因加密指定在方设置中，但未加密 AS2 消息，或者加密指定不准备处理 AS2 消息启用，但对消息加密。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请验证是否已对传入的 AS2 消息进行加密（如果在参与方设置中指定了加密），或者验证是否未对传入的 AS2 消息进行加密（如果在参与方设置中指定了不启用加密）。 执行以下操作之一：  
  
1.  如果**替代选择入站的消息属性属性**中为在 BizTalk Server 管理控制台中，AS2 属性对话框中的 AS2 消息发送方页面方**应对消息进行加密**选择属性，但未加密消息，发送消息的组织联系并要求他们来加密消息，并重新发送它。 也可以清除**应对消息进行加密**属性，或**重写入站的消息属性**属性。  
  
2.  如果**重写入站的消息属性**选定属性，则**应对消息进行加密**属性处于未选中状态，但对消息加密，请联系发送消息的当事方，并请求无法加密消息，并重新发送它。 也可以选择**应对消息进行加密**属性。