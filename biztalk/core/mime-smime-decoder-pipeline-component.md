---
title: MIME SMIME 解码器管道组件 |Microsoft 文档
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
ms.openlocfilehash: d85fe099cb876156410ba86c5f204a154dfbac36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263221"
---
# <a name="mime-smime-decoder-pipeline-component"></a>MIME SMIME 解码器管道组件
MIME/SMIME 解码器组件可为消息提供 MIME 解码功能。 此管道组件可置于接收管道的解码阶段中，它支持 7 位、8 位、二进制、Quoted-Printable、UUEncode 和 Base64 解码。 本地化数据字符集的更改将不会影响解码。  
  
 MIME/SMIME 解码器组件可以对传入消息进行解密和签名验证。 使用的解密证书来自运行服务的当前用户的个人证书存储。 使用的签名验证证书来自本地计算机的通讯簿存储或消息本身。  
  
 一旦消息解密成功，MIME/SMIME 解码器管道组件就会关联用于将消息解密为消息谓词的解密证书的指纹。 这意味着所有订阅该消息的服务（业务流程或发送端口）都必须与拥有其密钥的主机相关联。 主机和密钥之间的关联可作为主机的一个属性在 BizTalk 管理控制台中完成设置。 在 BizTalk 管理控制台中配置主机的详细信息，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。  
  
 MIME/SMIME 解码器管道组件是唯一的即时可用的接收管道组件，该组件可以处理多部分消息，包括多部分 MIME/SMIME 消息。 该管道组件可解析消息，并创建等效的多部分 BizTalk 消息。 多部分 BizTalk 消息只有一个称为正文部分的部分。 所有其他管道组件（如 XML 拆装器管道组件）只处理 BizTalk 消息的正文部分。 另外，可使用 BizTalk 正文部分所对应的 MessageType 将消息路由到订户。  
  
 MIME/SMIME 解码器管道组件将评估以下条件，以标识与多部分 MIME 消息相对应的 BizTalk 正文部分。 条件评估的顺序如下：  
  
1.  第一个 MIME/SMIME 部分的内容说明标头设置为“body”（不区分大小写）。  
  
2.  第一个 MIME/SMIME 部分的内容类型标头设置为“text/xml”（不区分大小写）。  
  
3.  第一个 MIME/SMIME 部分的内容类型标头设置为“text/”（不区分大小写）。  
  
4.  第一个 MIME/SMIME 部分。  
  
> [!NOTE]
>  输出 BizTalk 消息中的部分顺序与 MIME/SMIME 消息中 MIME/SMIME 部分的顺序相同。  
  
> [!NOTE]
>  如果多部分 BizTalk 消息正由业务流程订阅或使用，则消息中的部分数必须与激活该业务流程的消息中的部分数一致。  
  
 有关配置 MIME/SMIME 解码器管道组件的信息，请参阅[如何配置 MIME SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。 有关 BizTalk Server 支持解密、 登录验证和证书的使用情况的详细信息，请参阅[发送和接收消息的安全性](../core/security-for-sending-and-receiving-messages.md)。  
  
## <a name="see-also"></a>另请参阅  
 [管道组件](../core/pipeline-components.md)   
 [MIME SMIME 属性架构和属性](../core/mime-smime-property-schema-and-properties.md)   
 [MIME （BizTalk Server 示例）](../core/mime-biztalk-server-sample.md)