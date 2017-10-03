---
title: "为此 AS2 交换方必须包含值对于 AS2-到 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 029eae5d-4c13-402d-90c5-8e9ef3814a1f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4adda90c2ae0e5dfa659e3bd36dcadfc58f815ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-party-for-this-as2-interchange-must-contain-a-value-for-as2-to"></a>此 AS2 交换的参与方必须包含 AS2-To 的值
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|AS2 引擎|  
|符号名称|InvalidAgreementAS2ToName|  
|消息正文|此 AS2 交换的参与方必须包含 AS2-To 的值。|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道无法处理传出的 AS2 消息，因为没有为解析后的作为消息接收方的参与方设置 AS2-To 属性。 这表明通过将与参与方关联的发送端口与订阅消息的发送端口匹配来解析传出 AS2 消息的参与方。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行，如下所示：  
  
1.  打开 BizTalk Server 管理控制台。  
  
2.  移动到“参与方”节点，并打开为消息解析的参与方的“AS2 属性”对话框。  
  
3.  单击“作为 AS2 消息接收方的参与方”节点。  
  
4.  为 AS2-To 属性输入值。