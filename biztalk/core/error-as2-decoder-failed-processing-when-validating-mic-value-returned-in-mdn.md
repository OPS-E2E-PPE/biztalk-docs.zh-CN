---
title: AS2 解码器处理在验证 MDN 中返回 MIC 值时失败 |Microsoft Docs
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
ms.openlocfilehash: b65543f3edc47b03f8b1f71344d16c5ff7b9293a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388982"
---
# <a name="the-as2-decoder-failed-processing-when-validating-the-mic-value-returned-in-the-mdn"></a>AS2 解码器处理在验证 MDN 中返回 MIC 值时失败
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
| 产品版本 |                                                                      [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                       |
|    事件 ID     |                                                                                                   -                                                                                                   |
|  事件源   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                         |
|    组件    |                                                                                              AS2 引擎                                                                                               |
|  符号名称  |                                                                                AS2DecoderMdnMicFailureDuringProcessing                                                                                |
|  消息正文   | AS2 解码器在处理在验证 MDN 中返回 MIC 值时失败。  MDN 消息的详细信息如下所示：AS2-从:"{0}"AS2-到:"{1}"MessageID:"{2}"OriginalMessageID:"{3}" |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道不无法处理传入 MDN，因为 MIC （消息完整性检查） 未通过验证。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请验证用于生成 MDN （在原始消息的 Signed-receipt-micalg 即用的标头中） 的算法是为 AS2 消息接收方的 Signed-receipt-micalg 即用的属性中指定的算法相同。 两者都应为 SHA1 或 MD5。 如果指定的算法相同，验证已接收内容 MIC 扩展字段中的多部分签名 MDN 消息的第二部分包含有效的 MIC 摘要。 如果是这样，确定为什么 MDN 不对应于已发送交换。