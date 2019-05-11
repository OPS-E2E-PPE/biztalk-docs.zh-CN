---
title: AS2 解码器处理失败，因为 MDN 签名与我们的请求不匹配 |Microsoft Docs
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
ms.openlocfilehash: 2e79b28c69786bad3e261cc3269329bd6465a8ad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388999"
---
# <a name="the-as2-decoder-failed-processing-because-the-mdn-signing-did-not-match-our-request"></a>AS2 解码器处理失败，因为 MDN 签名与我们的请求不匹配
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
| 产品版本 |                                                                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                       |
|    事件 ID     |                                                                                                   -                                                                                                    |
|  事件源   |                                                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                         |
|    组件    |                                                                                               AS2 引擎                                                                                               |
|  符号名称  |                                                                          AS2DecoderMdnSigningMismatchFailureDuringProcessing                                                                           |
|  消息正文   | AS2 解码器处理失败，因为 MDN 签名与我们的请求不匹配。  MDN 消息的详细信息如下所示：AS2-从:"{0}"AS2-到:"{1}"MessageID:"{2}"OriginalMessageID:"{3}" |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入 MDN 是因为已签名 MDN，但签名不请求的 MDN 或 MDN 是无符号整数，但签名请求了 MDN。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  
  
1.  更改以匹配请求的 MDN 的签名请求。 为此，请打开作为 AS2 消息接收方页的 AS2 属性对话框中，并选择"请求 MDN"属性的参与方，请选中或清除"请求经过签名的 MDN"属性。  
  
2.  请与原始的 AS2 消息，若要解决是否应签名 Mdn 的接收方。