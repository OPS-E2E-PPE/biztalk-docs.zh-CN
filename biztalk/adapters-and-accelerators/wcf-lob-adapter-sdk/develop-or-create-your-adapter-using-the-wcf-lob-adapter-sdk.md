---
title: 开发或创建使用 WCF LOB 适配器 SDK 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ca8c03a-1e4a-4077-b4cb-4e184b520bbb
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e7e4c76add25b53a8b3e32707c6a09b92636559
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224717"
---
# <a name="develop-or-create-your-adapter-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="fdad7-102">开发或创建使用 WCF LOB 适配器 SDK 适配器</span><span class="sxs-lookup"><span data-stu-id="fdad7-102">Develop or create your adapter using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="fdad7-103">本部分包含的开发人员正在创建使用适配器的信息[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fdad7-103">This section contains information for developers who are creating adapters using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="fdad7-104">一旦已开发了适配器，它通常由任一.NET 或[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为一种方式访问操作和数据所需的目标业务线系统中的开发人员。</span><span class="sxs-lookup"><span data-stu-id="fdad7-104">Once the adapter has been developed, it is usually consumed by either .NET or [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] developers as a way to access operations and data in a desired target line-of-business system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fdad7-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="fdad7-105">In This Section</span></span>  
  
-   [<span data-ttu-id="fdad7-106">使用 WCF LOB 适配器 SDK 开发最佳做法</span><span class="sxs-lookup"><span data-stu-id="fdad7-106">Development Best Practices using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="fdad7-107">使用 WCF LOB 适配器 SDK 中的 WSDL 代理使用的命名空间</span><span class="sxs-lookup"><span data-stu-id="fdad7-107">Use namespaces with the WSDL-Proxy in the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/use-namespaces-with-the-wsdl-proxy-in-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="fdad7-108">描述与 WCF LOB 适配器 SDK 的 WSDL PortType 文档架构</span><span class="sxs-lookup"><span data-stu-id="fdad7-108">Describe the WSDL PortType Documentation Schema with the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/describe-the-wsdl-porttype-documentation-schema-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="fdad7-109">管理使用 WCF LOB 适配器 SDK 适配器进行版本控制</span><span class="sxs-lookup"><span data-stu-id="fdad7-109">Manage adapter versioning with the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/manage-adapter-versioning-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="fdad7-110">使用服务行为来输入具有 WCF LOB 适配器 SDK 的凭据</span><span class="sxs-lookup"><span data-stu-id="fdad7-110">Use a Service Behavior to enter credentials with the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/use-a-service-behavior-to-enter-credentials-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="fdad7-111">将适配器设置公开为使用 WCF LOB 适配器 SDK 的绑定属性</span><span class="sxs-lookup"><span data-stu-id="fdad7-111">Expose adapter settings as binding property using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/expose-adapter-settings-as-a-binding-property-using-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="fdad7-112">浏览和搜索元数据中使用 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="fdad7-112">Browse and Search Metadata using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/browse-and-search-metadata-using-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="fdad7-113">事务支持</span><span class="sxs-lookup"><span data-stu-id="fdad7-113">Transaction Support</span></span>](../../core/transaction-support.md)  
  
-   [<span data-ttu-id="fdad7-114">承载在 IIS 使用 WCF LOB 适配器 SDK 中的适配器</span><span class="sxs-lookup"><span data-stu-id="fdad7-114">Host an adapter in IIS using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/host-an-adapter-in-iis-using-the-wcf-lob-adapter-sdk.md) 
  
-   [<span data-ttu-id="fdad7-115">使用使用 WCF LOB 适配器 SDK 创建的适配器</span><span class="sxs-lookup"><span data-stu-id="fdad7-115">Consume an Adapter created using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/consume-an-adapter-created-using-the-wcf-lob-adapter-sdk.md)  
  
## <a name="see-also"></a><span data-ttu-id="fdad7-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fdad7-116">See Also</span></span>  
 <span data-ttu-id="fdad7-117">[WCF LOB 适配器 SDK 入门](../../adapters-and-accelerators/wcf-lob-adapter-sdk/get-started-with-the-with-the-wcf-lob-adapter-sdk.md) </span><span class="sxs-lookup"><span data-stu-id="fdad7-117">[Get started with the WCF LOB Adapter SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/get-started-with-the-with-the-wcf-lob-adapter-sdk.md) </span></span>  
 [<span data-ttu-id="fdad7-118">故障排除的 WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="fdad7-118">Troubleshooting the WCF Adapters</span></span>](../../core/troubleshooting-the-wcf-adapters.md)