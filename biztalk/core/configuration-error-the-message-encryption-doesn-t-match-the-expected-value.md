---
title: 配置错误。 消息加密并不&#39;t 与预期值匹配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 99c37c7d-6654-4004-8345-9d7bfc3659b6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51756b202d554b2ea85eb8e302497729f524ea2a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356511"
---
# <a name="configuration-error-the-message-encryption-doesn39t-match-the-expected-value"></a>配置错误。 消息加密并不&#39;t 匹配预期值
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                  |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                |
| 产品版本 |                                                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                            |
|    事件 ID     |                                                                                        -                                                                                         |
|  事件源   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                              |
|    组件    |                                                                                    AS2 引擎                                                                                    |
|  符号名称  |                                                                   AS2DecoderPartyEncryptionConfigurationError                                                                    |
|  消息正文   | 配置错误。 消息加密与预期值不匹配。 请与发送合作伙伴联系，以验证加密使用。 AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}" |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道的 AS2 解码器组件无法因为在参与方设置中，指定加密但未加密的 AS2 消息，或加密指定为不处理 AS2 消息已启用，但对消息进行加密。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请验证传入的 AS2 消息进行加密，是否参与方设置中指定加密或为未指定加密未加密的传入 AS2 消息启用参与方设置中。 执行以下操作之一：  
  
1.  如果**选择入站的消息属性属性重写**作为 AS2 消息发送方在 BizTalk Server 管理控制台的 AS2 属性对话框页的参与方**应对消息进行加密**选择属性，但未加密消息，请与发送消息的参与方和要求他们以加密消息，并重新发送它。 也可以清除**应对消息进行加密**属性，或**替代入站的消息属性**属性。  
  
2.  如果**替代入站的消息属性**选定属性，则**应对消息进行加密**清除属性，但对消息进行加密，请与发送消息的参与方，并请求他们无法加密消息，并重新发送它。 也可以选择**应对消息进行加密**属性。