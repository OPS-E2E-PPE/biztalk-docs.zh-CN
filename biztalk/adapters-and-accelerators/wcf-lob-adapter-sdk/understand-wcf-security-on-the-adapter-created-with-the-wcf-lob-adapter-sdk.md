---
title: "了解在使用 WCF LOB 适配器 SDK 创建的适配器上的 WCF 安全性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1ee402b-ffda-42c1-8d85-d7cbe073a307
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baf0c62c3d0c37c1f69cb944112ff832dade5ec4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="understand-wcf-security-on-the-adapter-created-with-the-wcf-lob-adapter-sdk"></a>了解在使用 WCF LOB 适配器 SDK 创建的适配器上的 WCF 安全
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]扩展[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道体系结构，并依赖于消息传送基础结构和它所提供的 API。  WCF LOB 适配器需要建立与目标系统的连接，因此需使用身份验证和使目标系统连接所需的其他安全信息配置适配器。  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]是一个分布式编程平台，基于可以通过许多不同的节点、 SOAP 中介、 防火墙和可能 Internet 途中从出差业务线系统的适配器和到客户端的 SOAP 消息。 这可能会存在大量不同的安全威胁到你的适配器和部署方案。  
  
 安全性中扮演企业体系结构的任何解决方案中的主要部分。 你可以利用保密性、 完整性、 身份验证和 WCF 安全模型，来帮助保护免受安全威胁的适配器中提供的授权功能。 你还必须考虑的传输和消息级别之间的适配器和目标系统，以防这两个实体之间的通信的安全。 即使 WCF 提供了一套丰富的 WS-* 规范，实现这些高级适配器中的标准将取决于业务线系统提供的功能的安全。  
  
 有关详细信息[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]安全包括概述、 概念、 常见方案和最佳实践，请参阅[Windows Communication Foundation 安全性](https://msdn.microsoft.com/library/ms732362.aspx)。
  
## <a name="see-also"></a>另请参阅  
 [规划和设计使用 WCF LOB 适配器 SDK 的适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)