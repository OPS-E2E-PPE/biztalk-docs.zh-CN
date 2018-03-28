---
title: 了解在使用 WCF LOB 适配器 SDK 创建的适配器上的 WCF 安全性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1ee402b-ffda-42c1-8d85-d7cbe073a307
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baf0c62c3d0c37c1f69cb944112ff832dade5ec4
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="understand-wcf-security-on-the-adapter-created-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="3a348-102">了解在使用 WCF LOB 适配器 SDK 创建的适配器上的 WCF 安全</span><span class="sxs-lookup"><span data-stu-id="3a348-102">Understand WCF security on the adapter created with the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="3a348-103">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]扩展[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道体系结构，并依赖于消息传送基础结构和它所提供的 API。</span><span class="sxs-lookup"><span data-stu-id="3a348-103">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] extends the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] channel architecture and relies on the messaging infrastructure and the API that it provides.</span></span>  <span data-ttu-id="3a348-104">WCF LOB 适配器需要建立与目标系统的连接，因此需使用身份验证和使目标系统连接所需的其他安全信息配置适配器。</span><span class="sxs-lookup"><span data-stu-id="3a348-104">A WCF LOB adapter needs to establish a connection to target systems, and hence it is necessary to configure the adapter with authentication and other security information required to make the target system connections.</span></span>  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]<span data-ttu-id="3a348-105"> 是一个分布式编程平台，基于可以通过许多不同的节点、 SOAP 中介、 防火墙和可能 Internet 途中从出差业务线系统的适配器和到客户端的 SOAP 消息。</span><span class="sxs-lookup"><span data-stu-id="3a348-105"> is a distributed programming platform based on SOAP messages that can travel through many different nodes, SOAP intermediaries, firewalls, and potentially the Internet en-route from the line-of-business system to the adapter and on to the client.</span></span> <span data-ttu-id="3a348-106">这可能会存在大量不同的安全威胁到你的适配器和部署方案。</span><span class="sxs-lookup"><span data-stu-id="3a348-106">This could present a number of different security threats to your adapter and deployment scenario.</span></span>  
  
 <span data-ttu-id="3a348-107">安全性中扮演企业体系结构的任何解决方案中的主要部分。</span><span class="sxs-lookup"><span data-stu-id="3a348-107">Security plays a major part in any enterprise architecture solution.</span></span> <span data-ttu-id="3a348-108">你可以利用保密性、 完整性、 身份验证和 WCF 安全模型，来帮助保护免受安全威胁的适配器中提供的授权功能。</span><span class="sxs-lookup"><span data-stu-id="3a348-108">You can leverage the confidentiality, integrity, authentication, and authorization features provided in the WCF security model to help secure the adapter from security threats.</span></span> <span data-ttu-id="3a348-109">你还必须考虑的传输和消息级别之间的适配器和目标系统，以防这两个实体之间的通信的安全。</span><span class="sxs-lookup"><span data-stu-id="3a348-109">You must also consider the transport and message-level security between the adapter and the target system to protect the communication between these two entities.</span></span> <span data-ttu-id="3a348-110">即使 WCF 提供了一套丰富的 WS-\* 规范，实现这些高级适配器中的标准将取决于业务线系统提供的功能的安全。</span><span class="sxs-lookup"><span data-stu-id="3a348-110">Even though WCF provides a rich set of WS-\* specifications, implementation of these advanced security standards in your adapter will depend on the capabilities provided by the line-of-business system.</span></span>  
  
 <span data-ttu-id="3a348-111">有关详细信息[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]安全包括概述、 概念、 常见方案和最佳实践，请参阅[Windows Communication Foundation 安全性](https://msdn.microsoft.com/library/ms732362.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3a348-111">For more information about [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] security including an overview, concepts, common scenarios, and best practices, see [Windows Communication Foundation Security](https://msdn.microsoft.com/library/ms732362.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3a348-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a348-112">See Also</span></span>  
 [<span data-ttu-id="3a348-113">规划和设计使用 WCF LOB 适配器 SDK 的适配器</span><span class="sxs-lookup"><span data-stu-id="3a348-113">Plan and design an adapter using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)