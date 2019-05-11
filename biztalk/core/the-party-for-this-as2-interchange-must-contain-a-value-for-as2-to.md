---
title: 此 AS2 交换的参与方必须包含值为 AS2-到 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 029eae5d-4c13-402d-90c5-8e9ef3814a1f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccabce0ce60f018f6d55d64a26c1f9540ed88fa2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394099"
---
# <a name="the-party-for-this-as2-interchange-must-contain-a-value-for-as2-to"></a>此 AS2 交换的参与方必须包含值为 AS2-到
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       AS2 引擎                                       |
|  符号名称  |                               InvalidAgreementAS2ToName                                |
|  消息正文   |          此 AS2 交换的参与方必须包含值为 AS2-到。           |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道不无法处理传出的 AS2 消息，因为 AS2-作为消息接收方的解析参与方未设置属性。 这表示传出的 AS2 消息的参与方已通过匹配订阅该消息的发送端口的参与方与关联的发送端口来解决。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行，如下所示：  
  
1.  打开 BizTalk Server 管理控制台。  
  
2.  转到参与方节点，然后打开为消息解析的参与方 AS2 属性对话框。  
  
3.  为 AS2 消息接收方节点中单击的参与方。  
  
4.  输入 AS2 的值的属性。