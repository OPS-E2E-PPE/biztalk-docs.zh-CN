---
title: 处理验证 MIC 值返回在 MDN 时 AS2 解码器失败 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fe2d76d-b0f1-4118-8483-547c2c9fffb7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90388f27c44314d1c5bc795744366cfc88ed6321
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241333"
---
# <a name="the-as2-decoder-failed-processing-when-validating-the-mic-value-returned-in-the-mdn"></a>AS2 解码器在验证 MDN 中返回的 MIC 值时处理失败
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|AS2 引擎|  
|符号名称|AS2DecoderMdnMicFailureDuringProcessing|  
|消息正文|AS2 解码器在验证 MDN 中返回的 MIC 值时处理失败。  MDN 消息的详细信息如下所示： AS2-从:"{0}"AS2-到:"\ {1 \}"MessageID:"\ {2 \}"OriginalMessageID:"\ {3\}"|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的 MDN，因为 MIC（消息完整性检查）未通过验证。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请验证用于生成 MDN 的算法（在原始消息的 Signed-Receipt-MICalg 标头中）是否与 AS2 消息接收方的 Signed-Receipt-MICalg 属性中指定的算法相同。 都应是 SHA1 或 MD5。 如果指定的算法相同，请验证多部分签名的 MDN 消息的第二部分中的接收时间内容 MIC 扩展字段包括有效的 MIC 摘要。 如果是这样，确定为何 MDN 不对应于已发送的交换。