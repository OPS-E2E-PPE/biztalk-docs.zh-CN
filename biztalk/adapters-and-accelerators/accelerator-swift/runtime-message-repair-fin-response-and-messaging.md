---
title: 运行时，消息修复、 FIN 响应和消息传送 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, about architecture
- architecture
- BizTalk Accelerator for SWIFT, architecture
ms.assetid: c7f34517-6663-44a6-b6ea-6d55fdb08caf
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 539d6f6d7a2b84262750f8b3c6da3c16a67f0de9
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="runtime-message-repair-fin-response-and-messaging"></a>运行时、 消息修复、 FIN 响应和消息传送

## <a name="overview"></a>概述
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] 提供客户和合作伙伴财务行业特定消息传送和连接功能，这有助于加快实施[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为财务组织的中间件。  
  
 通过利用开放标准基于工具和运行时功能的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]若要实现对 SWIFT 类似的消息格式的支持，A4SWIFT 可以减少屏障到采用更新 SWIFT 标准通过采用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为通用中间件集成平台。  
  
 A4SWIFT 和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]减少同时，还通过减少交付应用程序宿主和集成以及工作流的类服务器的企业的总体维护和支持成本降低总拥有成本 (TCO) 到市场时间金融服务行业中的实现。  
  
 你可以广泛的分类与 SWIFT 消息传送和 SWIFT 连接 A4SWIFT 功能。 消息传送的完整 A4SWIFT 结合了分析的 SWIFT 消息和验证 （包括入站/出站批处理）、 消息项和修复 (其中包括与集成[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]作为前端用户工具)，和其他的业务线 (LOB) 应用程序。  
  
 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] 可提供 XSD 架构和完整的验证，包括网络规则，所有 358 的财务 (FIN) 消息。 它还提供入站 debatching。  

## <a name="next-steps"></a>后续步骤  
 本部分包含：  
  
-   [Components](components.md)  
  
-   [BizTalk Accelerator for SWIFT 运行时](biztalk-accelerator-for-swift-runtime.md)  
  
-   [消息修复和新提交](message-repair-and-new-submission.md)  
  
-   [FIN 响应对帐](fin-response-reconciliation.md)  
  
-   [SWIFT 消息](swift-messages.md)

- [ A4SWIFT_* 的已提升属性](a4swift-promoted-properties.md)