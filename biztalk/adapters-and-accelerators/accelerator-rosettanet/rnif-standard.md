---
title: "RNIF 标准 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RNIF, message definitions
- RNIF, messaging framework patterns
- messages, message definitions
- RNIF, standards
- messages, messaging framework patterns
ms.assetid: d39a9683-1ef5-462b-9472-4e30fe873f7d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6b29d8c9c770893fd78769b86266ce33e31a336
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="rnif-standard"></a>RNIF 标准
RosettaNet 实现框架 (RNIF) 标准定义系统传输 RosettaNet 消息的方式。 RNIF 标准是一个强大的传输、路由、打包和安全标准。 所有 RosettaNet 消息传送系统都必须符合 RNIF 标准，才能获得 RosettaNet 证书。  
  
 此标准定义了消息结构、确认需求、多用途 Internet 邮件扩展 (MIME) 编码以及数字签名。 核心标准包括身份验证、授权、加密以及不可否认性的要求。 RNIF 标准基于 HTTP、MIME 以及 XML 标准。 RNIF 标准不指定平台，也不指定所支持的应用程序。  
  
 [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]实现两个版本的 RNIF: RNIF 规范 v02.00.01 和 RNIF 规范 1.1 版。 RNIF 2.01 添加超出支持的 RNIF 1.1，包括加密、 附件和同步事务的重要功能。 RNIF 2.0 并不向后兼容 RNIF 1.1。  
  
## <a name="messaging-framework-patterns"></a>消息传递框架模式  
 下表给出了消息传送框架模式和同步消息交换的 RNIF 支持。 单操作消息不涉及响应，而双操作消息则包括请求和响应。  
  
|框架|模式|同步 /<br />异步|  
|---------------|-------------|---------------------------------|  
|RNIF 1.1|通知|异步|  
|RNIF 1.1|事务|异步|  
|RNIF 2.0|双操作|同步|  
|RNIF 2.0|双操作|异步|  
|RNIF 2.0|单操作|同步|  
|RNIF 2.0|单操作|异步|  
  
## <a name="message-definitions"></a>消息定义  
 RNIF 1.1 和 RNIF 2.01 对 RosettaNet 消息的定义有所不同。 这些区别包括：处理附件的方式、安全/多用途 Internet 邮件扩展 (SMIME) 信封、传递头以及 MIME 打包。 特别是 RNIF 2.01 还包括附件；另外，RNIF 2.01 添加了传递头，而 RNIF 1.1 不支持传递头。  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不支持*RNIF 1.1 的技术建议*RosettaNet 组织 （一个用于附件支持，一个用于同步的响应） 发布。  
  
 系统将 RNIF 1.1 和 RNIF 2.01 消息的各部分用于标识参与方、路由以及标识服务级。 在读取并答复服务内容正文（消息的主要内容）之前，每个参与方都必须成功地填充或解释头值。  
  
 下图描述了 RNIF 1.1 和 RNIF 2.01 消息定义。  
  
 ![&#60;无更改 &#62;] (../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-rnif-message-definitions.gif "RN3_RNIF_Message_Definitions")  
  
 在 RNIF 1.1 消息中，版本号表明 RNIF 版本。 内容长度是 RosettaNet 服务消息的长度。 服务消息（包括前导头、服务头以及服务内容）是一个 Multipart/related MIME 实体。 签名长度是以字节为单位计算的签名长度。 如果存在签名，则该签名为服务消息字段的一个公钥加密标准 (PKCS) #7 签名。  
  
 RNIF 2.01 包括一个不依赖传输协议的容器，它将业务负载、头组件以及系统将在程序包中交换的其他元素封装在一起。 如同为 RNIF 2.01 所定义的，RosettaNet 业务消息包括前导头、传递头、服务头以及服务内容。 系统必须根据 RosettaNet 标准文档类型定义 (DTD) 语法验证规则，对照包含该业务消息的文档类型架构，验证该消息的所有元素。 服务内容可以是操作消息或信号消息。 如果服务内容是操作消息，则此消息可以包括一个或多个附件。  
  
 RosettaNet 业务消息是一个 Multipart/related MIME 实体。 如上图所示，头和服务内容使用 MIME Multipart/related 结构打包在一起，类似于 RNIF 1.1 打包方案。 系统可选择对 RosettaNet 业务消息进行数字签名。 在 RNIF 1.1 中，可以使用 RosettaNet 对象 (RNO) 格式实现此目的。 RNIF 2.0 不支持 RNO 格式，而是使用标准 S/MIME 编码。  
  
 系统还可能会对 RNIF 2.01 负载或负载容器进行加密。 要执行此操作，请将要加密的部分绑定到 Multipart/related MIME 实体，然后再进行加密。 之后将产生的 S/MIME 对象打包为 RosettaNet 业务消息的一部分。  
  
 信号消息必须始终为 RosettaNet 定义的信号消息实例。 对于操作消息，RNIF 2.01 规范提供了以第三方定义的格式发送业务操作消息的选项。 RNIF 2.01 服务头还包括用于实现此目的的其他字段，例如标识“标准正文”的字段以及标识此操作消息所遵循规范的版本的字段。  
  
 只有操作消息（也称为业务内容）才可以是非 RosettaNet 消息。 系统必须在 RosettaNet 定义的 PIP 中交换这些消息。 RosettaNet 必须认可这些消息，方法是在 PIP 规范中显式标识认可的第三方操作消息。 此外，贸易伙伴必须在贸易伙伴协议中达成一致，以交换第三方业务内容。 协议必须包括 PIP 负载绑定信息，它标识将用于替换 PIP 中特定操作消息的第三方业务内容。  
  
## <a name="see-also"></a>另请参阅  
 [RosettaNet 和 CIDX 标准消息传送](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md)   
 [RosettaNet Pip](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md)