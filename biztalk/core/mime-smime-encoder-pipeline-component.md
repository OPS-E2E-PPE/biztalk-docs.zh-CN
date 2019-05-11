---
title: MIME-SMIME 编码器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, MIME/SMIME Encoder
- MIME/SMIME Encoder [pipeline component]
- BTS.EncryptionCert property
ms.assetid: 397505e6-47d0-4b63-9197-814ee4388369
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c20197519f6bde52470712175cb632a7309c3609
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65527529"
---
# <a name="mime-smime-encoder-pipeline-component"></a>MIME-SMIME 编码器管道组件
MIME/SMIME 编码器组件可以放入发送管道的编码阶段。 它支持 7 位、 8 位、 二进制、 quoted printable，base64 和 UUencode 编码。 本地化的数据字符集的更改不会影响的编码。  
  
 此组件可用于对 MIME 编码、 签名或加密传出消息使用加密和签名证书。  
  
 如果在配置发送管道中的编码组件进行签名的消息，并包括运行管道的主机的 BizTalk 组没有配置签名证书，传出消息将被挂起 （具有相应错误） 到运行该管道的主机的挂起队列。 如果在其下运行服务的当前用户的个人证书存储中找不到签名证书，该消息将挂起到运行该管道的主机的挂起队列。  
  
 如果配置出站消息进行加密的出站管道中的编码组件，并且证书存储区中找不到证书，该消息将挂起到运行该管道的主机的挂起队列。  
  
 若要在接收已签名和加密消息的请求响应端口执行响应加密，自定义管道组件必须添加到之前的 MIME/SMIME 编码器管道组件的管道。 此自定义管道组件必须确定的加密证书相对应的指纹，并将其设置为**BTS。EncryptionCert**消息上下文属性。 有关消息上下文属性的详细信息，请参阅[如何修改组属性](../core/how-to-modify-group-properties.md)。  
  
 有关配置 MIME/SMIME 编码器管道组件的信息，请参阅[如何配置 MIME-SMIME 编码器管道组件](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)。 有关 BizTalk Server 支持的加密、 签名和证书的使用情况的详细信息，请参阅[发送和接收消息的安全性](../core/security-for-sending-and-receiving-messages.md)。  
  
## <a name="see-also"></a>请参阅  
 [管道组件](../core/pipeline-components.md)   
 [MIME-SMIME 属性架构和属性](../core/mime-smime-property-schema-and-properties.md)   
 [MIME（BizTalk Server 示例）](../core/mime-biztalk-server-sample.md)