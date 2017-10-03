---
title: "发布作为 Web 服务业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- orchestrations, Web services
- Web services, orchestrations
- BizTalk Web Services Publishing Wizard, orchestrations
- BizTalk Web Services Publishing Wizard, prerequisites
- orchestrations, publishing
ms.assetid: f209310d-c265-4c37-8424-c9b287e713ca
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b6d36f6c56851bfedcd522f96d01a8256232826
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-an-orchestration-as-a-web-service"></a><span data-ttu-id="1f0bf-102">将业务流程发布为 Web Service</span><span class="sxs-lookup"><span data-stu-id="1f0bf-102">Publishing an Orchestration as a Web Service</span></span>
<span data-ttu-id="1f0bf-103">可以使用 BizTalk Web Services 发布向导将业务流程发布为 Web Services。</span><span class="sxs-lookup"><span data-stu-id="1f0bf-103">You use the BizTalk Web Services Publishing Wizard to publish an orchestration as a Web service.</span></span> <span data-ttu-id="1f0bf-104">该向导基于 BizTalk 程序集中的业务流程创建 Web Services。</span><span class="sxs-lookup"><span data-stu-id="1f0bf-104">The wizard creates a Web service based on an orchestration in a BizTalk assembly.</span></span> <span data-ttu-id="1f0bf-105">使用该向导，你可以选择用于发布 Web Services 的业务流程和接收端口。</span><span class="sxs-lookup"><span data-stu-id="1f0bf-105">Using the wizard, you select orchestrations and receive ports to publish Web services.</span></span> <span data-ttu-id="1f0bf-106">你可以定义目标命名空间、SOAP 标头要求和该向导生成的 Web Services 项目的位置。</span><span class="sxs-lookup"><span data-stu-id="1f0bf-106">You can define target namespaces, SOAP header requirements, and locations for the Web service project the wizard generates.</span></span>  
  
 <span data-ttu-id="1f0bf-107">在运行向导之前，必须编译包含要发布为 Web Services 的业务流程和架构的 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="1f0bf-107">Before you run the wizard, you must compile your BizTalk assemblies that contain the orchestrations and schemas that you intend to publish as a Web service.</span></span>  
  
 <span data-ttu-id="1f0bf-108">在运行 BizTalk Web 服务发布向导之前, 必须启用 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="1f0bf-108">Prior to running the BizTalk Web Services Publishing Wizard, you must enable Web services.</span></span> <span data-ttu-id="1f0bf-109">有关启用你的系统的 Web 服务的详细信息，请参阅[启用 Web 服务](../core/enabling-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="1f0bf-109">For more information about enabling Web services for your system, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f0bf-110">必须安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发布作为 Web 服务业务流程之前。</span><span class="sxs-lookup"><span data-stu-id="1f0bf-110">You must install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] before you can publish an orchestration as a Web service.</span></span> <span data-ttu-id="1f0bf-111">你不需要安装 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1f0bf-111">You don't need to install Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1f0bf-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="1f0bf-112">In This Section</span></span>  
  
-   [<span data-ttu-id="1f0bf-113">如何映射到 Web 服务的业务流程</span><span class="sxs-lookup"><span data-stu-id="1f0bf-113">How to Map Orchestrations to Web Services</span></span>](../core/how-to-map-orchestrations-to-web-services.md)  
  
-   [<span data-ttu-id="1f0bf-114">如何使用发布向导的 BizTalk Web 服务发布作为 Web 服务业务流程</span><span class="sxs-lookup"><span data-stu-id="1f0bf-114">How to Use the BizTalk Web Services Publishing Wizard to Publish an Orchestration as a Web Service</span></span>](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)  
  
-   [<span data-ttu-id="1f0bf-115">如何从作为 Web 服务发布的业务流程引发 SOAP 异常</span><span class="sxs-lookup"><span data-stu-id="1f0bf-115">How to Throw SOAP Exceptions from Orchestrations Published as a Web Service</span></span>](../core/how-to-throw-soap-exceptions-from-orchestrations-published-as-a-web-service.md)