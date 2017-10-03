---
title: "MIME SMIME 编码器管道组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, MIME/SMIME Encoder
- MIME/SMIME Encoder [pipeline component]
- BTS.EncryptionCert property
ms.assetid: 397505e6-47d0-4b63-9197-814ee4388369
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6c6a79052d3294420c46bff2a1ce3c0ed869e48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="mime-smime-encoder-pipeline-component"></a>MIME SMIME 编码器管道组件
MIME/SMIME 编码器管道组件可放置在发送管道的编码阶段。 它支持 7 位、8 位、二进制、quoted-printable、base64 和 UUencode 编码。 更改本地化数据字符集不会影响编码。  
  
 此组件可用于对使用加密和签名证书的传出消息进行 MIME 编码、签名或加密。  
  
 如果发送管道中包含已配置用来对消息进行签名的编码组件，但没有为包含运行该管道的主机的 BizTalk 组配置签名证书，则传出消息将挂起到运行该管道的主机的挂起队列中（并显示相应的错误）。 如果在运行服务的当前用户的个人证书存储中找不到签名证书，则消息将挂起到运行该管道的主机的挂起队列中。  
  
 如果出站管道中存在已配置用来对出站消息进行加密的编码组件，但在证书存储中找不到证书，则消息将挂起到运行该管道的主机的挂起队列中。  
  
 若要对接收已签名和加密的消息的请求-响应端口执行响应加密，必须在管道中的 MIME/SMIME 编码器管道组件之前添加自定义管道组件。 此自定义管道组件必须标识对应于加密证书的指纹，并将其设置为**BTS。EncryptionCert**消息上下文属性。 有关消息上下文属性的详细信息，请参阅[如何修改组属性](../core/how-to-modify-group-properties.md)。  
  
 有关配置 MIME/SMIME 编码器管道组件的信息，请参阅[如何配置 MIME SMIME 编码器管道组件](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)。 有关加密、 签名和证书的使用情况的 BizTalk Server 支持的详细信息，请参阅[发送和接收消息的安全性](../core/security-for-sending-and-receiving-messages.md)。  
  
## <a name="see-also"></a>另请参阅  
 [管道组件](../core/pipeline-components.md)   
 [MIME SMIME 属性架构和属性](../core/mime-smime-property-schema-and-properties.md)   
 [MIME （BizTalk Server 示例）](../core/mime-biztalk-server-sample.md)