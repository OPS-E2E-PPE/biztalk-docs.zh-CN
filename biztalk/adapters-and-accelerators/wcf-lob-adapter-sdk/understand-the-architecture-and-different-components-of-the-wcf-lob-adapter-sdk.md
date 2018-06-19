---
title: 了解的体系结构和不同组件的 WCF LOB 适配器 SDK |Microsoft 文档
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
ms.openlocfilehash: feea57176512bb42306feb8b60a10a887a020145
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223517"
---
# <a name="understand-the-architecture-and-different-components-of-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="c803c-102">了解的体系结构和不同组件的 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="c803c-102">Understand the architecture and different components of the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="c803c-103">阅读有关[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]以帮助了解不同的组件和 WCF 的角色。</span><span class="sxs-lookup"><span data-stu-id="c803c-103">Read about the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] to help understand the different components, and the role of WCF.</span></span>  

<span data-ttu-id="c803c-104">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是一套工具和开发的业务线系统的可重用、 元数据丰富适配器提供一致的 framework 的组件。</span><span class="sxs-lookup"><span data-stu-id="c803c-104">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is a collection of tools and components that provide a consistent framework for developing reusable, metadata-rich adapters for line-of-business systems.</span></span> <span data-ttu-id="c803c-105">适配器使用编写[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]作为自定义 WCF 绑定，且可由 WCF 支持的客户端使用。</span><span class="sxs-lookup"><span data-stu-id="c803c-105">Adapters written using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] are surfaced as custom WCF bindings and can be consumed by a WCF-capable client.</span></span>  
  
## <a name="features-and-components-overview"></a><span data-ttu-id="c803c-106">功能和组件概述</span><span class="sxs-lookup"><span data-stu-id="c803c-106">Features and components overview</span></span>
<span data-ttu-id="c803c-107">[什么是 Windows Communication Foundation 行的业务适配器 SDK](what-is-the-windows-communication-foundation-line-of-business-adapter-sdk.md)提供的功能和组件构成了 SDK 的概述和说明的元数据和连接管理，并说明常用的 WCF 术语。</span><span class="sxs-lookup"><span data-stu-id="c803c-107">[What Is the Windows Communication Foundation Line of Business Adapter SDK](what-is-the-windows-communication-foundation-line-of-business-adapter-sdk.md) provides an overview of the features and components that make up the SDK, and describes the metadata, connection management, and describes the common WCF terms.</span></span>

## <a name="role-of-wcf"></a><span data-ttu-id="c803c-108">WCF 的角色</span><span class="sxs-lookup"><span data-stu-id="c803c-108">Role of WCF</span></span>  
<span data-ttu-id="c803c-109">[读取 WCF LOB 适配器 SDK 如何使用 WCF](read-how-wcf-is-used-by-the-wcf-lob-adapter-sdk.md)说明与 SDK 和 WCF 之间的关系。</span><span class="sxs-lookup"><span data-stu-id="c803c-109">[Read how WCF is used by the WCF LOB Adapter SDK](read-how-wcf-is-used-by-the-wcf-lob-adapter-sdk.md) explains the relationship with the SDK and WCF.</span></span>

## <a name="architecture-overview"></a><span data-ttu-id="c803c-110">体系结构概述</span><span class="sxs-lookup"><span data-stu-id="c803c-110">Architecture Overview</span></span>  
<span data-ttu-id="c803c-111">[体系结构概述](architecture-overview-of-the-wcf-lob-adapter-sdk.md)descrbied 内部体系结构和 WCF LOB 适配器 SDK 的主要组件。</span><span class="sxs-lookup"><span data-stu-id="c803c-111">[Architecture overview ](architecture-overview-of-the-wcf-lob-adapter-sdk.md) descrbied the internal architecture and the main components of WCF LOB Adapter SDK.</span></span>
 
## <a name="connection-handler-metadata-custom-and-core-components"></a><span data-ttu-id="c803c-112">连接、 处理程序、 元数据、 自定义，和核心组件</span><span class="sxs-lookup"><span data-stu-id="c803c-112">Connection, handler, metadata, custom, and core components</span></span>
<span data-ttu-id="c803c-113">[WCF LOB 适配器 SDK 密钥组件](key-components-of-the-wcf-lob-adapter-sdk.md)描述了这些不同组件。</span><span class="sxs-lookup"><span data-stu-id="c803c-113">[Key Components of the WCF LOB Adapter SDK](key-components-of-the-wcf-lob-adapter-sdk.md) describes these different components.</span></span>

## <a name="biztalk-server-and-the-sdk"></a><span data-ttu-id="c803c-114">BizTalk Server 和 SDK</span><span class="sxs-lookup"><span data-stu-id="c803c-114">BizTalk Server and the SDK</span></span>  
[<span data-ttu-id="c803c-115">用于 Oracle 数据库和 WCF LOB 适配器 SDK 的 BizTalk Adapter</span><span class="sxs-lookup"><span data-stu-id="c803c-115">BizTalk Adapter for Oracle Database and the WCF LOB Adapter SDK</span></span>](../adapter-oracle-database/architecture-overview-of-the-biztalk-adapter-for-oracle-database.md)   
  
## <a name="see-also"></a><span data-ttu-id="c803c-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c803c-116">See Also</span></span>  
 [<span data-ttu-id="c803c-117">BizTalk Server 入门</span><span class="sxs-lookup"><span data-stu-id="c803c-117">Getting started with BizTalk Server</span></span>](../../core/getting-started-with-biztalk-server.md)