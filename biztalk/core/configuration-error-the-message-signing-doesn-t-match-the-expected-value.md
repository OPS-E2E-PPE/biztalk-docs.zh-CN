---
title: 配置错误。 消息签名不&#39;t 与预期值匹配。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f067351-b6b0-479d-b2ff-81e9f45b5924
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a89d1124bc417b8af4d18271b05d3579d6935b99
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391505"
---
# <a name="configuration-error-the-message-signing-doesn39t-match-the-expected-value"></a>配置错误。 消息签名不&#39;t 与预期值匹配。
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                              |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                              |
| 产品版本 |                                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                          |
|    事件 ID     |                                                                                      -                                                                                       |
|  事件源   |                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                            |
|    组件    |                                                                                  AS2 引擎                                                                                  |
|  符号名称  |                                                                   AS2DecoderPartySigningConfigurationError                                                                   |
|  消息正文   | 配置错误。 消息签名与预期值不匹配。 请与发送合作伙伴联系，以验证签名使用。 AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}" |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道的 AS2 解码器组件无法在参与方设置中，指定签名但未签名的 AS2 消息，或指定签名，则无法启用，因为处理 AS2 消息但是，对消息进行签名。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请验证传入的 AS2 消息进行签名，如果在参与方设置中指定了签名，或如果签名未签名传入的 AS2 消息指定为未启用参与方设置中。 执行以下操作之一：  
  
1.  如果**替代入站的消息属性**属性选择的参与方中作为 AS2 消息发送方在 BizTalk Server 管理控制台的 AS2 属性对话框页**应对消息进行签名的**选择属性，但未签名消息，请与发送消息的参与方和要求他们对消息进行签名并重新发送它。 也可以清除**应对消息进行签名**属性，或**替代入站的消息属性**属性。  
  
2.  如果**替代入站的消息属性**选定属性，则**应对消息进行签名**清除属性，但对消息进行签名、 联系发送消息的参与方并请求他们不这样做对消息进行签名，然后重新发送它。 也可以选择**应对消息进行签名**属性。