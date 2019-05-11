---
title: 开发或创建您的适配器使用 WCF LOB 适配器 SDK |Microsoft Docs
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
ms.openlocfilehash: d10f03639eb7c0c452887819d4c606d562ca7bf0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363655"
---
# <a name="develop-or-create-your-adapter-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="2e043-102">开发或创建您的适配器使用 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="2e043-102">Develop or create your adapter using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="2e043-103">此部分包含有关要创建使用适配器开发人员信息[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2e043-103">This section contains information for developers who are creating adapters using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="2e043-104">一旦该适配器已开发完毕，通常使用由.NET 或[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为一种方法来访问所需的目标业务线系统中的操作和数据的开发人员。</span><span class="sxs-lookup"><span data-stu-id="2e043-104">Once the adapter has been developed, it is usually consumed by either .NET or [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] developers as a way to access operations and data in a desired target line-of-business system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2e043-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="2e043-105">In This Section</span></span>  
  
-   [<span data-ttu-id="2e043-106">使用 WCF LOB 适配器 SDK 开发最佳做法</span><span class="sxs-lookup"><span data-stu-id="2e043-106">Development Best Practices using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="2e043-107">使用 WCF LOB 适配器 SDK 中的 WSDL 代理使用的命名空间</span><span class="sxs-lookup"><span data-stu-id="2e043-107">Use namespaces with the WSDL-Proxy in the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/use-namespaces-with-the-wsdl-proxy-in-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="2e043-108">描述使用 WCF LOB 适配器 SDK 的 WSDL PortType 文档架构</span><span class="sxs-lookup"><span data-stu-id="2e043-108">Describe the WSDL PortType Documentation Schema with the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/describe-the-wsdl-porttype-documentation-schema-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="2e043-109">管理适配器使用 WCF LOB 适配器 SDK 的版本控制</span><span class="sxs-lookup"><span data-stu-id="2e043-109">Manage adapter versioning with the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/manage-adapter-versioning-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="2e043-110">一种服务行为用于输入凭据与 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="2e043-110">Use a Service Behavior to enter credentials with the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/use-a-service-behavior-to-enter-credentials-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="2e043-111">将适配器设置为使用 WCF LOB 适配器 SDK 的绑定属性</span><span class="sxs-lookup"><span data-stu-id="2e043-111">Expose adapter settings as binding property using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/expose-adapter-settings-as-a-binding-property-using-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="2e043-112">浏览和搜索元数据中使用 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="2e043-112">Browse and Search Metadata using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/browse-and-search-metadata-using-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="2e043-113">事务支持</span><span class="sxs-lookup"><span data-stu-id="2e043-113">Transaction Support</span></span>](../../core/transaction-support.md)  
  
-   [<span data-ttu-id="2e043-114">在使用 WCF LOB 适配器 SDK 的 IIS 中适配器的宿主</span><span class="sxs-lookup"><span data-stu-id="2e043-114">Host an adapter in IIS using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/host-an-adapter-in-iis-using-the-wcf-lob-adapter-sdk.md) 
  
-   [<span data-ttu-id="2e043-115">使用创建使用 WCF LOB 适配器 SDK 的适配器</span><span class="sxs-lookup"><span data-stu-id="2e043-115">Consume an Adapter created using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/consume-an-adapter-created-using-the-wcf-lob-adapter-sdk.md)  
  
## <a name="see-also"></a><span data-ttu-id="2e043-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e043-116">See Also</span></span>  
 <span data-ttu-id="2e043-117">[开始使用 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/get-started-with-the-with-the-wcf-lob-adapter-sdk.md) </span><span class="sxs-lookup"><span data-stu-id="2e043-117">[Get started with the WCF LOB Adapter SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/get-started-with-the-with-the-wcf-lob-adapter-sdk.md) </span></span>  
 [<span data-ttu-id="2e043-118">WCF 适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="2e043-118">Troubleshooting the WCF Adapters</span></span>](../../core/troubleshooting-the-wcf-adapters.md)