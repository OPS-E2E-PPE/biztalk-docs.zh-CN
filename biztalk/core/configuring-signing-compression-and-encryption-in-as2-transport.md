---
title: 配置签名、 压缩和 AS2 传输中的加密 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc3537a7-c065-4a33-a375-29e7902b5ffa
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a154255cb64fcebafa2ef8164714e46bf5673ba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007198"
---
# <a name="configuring-signing-compression-and-encryption-in-as2-transport"></a>配置 AS2 传输中的签名、压缩和加密
可以从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台内配置数字签名、签名验证、加密和解密。 该配置需要设置 AS2 管道和 BizTalk 参与方的相应属性。  
  
## <a name="using-as2-pipelines"></a>使用 AS2 管道  
 若要确保入站 AS2 消息的安全，请在接收位置使用 AS2 接收管道（AS2EdiReceive 或 AS2Receive）。 AS2 解码器对 AS2 消息进行解密、解压缩和/或执行签名验证。 有关如何执行以上的详细信息，请参阅的"AS2 解码器"部分[AS2 接收组件](../core/as2-receive-components.md)。  
  
 若要确保出站 AS2 消息的安全，请在发送端口使用 AS2 发送管道（AS2EdiSend 或 AS2Send）。 AS2 编码器对出站 AS2 消息进行签名、压缩和加密。 有关如何执行以上的详细信息，请参阅的"AS2 编码器"部分[AS2 发送组件](../core/as2-send-components.md)。  
  
> [!IMPORTANT]
>  在对消息进行签名之后，不得对签名 blob 进行更改。 如果将其更改，则签名会受损。 可以更改边界标头和边界标头以外的对象，但不得更改边界标头以内的对象。  
  
## <a name="setting-as2-agreement-properties"></a>设置 AS2 协议属性  
 可以通过设置 AS2 协议属性来配置签名和加密处理，如下所示：  
  
- 若要签名、 压缩和/或加密出站消息，检查**应对消息进行签名**，**应对消息进行压缩**，并**应对消息进行加密**上的属性**验证**（对于传出的 AS2 消息） 的单向协议选项卡中的页**协议属性**对话框。  
  
- 若要请求经过签名的 MDN 以响应出站消息，检查**请求 MDN**并**请求经过签名的 MDN**上的属性**确认 (Mdn)** 页单向协议选项卡**协议属性**对话框。  
  
- 若要指定入站的消息已签名，将经过压缩和/或加密，检查**使用的验证和 MDN 的协议设置而非消息标头**属性，**应对消息进行签名**属性，**应对消息进行压缩**属性，并**应对消息进行加密**属性上的**验证**单向协议的页（适用于传入的 AS2 消息） 选项卡**协议属性**对话框。  
  
  > [!NOTE]
  >  当**使用的验证和 MDN 的协议设置而非消息标头**选择属性，将忽略传入消息的所有标头详细信息并根据协议设置处理该消息。  
  
- 若要在入站的消息属性通过选择重写时，指定经过签名的 MDN 以响应入站消息，**使用的验证和 MDN 的协议设置而非消息标头**属性，检查**请求签名 MDN**属性**确认 (Mdn)** 页**协议属性**对话框。  
  
  > [!NOTE]
  >  当**使用的验证和 MDN 的协议设置而非消息标头**选择属性，将忽略传入消息的所有标头详细信息并根据协议设置处理该消息。  
  
- 若要指定经过签名的 MDN 以响应入站消息，入站的消息属性未重写时 (**使用的验证和 MDN 的协议设置而非消息标头**清除)，但消息标头不这样做指定进行签名，检查**请求的 MDN 签名如果处置通知选项标头不存在或已签名回执协议标头设置为可选**属性上的**接收方 MDN 设置**页**协议属性**对话框。  
  
- 若要指定一个传出 AS2 消息的 BizTalk 组属性中指定不同的签名证书，请选择**覆盖组签名证书**中**签名证书**页的单向协议选项卡**协议属性**对话框，然后指定签名证书。 如果设置此属性，将使用中提供的证书签名解决协议的 AS2 消息**签名证书**页并不提供的证书为 BizTalk 组属性的一部分。  
  
  有关设置参与方属性的详细信息，请参阅[配置 AS2 属性](../core/configuring-as2-properties.md)。  
  
## <a name="see-also"></a>请参阅  
 [AS2 安全性](../core/as2-security.md)   
 [为 AS2 配置证书](../core/configuring-certificates-for-as2.md)   
 [AS2 消息](../core/as2-messages.md)   
 [AS2 接收组件](../core/as2-receive-components.md)   
 [AS2 发送组件](../core/as2-send-components.md)   
 [配置 AS2 属性](../core/configuring-as2-properties.md)