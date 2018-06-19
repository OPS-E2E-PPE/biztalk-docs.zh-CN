---
title: 开发在 BizTalk Server 应用程序 Siebel |Microsoft 文档
description: 创建 Siebel 应用程序使用 WCF，或在 BizTalk Server 中使用 BizTalk 适配器包 (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bc04906-6d64-433c-b357-797ec5883279
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c1535a3aa7861effdad998d4d997fbcdfced02c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222597"
---
# <a name="develop-your-siebel-applications"></a><span data-ttu-id="28ca7-103">开发 Siebel 应用程序</span><span class="sxs-lookup"><span data-stu-id="28ca7-103">Develop your Siebel applications</span></span>

## <a name="overview"></a><span data-ttu-id="28ca7-104">概述</span><span class="sxs-lookup"><span data-stu-id="28ca7-104">Overview</span></span>
<span data-ttu-id="28ca7-105">[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="28ca7-105">The [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="28ca7-106">客户端应用程序可以使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]来调用 Siebel 项目上的操作。</span><span class="sxs-lookup"><span data-stu-id="28ca7-106">Client applications can consume the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] to invoke operations on Siebel artifacts.</span></span> <span data-ttu-id="28ca7-107">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]可使用：</span><span class="sxs-lookup"><span data-stu-id="28ca7-107">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] can be consumed:</span></span>  
  
-   <span data-ttu-id="28ca7-108">通过 BizTalk Server 解决方案中的物理端口绑定。</span><span class="sxs-lookup"><span data-stu-id="28ca7-108">Through a physical port binding in a BizTalk Server solution.</span></span>  
  
-   <span data-ttu-id="28ca7-109">通过调用客户端代理的一个实例上的方法。</span><span class="sxs-lookup"><span data-stu-id="28ca7-109">By invoking methods on an instance of a client proxy.</span></span>  
  
-   <span data-ttu-id="28ca7-110">作为承载的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="28ca7-110">As a hosted WCF service.</span></span>  
  
-   <span data-ttu-id="28ca7-111">通过使用 WCF 通道模型的代码中的通道实例发送 SOAP 消息。</span><span class="sxs-lookup"><span data-stu-id="28ca7-111">By sending SOAP messages over a channel instance in code that uses the WCF channel model.</span></span>  
  
-   <span data-ttu-id="28ca7-112">通过 ADO.NET 接口。</span><span class="sxs-lookup"><span data-stu-id="28ca7-112">Through an ADO.NET interface.</span></span>  
  
## <a name="biztalk-vs-wcf-service-vs-wcf-channel-vs-adonet"></a><span data-ttu-id="28ca7-113">BizTalk vs WCF 服务与 WCF 通道 vs ADO.NET</span><span class="sxs-lookup"><span data-stu-id="28ca7-113">BizTalk vs WCF service vs WCF channel vs ADO.NET</span></span>
 <span data-ttu-id="28ca7-114">下表中：</span><span class="sxs-lookup"><span data-stu-id="28ca7-114">The following table:</span></span>  
  
-   <span data-ttu-id="28ca7-115">列出可以对 Siebel 系统使用执行的不同运算[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="28ca7-115">Lists the different operations that can be performed on a Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
-   <span data-ttu-id="28ca7-116">指示哪方法 ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，WCF 服务模型、 WCF 通道模型或 ADO.NET 接口) 可以用于执行操作。</span><span class="sxs-lookup"><span data-stu-id="28ca7-116">Indicates which of the approaches ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], WCF service model, WCF channel model, or ADO.NET interface) can be used to perform the operations.</span></span>  
  
-   <span data-ttu-id="28ca7-117">提供有关执行任务使用选的方法的详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="28ca7-117">Provides links to more information about performing the task using the chosen approach.</span></span>  
  
