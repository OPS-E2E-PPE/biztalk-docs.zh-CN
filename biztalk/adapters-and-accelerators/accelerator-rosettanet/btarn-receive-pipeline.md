---
title: "BTARN 接收管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BTARN, receive pipelines
- RNMimeDecoder component
- ReceiveMessageNonRepudiate component
- RNDAsm component
- receive pipelines, message flow
- RNPartyRes component
- receive pipelines, BTARN
- MessageUpdater component
- messages, message flow
ms.assetid: 811f2a6a-ddd2-49cc-a00b-4c9d0110a0d1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db4bc69348cfb99b5e7cebb07c65e05a0513cd0e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="btarn-receive-pipeline"></a>BTARN 接收管道
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]执行 RosettaNet 实现框架 (RNIF) 与 RNIFReceive 管道 (RNIFReceive.btp) 都接收到消息。 接收管道包括以下组件：  
  
-   ReceiveMessageNonRepudiate  
  
-   RNMimeDecoder（MIME 预处理器/解码器）  
  
-   RNDAsm（XML 拆装器）  
  
-   RNPartyRes（参与方解析组件）  
  
-   MessageUpdater  
  
## <a name="receivemessagenonrepudiate"></a>ReceiveMessageNonRepudiate  
 此组件 MessageStorageIn 表中存储对收到的消息。 此组件执行由 RNIF 标准所需的不可否认性处理。  
  
## <a name="rnmimedecoder"></a>RNMimeDecoder  
 此组件基于上本机 BizTalk Server MIME 预处理器/解码器。 RNMimeDecoder 添加 RNIF 处理的以下功能：  
  
-   有关 RNIF 2.01 解密的服务内容和附件，如果它们存在。  
  
-   针对 RNIF 1.1 处理 8 字节标头和负载末尾的分离的签名标头。  
  
 有关本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]预处理器/解码器，请参阅 BizTalk Server 帮助中的"MIME/SMIME 的解码器管道组件"。  
  
## <a name="rndasm"></a>RNDAsm  
 此组件基于本机的 BizTalk Server XML 反汇编程序。 RNDAsm 添加 RNIF 处理的以下功能：  
  
-   如果传入的文档的 DOCTYPE 标头，此组件将从其生成命名空间，并将传入的文档中的所有节点都移至该命名空间。  
  
-   执行消息关联，以确定传入消息是否有重复，并生成错误消息，如果消息已重复。  
  
-   将附件存储为消息的其他部分。  
  
-   提升消息属性。  
  
 有关本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]反汇编程序，请参阅 BizTalk Server 帮助中的"XML 的反汇编程序管道组件"。  
  
## <a name="rnpartyres"></a>RNPartyRes  
 此组件基于本机的 BizTalk Server 参与方解析组件。 RNPartyRes 添加 RNIF 处理的以下功能：  
  
-   如果传入的消息登录到 BizTalk 方会将发件人证书映射。 如果传入的消息未进行签名，并为其允许的贸易合作伙伴协议，该组件检索发件人方从传递标头 RNIF 2.01 或服务标头 RNIF 1.1。  
  
-   验证发件人存在和发件人已与主组织贸易合作伙伴协议。  
  
 有关本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]方解析组件，请参阅 BizTalk Server 帮助中的"方的解析管道组件"。  
  
## <a name="messageupdater"></a>MessageUpdater  
 此组件将添加 RNIF 处理的以下功能：  
  
-   使用 PIP 代码、 PIP 版本、 源方、 目标方和已存储的 ReceiveMessageNonRepudiate 组件的网络消息的消息跟踪 ID 有关的详细信息更新 MessageStorageIn 表。  
  
-   如果 PIP 不要求不可否认性，则将相应记录标记为删除，设置 `ToBePurged = True`。  
  
## <a name="message-flow"></a>消息流  
 消息流通过 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 接收管道的步骤如下：  
  
1.  HTTP 适配器接收 RNIF 1.1 对象或通过 HTTP POST RNIF 2.01 业务消息。  
  
2.  如果适配器成功接收消息时，适配器提取 RosettaNet 对象或业务消息，并将它路由到接收管道。  
  
3.  如果将对象或业务消息进行签名，MIME 预处理器/解码器中删除签名。  
  
4.  如果签名有效，拆装器会读取该前导码。  
  
5.  如果消息已操作消息，并且需要不可否认性 (**的起点和内容的不可否认性**过程配置设置中的设置是`True`)，解码器计算并仍然存在摘要。  
  
6.  反汇编程序验证该前导码 （与消息 （消息） 的指导原则和全局变量中的前导码架构）。  
  
7.  有关 RNIF 2.01 反汇编程序读取传递标头，并验证在全局变量中使用的消息准则和传递标头架构的标头。  
  
8.  有关 RNIF 2.01 反汇编程序从传递头中提取的合作伙伴信息，并检查要验证属于合作伙伴的签名。  
  
9. 有关 RNIF 2.01 负载进行加密，如果解码器解密负载容器。  
  
10. 反汇编程序读取服务标头，并验证在全局变量中使用的消息准则和服务标头架构的标头。  
  
11. RNIF 1.1，拆装器提取合作伙伴信息从服务标头，并检查要验证属于合作伙伴的签名。  
  
12. 拆装器检查是否得到的 PIP 授权合作伙伴。 如果没有，拆装器将答复 HTTP 自检 HTTP 403 条状态消息，如有必要，并会产生错误。  
  
13. 如果消息已签名的操作消息和**的起点和内容的不可否认性**设置为`True`，ReceiveMessageNonRepudiate 组件仍然存在 MessageStorageIn 表中的原始消息。  
  
14. 如果消息已签名的信号消息和**不可否认性所需**设置为`True`，ReceiveMessageNonRepudiate 组件仍然存在 MessageStorageIn 表中的信号消息。  
  
15. 如果消息已不可否认性 MessageStorageIn 表中保持不变，MessageUpdater 使用消息的过程配置的属性更新 MessageStorageIn 表。  
  
16. 如果重复收到了以前处理过的操作消息，则 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将发布出错信息。  
  
17. 有关 RNIF 2.01 解码器将解密负载，如果操作消息进行加密，并且没有之间的 HTTP 的同步和 PIP 的同步要求匹配。  
  
18. 反汇编程序读取服务内容，并对它使用消息的指导原则和架构进行验证。  
  
19. 有关 RNIF 2.01 拆装器验证清单有效的内容 ID 存在。  
  
20. 对于 RNIF 2.01 拆装器将读取的任何附件。  
  
21. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将 RosettaNet 头、服务内容和附件路由到公用流程。  
  
## <a name="see-also"></a>另请参阅  
 [BTARN 中的消息处理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)