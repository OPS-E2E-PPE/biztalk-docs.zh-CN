---
title: 业务流程发布为 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- orchestrations, Web services
- Web services, orchestrations
- BizTalk Web Services Publishing Wizard, orchestrations
- BizTalk Web Services Publishing Wizard, prerequisites
- orchestrations, publishing
ms.assetid: f209310d-c265-4c37-8424-c9b287e713ca
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b35f54c6aa850416029ad54b49de59178bcefd34
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398379"
---
# <a name="publishing-an-orchestration-as-a-web-service"></a><span data-ttu-id="707fa-102">业务流程发布为 Web 服务</span><span class="sxs-lookup"><span data-stu-id="707fa-102">Publishing an Orchestration as a Web Service</span></span>
<span data-ttu-id="707fa-103">BizTalk Web Services 发布向导用于业务流程发布为 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="707fa-103">You use the BizTalk Web Services Publishing Wizard to publish an orchestration as a Web service.</span></span> <span data-ttu-id="707fa-104">该向导创建基于 BizTalk 程序集中的业务流程的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="707fa-104">The wizard creates a Web service based on an orchestration in a BizTalk assembly.</span></span> <span data-ttu-id="707fa-105">使用该向导，选择业务流程和接收端口，以将 Web 服务发布。</span><span class="sxs-lookup"><span data-stu-id="707fa-105">Using the wizard, you select orchestrations and receive ports to publish Web services.</span></span> <span data-ttu-id="707fa-106">可以定义目标命名空间、 SOAP 标头要求和该向导将生成 Web 服务项目的位置。</span><span class="sxs-lookup"><span data-stu-id="707fa-106">You can define target namespaces, SOAP header requirements, and locations for the Web service project the wizard generates.</span></span>  
  
 <span data-ttu-id="707fa-107">在运行向导之前，必须编译您的 BizTalk 程序集包含业务流程和你想要将发布为 Web 服务的架构。</span><span class="sxs-lookup"><span data-stu-id="707fa-107">Before you run the wizard, you must compile your BizTalk assemblies that contain the orchestrations and schemas that you intend to publish as a Web service.</span></span>  
  
 <span data-ttu-id="707fa-108">在运行 BizTalk Web Services 发布向导之前, 必须启用 Web services。</span><span class="sxs-lookup"><span data-stu-id="707fa-108">Prior to running the BizTalk Web Services Publishing Wizard, you must enable Web services.</span></span> <span data-ttu-id="707fa-109">有关启用 Web services 为您的系统的详细信息，请参阅[启用 Web 服务](../core/enabling-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="707fa-109">For more information about enabling Web services for your system, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="707fa-110">必须安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]然后才能发布业务流程作为 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="707fa-110">You must install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] before you can publish an orchestration as a Web service.</span></span> <span data-ttu-id="707fa-111">不需要安装 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="707fa-111">You don't need to install Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="707fa-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="707fa-112">In This Section</span></span>  
  
-   [<span data-ttu-id="707fa-113">如何将业务流程映射到 Web 服务</span><span class="sxs-lookup"><span data-stu-id="707fa-113">How to Map Orchestrations to Web Services</span></span>](../core/how-to-map-orchestrations-to-web-services.md)  
  
-   [<span data-ttu-id="707fa-114">如何使用 BizTalk Web Services 发布向导业务流程发布为 Web 服务</span><span class="sxs-lookup"><span data-stu-id="707fa-114">How to Use the BizTalk Web Services Publishing Wizard to Publish an Orchestration as a Web Service</span></span>](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)  
  
-   [<span data-ttu-id="707fa-115">如何从发布为 Web 服务的业务流程引发 SOAP 异常</span><span class="sxs-lookup"><span data-stu-id="707fa-115">How to Throw SOAP Exceptions from Orchestrations Published as a Web Service</span></span>](../core/how-to-throw-soap-exceptions-from-orchestrations-published-as-a-web-service.md)