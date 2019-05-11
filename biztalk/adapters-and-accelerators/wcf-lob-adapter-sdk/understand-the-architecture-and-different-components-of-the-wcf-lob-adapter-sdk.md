---
title: 了解体系结构以及 WCF LOB 适配器 SDK 的不同组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 293189be-61d7-44f4-8ba6-e5550516d9b4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12ddf6f070d96ca24ab68dd30aa8205e78599922
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362912"
---
# <a name="understand-the-architecture-and-different-components-of-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="f36e5-102">了解体系结构以及 WCF LOB 适配器 SDK 的不同组件</span><span class="sxs-lookup"><span data-stu-id="f36e5-102">Understand the architecture and different components of the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="f36e5-103">阅读有关[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]可帮助了解不同的组件和 WCF 的角色。</span><span class="sxs-lookup"><span data-stu-id="f36e5-103">Read about the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] to help understand the different components, and the role of WCF.</span></span>  

<span data-ttu-id="f36e5-104">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是一系列工具和组件，用于开发可重用、 元数据丰富的业务线系统的适配器提供一致的框架。</span><span class="sxs-lookup"><span data-stu-id="f36e5-104">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is a collection of tools and components that provide a consistent framework for developing reusable, metadata-rich adapters for line-of-business systems.</span></span> <span data-ttu-id="f36e5-105">适配器使用编写[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]作为自定义 WCF 绑定和可供 WCF 支持的客户端。</span><span class="sxs-lookup"><span data-stu-id="f36e5-105">Adapters written using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] are surfaced as custom WCF bindings and can be consumed by a WCF-capable client.</span></span>  
  
## <a name="features-and-components-overview"></a><span data-ttu-id="f36e5-106">功能和组件概述</span><span class="sxs-lookup"><span data-stu-id="f36e5-106">Features and components overview</span></span>
<span data-ttu-id="f36e5-107">[什么是 Windows Communication Foundation 行业务线适配器 SDK](what-is-the-windows-communication-foundation-line-of-business-adapter-sdk.md)提供 SDK，构成组件的功能的概述并介绍了元数据、 连接管理以及介绍常见的 WCF 术语。</span><span class="sxs-lookup"><span data-stu-id="f36e5-107">[What Is the Windows Communication Foundation Line of Business Adapter SDK](what-is-the-windows-communication-foundation-line-of-business-adapter-sdk.md) provides an overview of the features and components that make up the SDK, and describes the metadata, connection management, and describes the common WCF terms.</span></span>

## <a name="role-of-wcf"></a><span data-ttu-id="f36e5-108">WCF 的角色</span><span class="sxs-lookup"><span data-stu-id="f36e5-108">Role of WCF</span></span>  
<span data-ttu-id="f36e5-109">[读取 WCF 如何使用 WCF LOB 适配器 SDK](read-how-wcf-is-used-by-the-wcf-lob-adapter-sdk.md)介绍了使用 SDK 和 WCF 的关系。</span><span class="sxs-lookup"><span data-stu-id="f36e5-109">[Read how WCF is used by the WCF LOB Adapter SDK](read-how-wcf-is-used-by-the-wcf-lob-adapter-sdk.md) explains the relationship with the SDK and WCF.</span></span>

## <a name="architecture-overview"></a><span data-ttu-id="f36e5-110">体系结构概述</span><span class="sxs-lookup"><span data-stu-id="f36e5-110">Architecture Overview</span></span>  
<span data-ttu-id="f36e5-111">[体系结构概述](architecture-overview-of-the-wcf-lob-adapter-sdk.md)descrbied 内部体系结构和 WCF LOB 适配器 SDK 的主要组件。</span><span class="sxs-lookup"><span data-stu-id="f36e5-111">[Architecture overview ](architecture-overview-of-the-wcf-lob-adapter-sdk.md) descrbied the internal architecture and the main components of WCF LOB Adapter SDK.</span></span>
 
## <a name="connection-handler-metadata-custom-and-core-components"></a><span data-ttu-id="f36e5-112">连接、 处理程序、 元数据、 自定义和核心组件</span><span class="sxs-lookup"><span data-stu-id="f36e5-112">Connection, handler, metadata, custom, and core components</span></span>
<span data-ttu-id="f36e5-113">[WCF LOB 适配器 SDK 的密钥组件](key-components-of-the-wcf-lob-adapter-sdk.md)介绍这些不同组件。</span><span class="sxs-lookup"><span data-stu-id="f36e5-113">[Key Components of the WCF LOB Adapter SDK](key-components-of-the-wcf-lob-adapter-sdk.md) describes these different components.</span></span>

## <a name="biztalk-server-and-the-sdk"></a><span data-ttu-id="f36e5-114">BizTalk Server 和 SDK</span><span class="sxs-lookup"><span data-stu-id="f36e5-114">BizTalk Server and the SDK</span></span>  
[<span data-ttu-id="f36e5-115">用于 Oracle 数据库和 WCF LOB 适配器 SDK 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="f36e5-115">BizTalk Adapter for Oracle Database and the WCF LOB Adapter SDK</span></span>](../adapter-oracle-database/architecture-overview-of-the-biztalk-adapter-for-oracle-database.md)   
  
## <a name="see-also"></a><span data-ttu-id="f36e5-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="f36e5-116">See Also</span></span>  
 [<span data-ttu-id="f36e5-117">BizTalk Server 入门</span><span class="sxs-lookup"><span data-stu-id="f36e5-117">Getting started with BizTalk Server</span></span>](../../core/getting-started-with-biztalk-server.md)