|<span data-ttu-id="28ca7-118">任务</span><span class="sxs-lookup"><span data-stu-id="28ca7-118">Task</span></span>|<span data-ttu-id="28ca7-119">BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="28ca7-119">BizTalk Server</span></span>|<span data-ttu-id="28ca7-120">WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="28ca7-120">WCF Service Model</span></span>|<span data-ttu-id="28ca7-121">WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="28ca7-121">WCF Channel Model</span></span>|<span data-ttu-id="28ca7-122">ADO.NET 接口</span><span class="sxs-lookup"><span data-stu-id="28ca7-122">ADO.NET Interface</span></span>|  
|----------|--------------------|-----------------------|-----------------------|-----------------------|  
|<span data-ttu-id="28ca7-123">在业务组件的基本插入、 更新、 删除和查询操作</span><span class="sxs-lookup"><span data-stu-id="28ca7-123">Basic Insert, Update, Delete, and Query operations on business components</span></span>|[<span data-ttu-id="28ca7-124">在业务组件使用 BizTalk Server 和 Siebel 适配器上运行操作</span><span class="sxs-lookup"><span data-stu-id="28ca7-124">Run Operations on Business Components Using BizTalk Server and the Siebel adapter</span></span>](run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)|[<span data-ttu-id="28ca7-125">使用 Siebel 适配器使用 WCF 服务模型运行业务组件上的操作</span><span class="sxs-lookup"><span data-stu-id="28ca7-125">Run Operations on Business Components with the Siebel adapter using the WCF Service Model</span></span>](run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md)|[<span data-ttu-id="28ca7-126">使用 Siebel 适配器使用 WCF 通道模型运行业务组件上的操作</span><span class="sxs-lookup"><span data-stu-id="28ca7-126">Run Operations on Business Components with the Siebel adapter using the WCF Channel Model</span></span>](run-tasks-on-business-components-with-the-siebel-adapter-using-a-wcf-channel.md)|<span data-ttu-id="28ca7-127">[在带有 Siebel 业务组件上运行 SELECT 查询](run-a-select-query-on-business-components-with-siebel.md)**注意：** 只能执行选择操作使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="28ca7-127">[Run a SELECT Query on Business Components with Siebel](run-a-select-query-on-business-components-with-siebel.md) **Note:**  You can only perform a SELECT operation using the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].</span></span>|  
|<span data-ttu-id="28ca7-128">对具有 MVG 字段的业务组件的操作</span><span class="sxs-lookup"><span data-stu-id="28ca7-128">Operations on business components with MVG fields</span></span>|[<span data-ttu-id="28ca7-129">使用 MVG 字段使用 BizTalk Server 和 Siebel 适配器运行在业务组件上的操作</span><span class="sxs-lookup"><span data-stu-id="28ca7-129">Run Operations on Business Components with MVG Fields Using BizTalk Server and the Siebel adapter</span></span>](run-operations-on-business-components-with-mvg-fields-using-the-siebel-adapter.md)|[<span data-ttu-id="28ca7-130">在上运行操作的业务组件与 MVG 字段与使用 WCF 服务模型和 Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="28ca7-130">Run Operations on Business Components with MVG Fields with the Siebel adapter using the WCF Service Model</span></span>](work-with-mvp-fields-using-the-siebel-adapter-and-the-wcf-service-model.md)|||  
|<span data-ttu-id="28ca7-131">对与选择列表字段的业务组件的操作</span><span class="sxs-lookup"><span data-stu-id="28ca7-131">Operations on business components with picklist fields</span></span>|[<span data-ttu-id="28ca7-132">使用选择列表字段使用 BizTalk Server 和 Siebel 适配器运行在业务组件上的操作</span><span class="sxs-lookup"><span data-stu-id="28ca7-132">Run Operations on Business Components with Picklist Fields Using BizTalk Server and the Siebel adapter</span></span>](run-tasks-on-business-components-with-picklist-fields-using-the-siebel-adapter.md)||||  
|<span data-ttu-id="28ca7-133">调用业务服务</span><span class="sxs-lookup"><span data-stu-id="28ca7-133">Invoking business services</span></span>|[<span data-ttu-id="28ca7-134">调用业务服务方法使用 BizTalk Server 和 Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="28ca7-134">Invoke Business Service Methods Using BizTalk Server and the Siebel adapter</span></span>](invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md)|||[<span data-ttu-id="28ca7-135">使用 Siebel 运行业务服务上的执行操作</span><span class="sxs-lookup"><span data-stu-id="28ca7-135">Run an EXECUTE Operation on Business Services with Siebel</span></span>](run-an-execute-operation-on-business-services-with-siebel.md)|  
|<span data-ttu-id="28ca7-136">调用具有集成对象的业务服务</span><span class="sxs-lookup"><span data-stu-id="28ca7-136">Invoking business services with integration objects</span></span>|[<span data-ttu-id="28ca7-137">调用具有集成对象使用 Siebel 适配器的业务服务方法</span><span class="sxs-lookup"><span data-stu-id="28ca7-137">Invoke Business Service Methods with Integration Objects using the Siebel adapter</span></span>](run-business-service-methods-with-integration-objects-using-the-siebel-adapter.md)||||  

