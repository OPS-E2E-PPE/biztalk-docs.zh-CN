---
title: MIME-SMIME 解码器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, MIME/SMIME Decoder
- MIME/SMIME Decoder [pipeline component]
ms.assetid: ff6c963c-1b5c-4be4-9eef-3ec9a018e7fd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 593873b1d3252eed752de21fe4bb9c99dc664974
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394475"
---
# <a name="mime-smime-decoder-pipeline-component"></a>MIME-SMIME 解码器管道组件
MIME/SMIME 解码器组件提供 MIME 解码的消息的功能。 此管道组件可置于接收管道的解码阶段，它支持 7 位、 8 位、 二进制、 quoted printable、 UUEncode 和 base64 解码。 本地化的数据字符集的更改不会影响解码。  
  
 MIME/SMIME 解码器组件可以解密和签名验证传入消息。 在其下运行该服务的当前用户的个人证书存储中使用的解密证书。 从本地计算机的通讯簿存储或从消息本身使用签名验证证书。  
  
 消息的解密成功，MIME/SMIME 解码器管道组件将用于对消息进行解密为消息的谓词的解密证书的指纹相关联。 这意味着任何订阅该消息的服务 （业务流程或发送端口） 必须与主机拥有该密钥相关联。 作为主机的属性，可在 BizTalk 管理控制台中完成主机和密钥之间的关联。 有关在 BizTalk 管理控制台中配置主机的详细信息，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。  
  
 MIME/SMIME 解码器管道组件是唯一的-现成的接收管道组件处理多部分消息，包括多部分 MIME/SMIME 消息。 管道组件可解析该消息并创建等效的多部分 BizTalk 消息。 多部分 BizTalk 消息有一个名为正文部分的唯一部分。 所有其他管道组件，如 XML 拆装器管道组件，只处理 BizTalk 消息的正文部分。 此外与 BizTalk 正文部分对应的 MessageType 用于将消息路由到订阅服务器。  
  
 MIME/SMIME 解码器管道组件来标识对应于由多部分 MIME 消息，BizTalk 正文部分的情况下，将评估以下条件。 条件计算的顺序是按如下所示：  
  
1.  第一个 MIME/SMIME 部分设置为"body"（不区分大小写） 的内容说明标头。  
  
2.  第一个 MIME/SMIME 部分的 Content-type 标头设置为"text/xml"(case-insensitive)。  
  
3.  第一个 MIME/SMIME 部分的 Content-type 标头设置为"text /"（不区分大小写）。  
  
4.  第一个 MIME/SMIME 部分。  
  
> [!NOTE]
>  顺序 BizTalk 消息的输出中的部分是与 MIME/SMIME 消息中 MIME/SMIME 部分的顺序相同。  
  
> [!NOTE]
>  如果多部分 BizTalk 消息正由业务流程或订阅，消息中的部分数必须匹配在激活该业务流程的消息中的部分数。  
  
 有关配置 MIME/SMIME 解码器管道组件的信息，请参阅[如何配置 MIME-SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。 有关 BizTalk Server 支持解密、 签名验证和使用证书的详细信息，请参阅[发送和接收消息的安全性](../core/security-for-sending-and-receiving-messages.md)。  
  
## <a name="see-also"></a>请参阅  
 [管道组件](../core/pipeline-components.md)   
 [MIME-SMIME 属性架构和属性](../core/mime-smime-property-schema-and-properties.md)   
 [MIME（BizTalk Server 示例）](../core/mime-biztalk-server-sample.md)