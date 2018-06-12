---
title: RNIF 消息处理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RosettaNet Implementation Framework (RNIF)
- RosettaNet, about RosettaNet
- RNIF
- RNIF, non-repudiation
- RNIF, BizTalk Accelerator for RosettaNet
- non-repudiation
- RNIF, about RNIF
- BizTalk Accelerator for RosettaNet, RNIF
- RosettaNet
ms.assetid: 994f15bc-765c-4220-8ab1-176919e9e821
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 810f673b9ae2cf9c6e1b64ccab6a6a541118cbca
ms.sourcegitcommit: 436ebffd959a9c4bdaafd4da9a5843c59a018eb7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2018
ms.locfileid: "34855520"
---
# <a name="rnif-message-processing"></a>RNIF 消息处理
RosettaNet 组织依据 RosettaNet 实现框架 (RNIF) 的规范定义消息交换。 RNIF 定义如何集成系统将传输消息。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 完全实现 RNIF 规范，将该功能添加到什么[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]本机提供的框。  
  
RNIF 通信非常复杂。 执行 RNIF 处理这些公共进程包括各种验证检查和复杂工作流逻辑。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 本机提供此功能。 这样，您便可使用 RosettaNet 兼容系统，而无需重新开发或维护 RNIF 逻辑。  
  
## <a name="btarn-support-for-rnif"></a>BTARN 对 RNIF 的支持  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 支持这两个版本的 RNIF: RNIF 1.1 和 RNIF 2.0 (V02.00.01)。 RNIF 2.0 增加了 RNIF 1.1 所不能支持的重要功能，包括加密、附件和同步事务。 RNIF 2.0 并不向后兼容 RNIF 1.1。  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 可与 RosettaNet Ready RNIF 2.0 兼容。  
  
两个版本对 RosettaNet 消息的定义有所不同。 有关不同的消息容器的详细信息，请参阅[RNIF 标准](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md)。  
  
集成系统执行 RNIF 传输 HTTP/HTTPS 和 SMTP;但是，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]实现仅 HTTP/HTTPS。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 不支持附件和同步事务中 RNIF 1.1。  
  
### <a name="non-repudiation"></a>不可否认性  
RNIF 标准包括对不可否认性的要求。 这涉及到将 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 接收或发送的所有消息的线路格式存储在不可否认性数据库中，这样，便可以合法地证明您已收到或发送了消息。 为此，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]使用中的 MessageStorageIn 表[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]存档数据库对于传入消息和传出消息的同一数据库中的 MessageStorageOut 表。  
  
您可以在流程配置的配置文件中分别设置服务内容和消息确认的不可否认性要求。 如果你设置一个或两个**的起点和内容的不可否认性**和**不可否认性所需**选项到`True`，然后[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将存储以下数据：  
  
|data|目录|  
|----------|--------------|  
|RecordID|存储消息的唯一专用 ID|  
|MessageCategory|请求 (0)、响应 (1) 或信号 (2)|  
|DestinationParty|目标参与方名称|  
|SourceParty|源参与方名称|  
|PIPCode|例如，PIP3A4|  
|PIPVersion|例如，V02.00|  
|MessageContent|二进制格式的消息|  
|MessageTrackingID|消息的消息跟踪 ID|  
|PIPInstanceID|流程的 PIP 实例 ID|  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Accelerator for RosettaNet 将添加到 BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)   
 [PIP 实现](../../adapters-and-accelerators/accelerator-rosettanet/pip-implementation.md)
