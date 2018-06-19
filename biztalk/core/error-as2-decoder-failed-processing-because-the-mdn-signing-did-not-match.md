---
title: AS2 解码器失败处理，因为 MDN 签名与我们请求不匹配 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a42d344-fc28-4bc4-9328-46158f15a008
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc0660a64ff0aeb35976ad1aa45a602d8db0913a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239973"
---
# <a name="the-as2-decoder-failed-processing-because-the-mdn-signing-did-not-match-our-request"></a>AS2 解码器处理失败，因为 MDN 签名与我们的请求不匹配
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|AS2 引擎|  
|符号名称|AS2DecoderMdnSigningMismatchFailureDuringProcessing|  
|消息正文|AS2 解码器处理失败，因为 MDN 签名与我们的请求不匹配。  MDN 消息的详细信息如下所示： AS2-从:"{0}"AS2-到:"\ {1 \}"MessageID:"\ {2 \}"OriginalMessageID:"\ {3\}"|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件指示接收管道无法处理传入的 MDN 或者因为 MDN 已签名，但签名未请求 MDN 或将 MDN 是无符号整数，但签名为请求 MDN。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  
  
1.  更改 MDN 的签名请求以匹配请求。 为此，请打开“AS2 属性”对话框的“作为 AS2 消息接收方的参与方”页，并且选中“请求 MDN”属性，选中或清除“请求经过签名的 MDN”属性。  
  
2.  请与联系以解决 Mdn 应或未进行签名的原始 AS2 消息接收方。