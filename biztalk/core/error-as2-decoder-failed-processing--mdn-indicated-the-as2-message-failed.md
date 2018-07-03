---
title: AS2 解码器处理失败，因为 MDN 指示 AS2 消息处理失败 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bce620a-f336-435e-b7c3-3db060f2819d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 240c90d488d313bf43982c7c98db3e8a1ea05e75
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984494"
---
# <a name="the-as2-decoder-failed-processing-because-the-mdn-indicated-the-as2-message-failed-processing"></a>AS2 解码器处理失败，因为 MDN 指示 AS2 消息处理失败
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                |
| 产品版本 |                                                                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                            |
|    事件 ID     |                                                                                                        -                                                                                                         |
|  事件源   |                                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                              |
|    组件    |                                                                                                    AS2 引擎                                                                                                    |
|  符号名称  |                                                                                      AS2DecoderMdnProcessingFailureReturned                                                                                      |
|  消息正文   | AS2 解码器处理失败，因为 MDN 指示 AS2 消息处理失败。  MDN 消息的详细信息如下所示： AS2-从:"{0}"AS2-到:"{1}"MessageID:"{2}"OriginalMessageID:"{3}" |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 MDN 响应显示原始 AS2 消息的接收方无法处理原始 AS2 消息。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请与 AS2 消息的接收方联系，确定在接收方处理失败的原因，修复原始 AS2 消息，然后重新发送。