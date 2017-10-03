---
title: "关键 SAP 适配器中的功能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, deprecated features
- features, technology-related
- adapters, new features
- features, deprecated
- features, metadata-related
- librfc32u.dll
- tRFC server
- features, new
- adapters, new and deprecated features
- queued tRFC client calls
- features, operations-related
- RFC server
ms.assetid: 30e3140c-447f-42ba-a3b0-13ae66e78b0c
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b34a695e34f617f6444b728e92cb544f91448c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="key-features-in-the-sap-adapter"></a><span data-ttu-id="2fdbe-102">SAP 适配器中的主要功能</span><span class="sxs-lookup"><span data-stu-id="2fdbe-102">Key features in the SAP Adapter</span></span>
<span data-ttu-id="2fdbe-103">本部分列出中的新的和已弃用功能[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-103">This section lists the new and deprecated features in [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2fdbe-104">已从早期版本使用本主题[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-104">This topic has been used from the previous version of [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] Help.</span></span>  
  
## <a name="features-in-the-sap-adapter"></a><span data-ttu-id="2fdbe-105">SAP 适配器中的功能</span><span class="sxs-lookup"><span data-stu-id="2fdbe-105">Features in the SAP Adapter</span></span>  
 <span data-ttu-id="2fdbe-106">以下是早期版本中引入的功能[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-106">The following are the features introduced in the previous releases of the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
### <a name="technology-related-features"></a><span data-ttu-id="2fdbe-107">技术相关功能</span><span class="sxs-lookup"><span data-stu-id="2fdbe-107">Technology-Related Features</span></span>  
  
|<span data-ttu-id="2fdbe-108">功能</span><span class="sxs-lookup"><span data-stu-id="2fdbe-108">Feature</span></span>|<span data-ttu-id="2fdbe-109">注释</span><span class="sxs-lookup"><span data-stu-id="2fdbe-109">Comment</span></span>|  
|-------------|-------------|  
|<span data-ttu-id="2fdbe-110">使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]与 SQL Server Reporting Services (SSRS)。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-110">Using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] with SQL Server Reporting Services (SSRS).</span></span>|<span data-ttu-id="2fdbe-111">现在可以使用客户端程序[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]从 SAP 后端的数据导入 SSRS 项目并生成带数据的报表。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-111">Client programs can now use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] to import data from an SAP backend into an SSRS project and generate reports out of the data.</span></span> <span data-ttu-id="2fdbe-112">有关详细信息如何使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]与 SSRS，请参阅[数据提供程序用于与 SSRS SAP](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssrs.md)。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-112">For more information on how to use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] with SSRS, see [Use the Data Provider for SAP with SSRS](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssrs.md).</span></span> <span data-ttu-id="2fdbe-113">有关 SSRS 的详细信息，请参阅[SQL Server Reporting Services](https://msdn.microsoft.com/library/ms159106.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-113">For more information about SSRS, see [SQL Server Reporting Services](https://msdn.microsoft.com/library/ms159106.aspx).</span></span>|  
|<span data-ttu-id="2fdbe-114">用于调用查询在 SAP 系统中定义的支持</span><span class="sxs-lookup"><span data-stu-id="2fdbe-114">Support for invoking queries defined in an SAP system</span></span>|<span data-ttu-id="2fdbe-115">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]公开某一操作，EXECQUERY，可用来执行在 SAP 系统中定义的查询。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-115">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] exposes an operation, EXECQUERY, that can be used to execute queries defined in an SAP system.</span></span> <span data-ttu-id="2fdbe-116">有关如何使用 EXECQUERY 功能的详细信息，请参阅 [执行 SAP 查询支持</span><span class="sxs-lookup"><span data-stu-id="2fdbe-116">For more information on how to use the EXECQUERY feature, see [Support for Executing SAP Queries</span></span>

<span data-ttu-id="2fdbe-117">] (https://msdn.microsoft.com/library/dd788118.aspx)。 |</span><span class="sxs-lookup"><span data-stu-id="2fdbe-117">](https://msdn.microsoft.com/library/dd788118.aspx).|</span></span>  
<span data-ttu-id="2fdbe-118">|支持使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与 Microsoft Office SharePoint Server (MOSS) |适配器可用于显示从 SAP 系统到 MOSS 门户上的数据。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-118">|Support for using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with Microsoft Office SharePoint Server (MOSS)|You can use the adapters to present data from the SAP system onto a MOSS portal.</span></span> <span data-ttu-id="2fdbe-119">有关详细信息，请参阅[SAP 适配器将用于 SharePoint](../../adapters-and-accelerators/adapter-sap/use-the-sap-adapter-with-sharepoint.md)。 |</span><span class="sxs-lookup"><span data-stu-id="2fdbe-119">For more information, see [Use the SAP Adapter with SharePoint](../../adapters-and-accelerators/adapter-sap/use-the-sap-adapter-with-sharepoint.md).|</span></span>  
  
### <a name="metadata-related-features"></a><span data-ttu-id="2fdbe-120">元数据相关的功能</span><span class="sxs-lookup"><span data-stu-id="2fdbe-120">Metadata-Related Features</span></span>  
  
|<span data-ttu-id="2fdbe-121">功能</span><span class="sxs-lookup"><span data-stu-id="2fdbe-121">Feature</span></span>|<span data-ttu-id="2fdbe-122">注释</span><span class="sxs-lookup"><span data-stu-id="2fdbe-122">Comment</span></span>|  
|-------------|-------------|  
|<span data-ttu-id="2fdbe-123">**DataTypesBehavior**绑定属性</span><span class="sxs-lookup"><span data-stu-id="2fdbe-123">**DataTypesBehavior** binding property</span></span>|<span data-ttu-id="2fdbe-124">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]提供复杂绑定属性， **DataTypesBehavior**，，允许适配器中 SAP 系统遇到特殊值时控制的适配器行为的客户端。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-124">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] shipped with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] provides a complex binding property, **DataTypesBehavior**, that enables adapter clients to control the adapter behavior when special values are encountered in the SAP system.</span></span> <span data-ttu-id="2fdbe-125">有关此绑定属性的详细讨论，请参阅[阅读有关 BizTalk 适配器用于 mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-125">For a detailed discussion about this binding property, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>|  
  
