---
title: 发布 WCF 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70b7851b-77c1-4ab3-a61f-e7165ceb56fb
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cc57665a8f57fde0d1ea410c0bad4454cb1a7a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398360"
---
# <a name="publish-wcf-services"></a><span data-ttu-id="8e3a8-102">发布 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="8e3a8-102">Publish WCF Services</span></span>
<span data-ttu-id="8e3a8-103">业务流程可以作为 BizTalk Server 将调用的 WCF 客户端中的 WCF 服务发布。</span><span class="sxs-lookup"><span data-stu-id="8e3a8-103">An orchestration can be published as a WCF service in BizTalk Server to be called by WCF clients.</span></span>  
  
## <a name="publish-wcf-services-with-the-isolated-wcf-adapters"></a><span data-ttu-id="8e3a8-104">发布独立 WCF 适配器的 WCF 的服务</span><span class="sxs-lookup"><span data-stu-id="8e3a8-104">Publish WCF services with the isolated WCF adapters</span></span> 
  
 <span data-ttu-id="8e3a8-105">创建并如 Wcf-basichttp 适配器的独立的 WCF 适配器、 Wcf-wshttp 适配器和 Wcf-customisolated 适配器使用 BizTalk WCF 服务发布向导发布 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="8e3a8-105">You create and publish WCF services by using the BizTalk WCF Service Publishing Wizard for the isolated WCF adapters such as the WCF-BasicHttp adapter, the WCF-WSHttp adapter, and the WCF-CustomIsolated adapter.</span></span> <span data-ttu-id="8e3a8-106">这将创建一个接收位置，作为进程外应用程序在 IIS 中存在。</span><span class="sxs-lookup"><span data-stu-id="8e3a8-106">This creates a receive location which exists as an out of process application in IIS.</span></span>  
  
 <span data-ttu-id="8e3a8-107">通过独立 WCF 适配器发布 WCF 服务之前，应具有托管 WCF 服务如何了解在 Internet 信息服务 (IIS)。</span><span class="sxs-lookup"><span data-stu-id="8e3a8-107">Before you publish a WCF service with the isolated WCF adapters, you should have an understanding of how to host WCF services in Internet Information Services (IIS).</span></span>  
  
## <a name="publish-service-metadata-for-the-wcf-receive-locations"></a><span data-ttu-id="8e3a8-108">为 WCF 接收位置发布服务元数据</span><span class="sxs-lookup"><span data-stu-id="8e3a8-108">Publish service metadata for the WCF receive locations</span></span>
  
 <span data-ttu-id="8e3a8-109">对于已发布的 WCF 接收位置使用 BizTalk WCF 服务发布向导创建服务元数据。</span><span class="sxs-lookup"><span data-stu-id="8e3a8-109">You create service metadata for published WCF receive locations by using the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="8e3a8-110">若要从已发布元数据文档生成服务模型客户端代码可以使用 Windows 软件开发工具包 (SDK) 和.NET Framework 运行时组件中包含的服务模型元数据实用工具工具 (SvcUtil.exe)。</span><span class="sxs-lookup"><span data-stu-id="8e3a8-110">To generate service model client code from the published metadata documents you can use the Service Model Metadata Utility tool (SvcUtil.exe) included in the Windows Software Development Kit (SDK) and .NET Framework Runtime Components.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8e3a8-111">运行 BizTalk WCF 服务发布向导之前，必须启用 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="8e3a8-111">Before running the BizTalk WCF Service Publishing Wizard, you must enable WCF services.</span></span> <span data-ttu-id="8e3a8-112">有关启用你的系统的 WCF 服务的详细信息，请参阅[配置 IIS 以实现独立 WCF 接收适配器](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="8e3a8-112">For more information about enabling WCF services for your system, see [Configuring IIS for the Isolated WCF Receive Adapters](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8e3a8-113">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8e3a8-113">Next steps</span></span>
  
-   [<span data-ttu-id="8e3a8-114">通过独立 WCF 接收适配器发布 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="8e3a8-114">Publishing WCF Services with the Isolated WCF Receive Adapters</span></span>](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="8e3a8-115">为 WCF 接收适配器发布服务元数据</span><span class="sxs-lookup"><span data-stu-id="8e3a8-115">Publishing Service Metadata for the WCF Receive Adapters</span></span>](../core/publishing-service-metadata-for-the-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="8e3a8-116">通过 WCF 接收适配器发布 WCF 服务时的注意事项</span><span class="sxs-lookup"><span data-stu-id="8e3a8-116">Considerations When Publishing WCF Services with the WCF Receive Adapters</span></span>](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="8e3a8-117">SOAP 标头与已发布的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="8e3a8-117">SOAP Headers with Published WCF Services</span></span>](../core/soap-headers-with-published-wcf-services.md)  
  
-   [<span data-ttu-id="8e3a8-118">从发布为 WCF 服务的业务流程引发错误异常</span><span class="sxs-lookup"><span data-stu-id="8e3a8-118">Throw Fault Exceptions from Orchestrations Published as WCF Services</span></span>](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md)