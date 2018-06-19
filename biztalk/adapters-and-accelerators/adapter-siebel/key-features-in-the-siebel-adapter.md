---
title: 关键 Siebel 适配器中的功能 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- features, performance-related
- adapter features, new
- features, technology-related
- features, metadata-related
- adapter features, operations-related
- adapter features, performance-related
- features, new
- features, operations-related
- adapter features, metadata-related
ms.assetid: 4612c9ab-810e-4c69-9168-a25c58682e71
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 295ff8b13358109a5d4737fb5f9325b3c9caa0f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222125"
---
# <a name="key-features-in-the-siebel-adapter"></a><span data-ttu-id="05b8a-102">Siebel 适配器中的主要功能</span><span class="sxs-lookup"><span data-stu-id="05b8a-102">Key features in the Siebel Adapter</span></span>
<span data-ttu-id="05b8a-103">本部分列出中的新功能[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="05b8a-103">This section lists the new features in [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05b8a-104">已从早期版本使用本主题[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="05b8a-104">This topic has been used from the previous version of [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] Help.</span></span>  
  
## <a name="new-features-in-the-siebel-adapter"></a><span data-ttu-id="05b8a-105">Siebel 适配器中的新增功能</span><span class="sxs-lookup"><span data-stu-id="05b8a-105">New Features in the Siebel Adapter</span></span>  
 <span data-ttu-id="05b8a-106">以下是此版本中引入的新功能[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="05b8a-106">The following are the new features introduced in this release of the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
### <a name="technology-related-features"></a><span data-ttu-id="05b8a-107">技术相关功能</span><span class="sxs-lookup"><span data-stu-id="05b8a-107">Technology-Related Features</span></span>  
  
|<span data-ttu-id="05b8a-108">功能</span><span class="sxs-lookup"><span data-stu-id="05b8a-108">Feature</span></span>|<span data-ttu-id="05b8a-109">注释</span><span class="sxs-lookup"><span data-stu-id="05b8a-109">Comment</span></span>|  
|-------------|-------------|  
|<span data-ttu-id="05b8a-110">支持使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与 Microsoft Office SharePoint Server (MOSS)</span><span class="sxs-lookup"><span data-stu-id="05b8a-110">Support for using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Microsoft Office SharePoint Server (MOSS)</span></span>|<span data-ttu-id="05b8a-111">适配器可用于显示从 MOSS 门户到 Siebel 系统的数据。</span><span class="sxs-lookup"><span data-stu-id="05b8a-111">You can use the adapters to present data from the Siebel system onto a MOSS portal.</span></span> <span data-ttu-id="05b8a-112">有关详细信息，请参阅[Siebel 适配器使用 Microsoft Office SharePoint Server](https://msdn.microsoft.com/library/dd788017.aspx)。</span><span class="sxs-lookup"><span data-stu-id="05b8a-112">For more information, see [Using the Siebel Adapter with Microsoft Office SharePoint Server](https://msdn.microsoft.com/library/dd788017.aspx).</span></span>|  
  
### <a name="operations-related-features"></a><span data-ttu-id="05b8a-113">与操作相关的功能</span><span class="sxs-lookup"><span data-stu-id="05b8a-113">Operations-Related Features</span></span>  
  
|<span data-ttu-id="05b8a-114">功能</span><span class="sxs-lookup"><span data-stu-id="05b8a-114">Feature</span></span>|<span data-ttu-id="05b8a-115">注释</span><span class="sxs-lookup"><span data-stu-id="05b8a-115">Comment</span></span>|  
|-------------|-------------|  
|<span data-ttu-id="05b8a-116">在业务组件上的关联操作的支持</span><span class="sxs-lookup"><span data-stu-id="05b8a-116">Support for ASSOCIATE operation on business components</span></span>|<span data-ttu-id="05b8a-117">适配器客户端可以将记录通过指定搜索表达式父和子记录相关联。</span><span class="sxs-lookup"><span data-stu-id="05b8a-117">Adapter clients can associate records by specifying search expressions for parent and child records.</span></span> <span data-ttu-id="05b8a-118">这是仅适用于多值的组 (MVG) 字段的业务组件。</span><span class="sxs-lookup"><span data-stu-id="05b8a-118">This is applicable only for business components with multivalued group (MVG) fields.</span></span> <span data-ttu-id="05b8a-119">请注意，搜索表达式应筛选恰好一个记录的父和子业务组件。</span><span class="sxs-lookup"><span data-stu-id="05b8a-119">Note that the search expressions should filter exactly one record for both the parent and child business components.</span></span>|  
|<span data-ttu-id="05b8a-120">在业务组件上的取消操作的支持</span><span class="sxs-lookup"><span data-stu-id="05b8a-120">Support for DISASSOCIATE operation on business components</span></span>|<span data-ttu-id="05b8a-121">通过指定父搜索表达式的记录和子记录，则可以取消关联适配器客户端。</span><span class="sxs-lookup"><span data-stu-id="05b8a-121">Adapter clients can dissociate records by specifying search expressions for parent and child records.</span></span> <span data-ttu-id="05b8a-122">这是仅适用于多值的组 (MVG) 字段的业务组件。</span><span class="sxs-lookup"><span data-stu-id="05b8a-122">This is applicable only for business components with multivalued group (MVG) fields.</span></span> <span data-ttu-id="05b8a-123">请注意，搜索表达式必须筛选恰好一个记录的父和子业务组件。</span><span class="sxs-lookup"><span data-stu-id="05b8a-123">Note that the search expressions must filter exactly one record for both the parent and child business components.</span></span>|  
|<span data-ttu-id="05b8a-124">支持的多值链接查询</span><span class="sxs-lookup"><span data-stu-id="05b8a-124">Support for multivalue link queries</span></span>|<span data-ttu-id="05b8a-125">适配器客户端可以查询通过指定的父记录和多值的字段名称与父记录关联的子记录。</span><span class="sxs-lookup"><span data-stu-id="05b8a-125">Adapter clients can query the child records associated with a parent record by specifying the parent record and the multivalued field name.</span></span> <span data-ttu-id="05b8a-126">这是仅适用于多值的组 (MVG) 字段的业务组件。</span><span class="sxs-lookup"><span data-stu-id="05b8a-126">This is applicable only for business components with multivalued group (MVG) fields.</span></span>|  
  
### <a name="other-features"></a><span data-ttu-id="05b8a-127">其他功能</span><span class="sxs-lookup"><span data-stu-id="05b8a-127">Other Features</span></span>  
  
|<span data-ttu-id="05b8a-128">功能</span><span class="sxs-lookup"><span data-stu-id="05b8a-128">Feature</span></span>|<span data-ttu-id="05b8a-129">注释</span><span class="sxs-lookup"><span data-stu-id="05b8a-129">Comment</span></span>|  
|-------------|-------------|  
|<span data-ttu-id="05b8a-130">使用中的适配器的新方法[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05b8a-130">New way of using the adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span></span>|<span data-ttu-id="05b8a-131">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]可以在 BizTalk 中作为 WCF 自定义端口或 WCF Siebel 端口使用。</span><span class="sxs-lookup"><span data-stu-id="05b8a-131">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] can be used in BizTalk either as a WCF-Custom port or a WCF-Siebel port.</span></span> <span data-ttu-id="05b8a-132">如果你想要使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]通过 WCF 自定义端口，你不需要添加到的 WCF 自定义端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，因为 WCF 自定义端口添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]默认情况下的管理控制台。</span><span class="sxs-lookup"><span data-stu-id="05b8a-132">If you want to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] through a WCF-Custom port, you do not need to add the WCF-Custom port to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console because the WCF-Custom port is added to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by default.</span></span> <span data-ttu-id="05b8a-133">但是，如果你想要使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]通过 WCF Siebel 端口，您必须首先添加到在 WCF Siebel 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="05b8a-133">However, if you want to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] through a WCF-Siebel port, you must first add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="05b8a-134">有关详细信息，请参阅[将 Siebel 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="05b8a-134">For more information, see [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05b8a-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05b8a-135">See Also</span></span>  
 [<span data-ttu-id="05b8a-136">为 Siebel eBusiness 应用程序了解的 BizTalk Adapter</span><span class="sxs-lookup"><span data-stu-id="05b8a-136">Understand BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)