### <a name="operations-related-features"></a><span data-ttu-id="2fdbe-126">与操作相关的功能</span><span class="sxs-lookup"><span data-stu-id="2fdbe-126">Operations-Related Features</span></span>  
  
|<span data-ttu-id="2fdbe-127">功能</span><span class="sxs-lookup"><span data-stu-id="2fdbe-127">Feature</span></span>|<span data-ttu-id="2fdbe-128">注释</span><span class="sxs-lookup"><span data-stu-id="2fdbe-128">Comment</span></span>|  
|-------------|-------------|  
|<span data-ttu-id="2fdbe-129">调用由 RFC 所需的外部程序的支持</span><span class="sxs-lookup"><span data-stu-id="2fdbe-129">Support for invoking external programs required by an RFC</span></span>|<span data-ttu-id="2fdbe-130">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]提供的绑定属性， **RfcAllowStartProgram**可以设置以启用 RFC 客户端库，以调用外部程序，如果任何，所需的特定 RFC。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-130">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] provides a binding property, **RfcAllowStartProgram** that can be set to enable the RFC client library to invoke external programs, if any, required by a particular RFC.</span></span> <span data-ttu-id="2fdbe-131">有关此绑定属性的详细信息，请参阅[阅读有关 BizTalk 适配器用于 mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-131">For more information about this binding property, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>|  
|<span data-ttu-id="2fdbe-132">支持在单个调用中发送多个 Idoc</span><span class="sxs-lookup"><span data-stu-id="2fdbe-132">Support for sending multiple IDOCs in a single call</span></span>|<span data-ttu-id="2fdbe-133">SAP 适配器现在支持将多个相同类型的 Idoc 发送单个适配器调用中。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-133">The SAP adapter now supports sending multiple IDOCs of the same type in a single adapter call.</span></span>|  
  
### <a name="other-features"></a><span data-ttu-id="2fdbe-134">其他功能</span><span class="sxs-lookup"><span data-stu-id="2fdbe-134">Other Features</span></span>  
  
|<span data-ttu-id="2fdbe-135">功能</span><span class="sxs-lookup"><span data-stu-id="2fdbe-135">Feature</span></span>|<span data-ttu-id="2fdbe-136">注释</span><span class="sxs-lookup"><span data-stu-id="2fdbe-136">Comment</span></span>|  
|-------------|-------------|  
|<span data-ttu-id="2fdbe-137">使用中的适配器的新方法[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fdbe-137">New way of using the adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span></span>|<span data-ttu-id="2fdbe-138">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]可以在 BizTalk 中作为 WCF 自定义端口或 WCF SAP 端口使用。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-138">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] can be used in BizTalk either as a WCF-Custom port or a WCF-SAP port.</span></span> <span data-ttu-id="2fdbe-139">如果你想要使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过 WCF 自定义端口，你不需要添加到的 WCF 自定义端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，因为 WCF 自定义端口添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]默认情况下的管理控制台。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-139">If you want to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] through a WCF-Custom port, you do not need to add the WCF-Custom port to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console because the WCF-Custom port is added to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by default.</span></span> <span data-ttu-id="2fdbe-140">但是，如果你想要使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过 WCF SAP 端口，您必须首先添加到 WCF SAP 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-140">However, if you want to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] through a WCF-SAP port, you must first add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="2fdbe-141">有关详细信息，请参阅[将 SAP 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-141">For more information, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>|  
  
## <a name="deprecated-features-in-the-sap-adapter"></a><span data-ttu-id="2fdbe-142">SAP 适配器中已弃用的功能</span><span class="sxs-lookup"><span data-stu-id="2fdbe-142">Deprecated Features in the SAP Adapter</span></span>  
 <span data-ttu-id="2fdbe-143">下列各节列出的受支持在以前版本的适配器，但这不受支持的当前版本中的功能[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-143">The following sections lists the features that were supported in the previous version of the adapter, but which are not supported in the current version of the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
### <a name="enablebusinessobjects-binding-property-deprecated"></a><span data-ttu-id="2fdbe-144">弃用的 EnableBusinessObjects 绑定属性</span><span class="sxs-lookup"><span data-stu-id="2fdbe-144">EnableBusinessObjects binding property deprecated</span></span>  
 <span data-ttu-id="2fdbe-145">此绑定属性中已弃用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-145">This binding property was deprecated in [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] shipped with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="2fdbe-146">此绑定属性用于确定是否在使用时生成元数据时，会显示 BAPI 节点[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2fdbe-146">This binding property was used to determine whether the BAPI node is displayed while generating metadata while using [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fdbe-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2fdbe-147">See Also</span></span>  
 [<span data-ttu-id="2fdbe-148">为 mySAP Business Suite 了解 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="2fdbe-148">Understand BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)