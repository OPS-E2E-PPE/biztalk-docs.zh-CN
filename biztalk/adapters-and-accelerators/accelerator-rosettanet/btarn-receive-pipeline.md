---
title: BTARN 接收管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53a9b9dd410a6a136b37ef506c9bc975f563a11a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284920"
---
# <a name="btarn-receive-pipeline"></a>BTARN 接收管道
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]执行使用 RNIFReceive 管道 (RNIFReceive.btp) 接收到 RosettaNet 实现框架 (RNIF) 消息。 接收管道包括以下组件：  
  
-   ReceiveMessageNonRepudiate  
  
-   RNMimeDecoder (MIME Preprocessor/Decoder)  
  
-   RNDAsm （XML 拆装器）  
  
-   RNPartyRes （参与方解析组件）  
  
-   MessageUpdater  
  
## <a name="receivemessagenonrepudiate"></a>ReceiveMessageNonRepudiate  
 此组件将接收到的消息存储在 MessageStorageIn 表中。 此组件在执行所需的 RNIF 标准的不可否认处理。  
  
## <a name="rnmimedecoder"></a>RNMimeDecoder  
 此组件为基础上本机 BizTalk Server MIME 预处理器/解码器。 RNMimeDecoder 添加 RNIF 处理的以下功能：  
  
- 对于 RNIF 2.01 解密服务内容和附件，它们是否存在。  
  
- 对于 RNIF 1.1 处理 8 字节标头和有效负载的末尾的分离的签名标头。  
  
  详细了解本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]预处理器/解码器，请参阅"MIME/SMIME 解码器管道组件"部分中 BizTalk Server 帮助。  
  
## <a name="rndasm"></a>RNDAsm  
 此组件基于本机 BizTalk Server XML 拆装器。 RNDAsm 添加 RNIF 处理的以下功能：  
  
- 如果传入文档 DOCTYPE 标头，此组件将从其生成命名空间，并将传入文档中的所有节点都移动到该命名空间。  
  
- 执行消息关联，以确定传入消息是否重复，并且如果消息是一个重复，将生成一条错误消息。  
  
- 将附件存储为消息的其他部分。  
  
- 升级消息属性。  
  
  详细了解本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]拆装器，请参阅 BizTalk Server 帮助中的"XML 的拆装器管道组件"。  
  
## <a name="rnpartyres"></a>RNPartyRes  
 此组件基于本机的 BizTalk Server 参与方解析组件。 RNPartyRes 添加 RNIF 处理的以下功能：  
  
- 如果传入消息进行签名到 BizTalk 参与方，映射发件人证书。 如果未签名的传入消息，并且贸易合作伙伴协议允许这样做，此组件检索发送方从传递头为 RNIF 2.01 或服务头 RNIF 1.1。  
  
- 验证存在发件人和发件人已与本组织的贸易合作伙伴协议。  
  
  详细了解本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]参与方解析组件，请参阅 BizTalk Server 帮助中的"参与方的解析管道组件"。  
  
## <a name="messageupdater"></a>MessageUpdater  
 此组件将添加为 RNIF 处理的以下功能：  
  
-   使用 PIP 代码、 PIP 版本、 源参与方、 目标参与方和消息跟踪 ID 的网络消息，则 ReceiveMessageNonRepudiate 组件将由存储有关的详细信息更新 MessageStorageIn 表。  
  
-   如果 PIP 不要求不可否认，将标记为删除，设置记录`ToBePurged = True`。  
  
## <a name="message-flow"></a>消息流  
 消息流通过[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]接收管道是按如下所示：  
  
1. HTTP 适配器接收 RNIF 1.1 对象或通过 HTTP POST 的 RNIF 2.01 业务消息。  
  
2. 如果适配器已成功接收消息，适配器将提取 RosettaNet 对象或业务消息，并将其路由到接收管道。  
  
3. 如果对象或业务消息已签名，MIME 预处理器/解码器将删除签名。  
  
4. 如果签名有效，拆装器将读取该前导码。  
  
5. 如果消息是操作消息，并且是必需的不可否认性 (**和内容的不可否认**流程配置设置中的设置是`True`)，则解码器计算并持久保留该摘要。  
  
6. 拆装器将验证该前导码 （使用消息 （消息） 指南和全局变量中的前导头架构）。  
  
7. 对于 RNIF 2.01，拆装器读取传递头中，并验证在全局变量中使用消息的指导原则和交付标头架构的标头。  
  
8. 对于 RNIF 2.01，拆装器从传递头中提取合作伙伴信息并检查要验证属于合作伙伴的签名。  
  
9. 对于 RNIF 2.01 负载进行加密，如果解码器解密负载容器。  
  
10. 拆装器读取服务头中，并验证在全局变量中使用消息的指导原则和服务头架构的标头。  
  
11. 对于 RNIF 1.1，拆装器从服务头中提取合作伙伴信息并检查要验证属于合作伙伴的签名。  
  
12. 拆装器将检查合作伙伴是否已获得 PIP 的授权。 如果没有，拆装器将回复 HTTP POST HTTP 403 状态消息，如有必要，并发布错误。  
  
13. 如果消息是签名的操作消息和**和内容的不可否认**设置为`True`，则 ReceiveMessageNonRepudiate 组件将仍然存在 MessageStorageIn 表中的原始消息。  
  
14. 如果消息是签名的信号消息并**要求不可否认**设置为`True`，则 ReceiveMessageNonRepudiate 组件将仍然存在 MessageStorageIn 表中的信号消息。  
  
15. 如果消息已在不可否认的 MessageStorageIn 表中保持不变，MessageUpdater 使用消息的过程配置的属性更新 MessageStorageIn 表。  
  
16. 如果消息是与以前处理过的操作消息时，重复的操作消息[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将发布一个错误。  
  
17. 为 RNIF 2.01 解码器将解密有效负载，如果对操作消息进行加密，并且没有匹配的 HTTP 的同步和 PIP 的同步要求。  
  
18. 拆装器读取服务内容，并对它使用消息的指导原则和架构进行验证。  
  
19. 对于 RNIF 2.01，该清单是有效和存在的内容 ID，则将验证拆装器。  
  
20. 对于 RNIF 2.01，拆装器将读取任何附件。  
  
21. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将路由 RosettaNet 标头、 服务内容和附件到公用流程。  
  
## <a name="see-also"></a>请参阅  
 [BTARN 中的消息处理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)