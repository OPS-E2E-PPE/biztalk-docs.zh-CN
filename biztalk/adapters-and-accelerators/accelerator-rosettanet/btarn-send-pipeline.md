---
title: BTARN 发送管道 |Microsoft 文档
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
ms.openlocfilehash: f566b37cc43f8aca2f0a36143d10d809c008d5cd
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007518"
---
# <a name="btarn-send-pipeline"></a>BTARN 发送管道
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RosettaNet 实现框架 (RNIF) 消息准备 RNIFSend 管道 (RNIFSend.btp) 中的传输。 发送管道包括：  
  
-   预处理器的 XML  
  
-   XML 组装器  
  
-   多用途 Internet 邮件扩展安全/多用途 Internet 邮件扩展 (MIME/SMIME) 编码器  
  
## <a name="xml-preprocessor"></a>XML 预处理器  
 XML 预处理器将 DOCTYPE 标头添加到消息。 标头来确定与消息关联的文档类型定义 (DTD) 架构。 RNIF 规范要求 RNIF 传输 DOCTYPE 标头。  
  
## <a name="xml-assembler"></a>XML 汇编程序  
 XML 汇编程序取决于 BizTalk Server XML 汇编程序。 它将属性从消息上下文传输回包络线和文档。 它从其 XML 部件和附件装配消息。 它不执行消息验证。  
  
 有关本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]XML 汇编程序，请参阅 BizTalk Server 帮助中的"XML 的汇编程序管道组件"。  
  
## <a name="mimesmime-encoder"></a>MIME/SMIME 编码器  
 MIME/SMIME 编码器取决于 BizTalk Server MIME/SMIME 编码器。 具体取决于贸易合作伙伴协议和 BizTalk Server MIME/SMIME 编码器的设置中的协议设置[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]编码器执行以下：  
  
-   将一个 8 字节的二进制标头添加到消息中，根据需要为 RNIF 1.1 消息。  
  
-   编码的消息部分，并计算摘要。  
  
-   将加密的负载 （服务内容加附件）、 或负载容器 （服务内容加服务标头加附件）。 如果设置了**编码所有端口**上设置**协议**到贸易合作伙伴协议的选项卡`False`，编码器将加密只对负载。 如果设置了**编码所有端口**将设置为`True`，编码器将加密负载容器。  
  
 有关本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MIME/SMIME 编码器，请参阅 BizTalk Server 帮助中的"MIME/SMIME 的编码器管道组件"。  
  
## <a name="message-flow"></a>消息流  
 消息流通过 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 发送管道的步骤如下：  
  
1.  如果设置了**将所有部分都编码**设置到贸易合作伙伴协议的`True`，MIME / SMIME 编码器将对所有消息部分进行都都编码。 它将使用在中设置的编码方法`Encoding`协议的属性。  
  
2.  有关 RNIF 2.01，如果消息已操作消息并且没有附件，编码器将执行以下操作为每个附件：  
  
    1.  如果附件是二进制的编码器将对其进行编码。  
  
    2.  编码器将生成附件的内容 ID。  
  
    3.  编码器将创建附件的 MIME 部分。  
  
3.  管道加密消息部分，并生成 RNIF 消息，具体取决于的设置为 RNIF 2.01**是否要求永久保密**（作为在过程配置设置中设置）：  
  
    1.  如果设置了**是否要求永久保密**到**负载**，编码器将加密服务内容和附件。 服务标头、 传递标头和前导码构造最终 RNIF 消息，然后将添加汇编程序。  
  
    2.  如果设置了**是否要求永久保密**到**负载容器**，编码器将加密服务标头、 服务内容和附件。 传递标头和前导码构造最终 RNIF 消息，然后将添加汇编程序。  
  
    3.  如果设置了**是否要求永久保密**到**无**，汇编程序对服务内容和 （不带附件中添加服务标头、 传递标头和前导码加密） 构造最终 RNIF 消息。  
  
4.  对于 RNIF 1.1 汇编程序将构造不加密最后一 RNIF 条消息。  
  
5.  编码器将在下面的示例对消息进行签名：  
  
    1.  消息是信号消息，与**不可否认性所需**属性 （在过程配置设置） 是`True`。  
  
    2.  此消息是操作消息中，与**的起点和内容的不可否认性**属性 （在过程配置设置） 是`True`。  
  
6.  有关 RNIF 2.01，编码器将计算的 MIME 消息，第一个正文部分的摘要，并保留了摘要。 它将计算使用在中设置的方法的摘要`Digest`贸易合作伙伴协议 （sha-1 或 MD5） 中的方法属性。  
  
## <a name="see-also"></a>另请参阅  
 [BTARN 中的消息处理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)