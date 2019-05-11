---
title: 了解使用 WCF LOB 适配器 SDK 创建的适配器上的 WCF 安全性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1ee402b-ffda-42c1-8d85-d7cbe073a307
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b34be29b74b10d5b9768cff5bc40a26abe41dce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362723"
---
# <a name="understand-wcf-security-on-the-adapter-created-with-the-wcf-lob-adapter-sdk"></a>了解使用 WCF LOB 适配器 SDK 创建的适配器上的 WCF 安全性
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]扩展了[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道体系结构，并依赖于消息传送基础结构和它所提供的 API。  WCF LOB 适配器需要建立与目标系统的连接，因此它需要使用身份验证和其他安全信息，使目标系统连接所需配置适配器。  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 分布式编程平台为基础可以通过许多不同的节点、 SOAP 中介，防火墙和可能 Internet 途中从传输业务线系统与适配器和到客户端的 SOAP 消息。 这可能会存在不同的安全威胁到您的适配器和部署方案的风险。  
  
 安全在任何企业体系结构解决方案中扮演的主要部分。 您可以利用机密性、 完整性、 身份验证和授权功能来帮助保护免受安全威胁的适配器的 WCF 安全模型中提供。 您还必须考虑的传输和消息级安全性来保护这两个实体之间的通信的适配器和目标系统之间。 即使 WCF 提供了一套丰富的 WS-* 规范，这些实现高级的安全性标准中您的适配器将取决于业务线系统提供的功能。  
  
 有关详细信息[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]安全包括概述、 概念、 常见方案和最佳实践，请参阅[Windows Communication Foundation 安全性](https://msdn.microsoft.com/library/ms732362.aspx)。
  
## <a name="see-also"></a>请参阅  
 [规划和设计适配器使用 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)