## <a name="next-steps"></a><span data-ttu-id="28ca7-138">后续步骤</span><span class="sxs-lookup"><span data-stu-id="28ca7-138">Next steps</span></span>  
 <span data-ttu-id="28ca7-139">本部分中的主题提供信息、 过程和示例来帮助你开发的应用程序使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]中都[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]解决方案编程。</span><span class="sxs-lookup"><span data-stu-id="28ca7-139">The topics in this section provide information, procedures, and examples to help you develop applications that consume the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] in both [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] programming solutions.</span></span> 

- [<span data-ttu-id="28ca7-140">创建与 Siebel 系统的连接</span><span class="sxs-lookup"><span data-stu-id="28ca7-140">Create a connection to the Siebel system</span></span>](create-a-connection-to-the-siebel-system.md)
- [<span data-ttu-id="28ca7-141">获取 Visual Studio 中的 Siebel 操作的元数据</span><span class="sxs-lookup"><span data-stu-id="28ca7-141">Get Metadata for Siebel Operations in Visual Studio</span></span>](get-metadata-for-siebel-operations-in-visual-studio.md)
- [<span data-ttu-id="28ca7-142">元数据节点 Id</span><span class="sxs-lookup"><span data-stu-id="28ca7-142">Metadata Node IDs</span></span>](metadata-node-ids1.md)
- [<span data-ttu-id="28ca7-143">使用绑定属性</span><span class="sxs-lookup"><span data-stu-id="28ca7-143">Working with the binding properties</span></span>](read-about-biztalk-adapter-for-siebel-binding-properties.md)
- [<span data-ttu-id="28ca7-144">开发使用 Siebel 适配器的 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="28ca7-144">Develop BizTalk applications using the Siebel adapter</span></span>](develop-biztalk-applications-using-the-siebel-adapter.md)
- [<span data-ttu-id="28ca7-145">使用 WCF 服务模型开发应用程序</span><span class="sxs-lookup"><span data-stu-id="28ca7-145">Develop applications using the WCF Service Model</span></span>](develop-siebel-applications-using-the-wcf-service-model.md)
- [<span data-ttu-id="28ca7-146">使用 WCF 通道模型开发应用程序</span><span class="sxs-lookup"><span data-stu-id="28ca7-146">Develop applications using the WCF Channel Model</span></span>](develop-siebel-applications-using-the-wcf-channel-model3.md)
- [<span data-ttu-id="28ca7-147">.NET Framework 数据提供程序用于 Siebel eBusiness Applications</span><span class="sxs-lookup"><span data-stu-id="28ca7-147">Use the .NET Framework Data Provider for Siebel eBusiness Applications</span></span>](use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)
- [<span data-ttu-id="28ca7-148">使用带有 SharePoint Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="28ca7-148">Use the Siebel Adapter with SharePoint</span></span>](use-the-siebel-adapter-with-sharepoint.md)
- [<span data-ttu-id="28ca7-149">示例</span><span class="sxs-lookup"><span data-stu-id="28ca7-149">Samples</span></span>](samples-for-the-siebel-adapter.md)
- [<span data-ttu-id="28ca7-150">使用 ServiceModel 元数据实用工具 BizTalk 适配器为 Siebel eBusiness Applications</span><span class="sxs-lookup"><span data-stu-id="28ca7-150">Using the ServiceModel Metadata Utility Tool with the BizTalk Adapter for Siebel eBusiness Applications</span></span>](use-the-servicemodel-metadata-utility-with-the-siebel-adapter.md)