---
title: "开发 BizTalk Server 应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99b56f86-d8e4-4f4a-9ce9-9f476ba88ea8
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c71782556d896d0697b73b83e2966f304b77a3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="developing-biztalk-server-applications"></a><span data-ttu-id="db3ed-102">开发 BizTalk Server 应用程序</span><span class="sxs-lookup"><span data-stu-id="db3ed-102">Developing BizTalk Server Applications</span></span>
<span data-ttu-id="db3ed-103">本部分包含的开发人员负责创建 BizTalk 项目的信息。</span><span class="sxs-lookup"><span data-stu-id="db3ed-103">This section contains information for developers who are tasked with creating BizTalk projects.</span></span> <span data-ttu-id="db3ed-104">项目是使用 BizTalk 项目系统设计环境中，可用于设计、 组织和生成 BizTalk 应用程序的各种元素创建的。</span><span class="sxs-lookup"><span data-stu-id="db3ed-104">Projects are created using the BizTalk project System Design Environment, which allows you to design, organize, and build the various elements of BizTalk applications.</span></span> <span data-ttu-id="db3ed-105">以下部分将详细介绍此过程：</span><span class="sxs-lookup"><span data-stu-id="db3ed-105">The following sections describe this process in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="db3ed-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="db3ed-106">In This Section</span></span>  
  
-   [<span data-ttu-id="db3ed-107">开发人员工具</span><span class="sxs-lookup"><span data-stu-id="db3ed-107">Developer Tools</span></span>](../core/developer-tools.md)  
  
-   [<span data-ttu-id="db3ed-108">使用 BizTalk 消息传送引擎</span><span class="sxs-lookup"><span data-stu-id="db3ed-108">Using the BizTalk Messaging Engine</span></span>](../core/using-the-biztalk-messaging-engine.md)  
  
-   [<span data-ttu-id="db3ed-109">创建使用 BizTalk 编辑器的架构</span><span class="sxs-lookup"><span data-stu-id="db3ed-109">Creating Schemas Using BizTalk Editor</span></span>](../core/creating-schemas-using-biztalk-editor.md)  
  
-   [<span data-ttu-id="db3ed-110">创建使用 BizTalk 映射程序图</span><span class="sxs-lookup"><span data-stu-id="db3ed-110">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)  
  
-   [<span data-ttu-id="db3ed-111">创建管道使用管道设计器</span><span class="sxs-lookup"><span data-stu-id="db3ed-111">Creating Pipelines Using Pipeline Designer</span></span>](../core/creating-pipelines-using-pipeline-designer.md)  
  
-   [<span data-ttu-id="db3ed-112">创建使用业务流程设计器的业务流程</span><span class="sxs-lookup"><span data-stu-id="db3ed-112">Creating Orchestrations Using Orchestration Designer</span></span>](../core/creating-orchestrations-using-orchestration-designer.md)  
  
-   [<span data-ttu-id="db3ed-113">创建和使用业务规则</span><span class="sxs-lookup"><span data-stu-id="db3ed-113">Creating and Using Business Rules</span></span>](../core/creating-and-using-business-rules.md)  
  
-   [<span data-ttu-id="db3ed-114">使用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="db3ed-114">Using Web Services</span></span>](../core/using-web-services.md)  
  
-   [<span data-ttu-id="db3ed-115">使用 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="db3ed-115">Using WCF Services</span></span>](../core/using-wcf-services.md)  
  
-   [<span data-ttu-id="db3ed-116">有关设计 BizTalk 应用程序的国际注意事项</span><span class="sxs-lookup"><span data-stu-id="db3ed-116">International Considerations for Designing BizTalk Applications</span></span>](../core/international-considerations-for-designing-biztalk-applications.md)  
  
-   [<span data-ttu-id="db3ed-117">部署到 BizTalk 应用程序从 Visual Studio BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="db3ed-117">Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application</span></span>](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)  
  
-   [<span data-ttu-id="db3ed-118">创建单一登录在应用程序</span><span class="sxs-lookup"><span data-stu-id="db3ed-118">Creating a Single Sign-On Application</span></span>](../core/creating-a-single-sign-on-application.md)  
  
-   [<span data-ttu-id="db3ed-119">查看具有 BizTalk 程序集查看器的程序集</span><span class="sxs-lookup"><span data-stu-id="db3ed-119">Viewing Assemblies with the BizTalk Assembly Viewer</span></span>](../core/viewing-assemblies-with-the-biztalk-assembly-viewer.md)  
  
-   [<span data-ttu-id="db3ed-120">实现消息安全性</span><span class="sxs-lookup"><span data-stu-id="db3ed-120">Implementing Message Security</span></span>](../core/implementing-message-security.md)  
  
## <a name="see-also"></a><span data-ttu-id="db3ed-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db3ed-121">See Also</span></span>  
 <span data-ttu-id="db3ed-122">[了解 BizTalk 应用程序部署和管理](../core/understanding-biztalk-application-deployment-and-management.md) </span><span class="sxs-lookup"><span data-stu-id="db3ed-122">[Understanding BizTalk Application Deployment and Management](../core/understanding-biztalk-application-deployment-and-management.md) </span></span>  
 <span data-ttu-id="db3ed-123">[BizTalk 应用程序部署和管理清单](../core/biztalk-application-deployment-and-management-checklists.md) </span><span class="sxs-lookup"><span data-stu-id="db3ed-123">[BizTalk Application Deployment and Management Checklists](../core/biztalk-application-deployment-and-management-checklists.md) </span></span>  
 [<span data-ttu-id="db3ed-124">BizTalk 应用程序部署和管理演练</span><span class="sxs-lookup"><span data-stu-id="db3ed-124">BizTalk Application Deployment and Management Walkthroughs</span></span>](http://msdn.microsoft.com/library/5321f8e0-1e2a-4ac4-a4a2-fc244071bc5b)