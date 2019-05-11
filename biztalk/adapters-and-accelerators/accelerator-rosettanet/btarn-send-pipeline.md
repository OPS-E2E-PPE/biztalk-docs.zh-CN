---
title: BTARN 发送管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Assembler
- send pipelines, message flow
- DOCTYPE headers
- MIME/SMIME Encoder
- send pipelines, BTARN
- BTARN, send pipelines
- XML Preprocessor
- messages, message flow
ms.assetid: 88562132-0ea4-4b5a-9445-b69f6c84e5ea
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62c86e810ad185f7497f73c1b4d4d53cffe8f29e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284869"
---
# <a name="btarn-send-pipeline"></a>BTARN 发送管道
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]做好 RNIFSend 管道 (RNIFSend.btp) 中的传输 RosettaNet 实现框架 (RNIF) 消息。 发送管道包括以下组件：  
  
-   XML 预处理器  
  
-   XML 组装器  
  
-   多用途 Internet 邮件扩展插件/安全多用途 Internet 邮件扩展 (MIME/SMIME) 编码器  
  
## <a name="xml-preprocessor"></a>XML 预处理器  
 XML 预处理器将 DOCTYPE 标头添加到消息。 标头标识与消息关联的文档类型定义 (DTD) 架构。 RNIF 规范以便进行 RNIF 传输需要 DOCTYPE 标头的存在。  
  
## <a name="xml-assembler"></a>XML 组装器  
 XML 组装器基于 BizTalk Server XML 组装器。 它将属性从消息上下文传输回信封和文档。 它从其 XML 部件和附件组装消息。 它不执行消息验证。  
  
 详细了解本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]XML 组装器，请参阅 BizTalk Server 帮助中的"XML 的组装器管道组件"。  
  
## <a name="mimesmime-encoder"></a>MIME/SMIME 编码器  
 MIME/SMIME 编码器基于 BizTalk Server MIME/SMIME 编码器。 具体取决于贸易合作伙伴协议和 BizTalk Server MIME/SMIME 编码器的设置中的协议设置[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]编码器执行以下：  
  
- 将 8 字节二进制标头添加到消息，根据需要为 RNIF 1.1 消息。  
  
- 编码的消息部分，并计算摘要。  
  
- 将加密的有效负载 （服务内容以及附件） 或负载容器 （服务内容、 服务头和附件）。 如果设置了**所有端口都编码**上设置**协议**到贸易合作伙伴协议的选项卡`False`，编码器将对只对负载进行加密。 如果设置了**所有端口都编码**将设置为`True`，编码器将对负载容器进行加密。  
  
  详细了解本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MIME/SMIME 编码器，请参阅"MIME/SMIME 编码器管道组件"部分中 BizTalk Server 帮助。  
  
## <a name="message-flow"></a>消息流  
 消息流通过[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]发送管道是，如下所示：  
  
1.  如果设置了**所有部分都编码**设置为贸易合作伙伴协议的`True`，MIME / SMIME 编码器将对所有消息部分进行都都编码。 它将使用在中设置的编码方法`Encoding`协议的属性。  
  
2.  对于 RNIF 2.01，如果消息是操作消息，并且没有附件，编码器将执行以下操作为每个附件：  
  
    1.  如果附件是二进制，编码器将对其进行编码。  
  
    2.  编码器将生成的附件的内容 ID。  
  
    3.  编码器将创建附件的 MIME 部分。  
  
3.  管道将加密消息部分并生成 RNIF 消息，具体取决于设置为 RNIF 2.01**是否要求永久保密**（按照流程配置设置中）：  
  
    1.  如果设置了**是否要求永久保密**到**负载**，编码器将加密的服务内容和附件。 然后，在组装器将服务头、 传递头和前导码来构造最终的 RNIF 消息。  
  
    2.  如果设置了**是否要求永久保密**到**负载容器**，编码器将加密的服务头、 服务内容和附件。 然后，在组装器将传递头和前导码来构造最终的 RNIF 消息。  
  
    3.  如果设置了**是否要求永久保密**到**None**，组装器会将服务头、 传递头和前导头添加到服务内容和附件中的 （不加密） 来构造最终的 RNIF 消息。  
  
4.  对于 RNIF 1.1，则组装器将构造最终的 RNIF 消息未加密。  
  
5.  编码器将在以下情况下对消息进行签名：  
  
    1.  该消息是信号消息，并**要求不可否认**属性 （在流程配置设置中） 是`True`。  
  
    2.  该消息是操作消息，并**和内容的不可否认**属性 （在流程配置设置中） 是`True`。  
  
6.  为 RNIF 2.01，编码器将计算在 MIME 消息的第一个正文部分的摘要，并保留该摘要。 它将计算使用的方法中设置的摘要`Digest`贸易合作伙伴协议 （sha-1 或 MD5） 中的方法属性。  
  
## <a name="see-also"></a>请参阅  
 [BTARN 中的消息处理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)