---
title: 开发 BizTalk Server 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 99b56f86-d8e4-4f4a-9ce9-9f476ba88ea8
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4282e036f798732b270dc13c11686d702f545c7e
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530917"
---
# <a name="developing-biztalk-server-applications"></a><span data-ttu-id="488c2-102">开发 BizTalk Server 应用程序</span><span class="sxs-lookup"><span data-stu-id="488c2-102">Developing BizTalk Server Applications</span></span>
<span data-ttu-id="488c2-103">本部分包含的开发人员负责创建 BizTalk 项目的信息。</span><span class="sxs-lookup"><span data-stu-id="488c2-103">This section contains information for developers who are tasked with creating BizTalk projects.</span></span> <span data-ttu-id="488c2-104">使用 BizTalk 项目系统设计环境，可用于设计、 组织和生成 BizTalk 应用程序的各种元素创建项目。</span><span class="sxs-lookup"><span data-stu-id="488c2-104">Projects are created using the BizTalk project System Design Environment, which allows you to design, organize, and build the various elements of BizTalk applications.</span></span> <span data-ttu-id="488c2-105">以下部分介绍此过程的详细信息。</span><span class="sxs-lookup"><span data-stu-id="488c2-105">The following sections describe this process in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="488c2-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="488c2-106">In This Section</span></span>  
  
-   [<span data-ttu-id="488c2-107">开发人员工具</span><span class="sxs-lookup"><span data-stu-id="488c2-107">Developer Tools</span></span>](../core/developer-tools.md)  
  
-   [<span data-ttu-id="488c2-108">使用 BizTalk 消息引擎</span><span class="sxs-lookup"><span data-stu-id="488c2-108">Using the BizTalk Messaging Engine</span></span>](../core/using-the-biztalk-messaging-engine.md)  
  
-   [<span data-ttu-id="488c2-109">使用 BizTalk 编辑器创建架构</span><span class="sxs-lookup"><span data-stu-id="488c2-109">Creating Schemas Using BizTalk Editor</span></span>](../core/creating-schemas-using-biztalk-editor.md)  
  
-   [<span data-ttu-id="488c2-110">使用 BizTalk 映射器创建映射</span><span class="sxs-lookup"><span data-stu-id="488c2-110">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)  
  
-   [<span data-ttu-id="488c2-111">使用管道设计器创建管道</span><span class="sxs-lookup"><span data-stu-id="488c2-111">Creating Pipelines Using Pipeline Designer</span></span>](../core/creating-pipelines-using-pipeline-designer.md)  
  
-   [<span data-ttu-id="488c2-112">使用业务流程设计器创建业务流程</span><span class="sxs-lookup"><span data-stu-id="488c2-112">Creating Orchestrations Using Orchestration Designer</span></span>](../core/creating-orchestrations-using-orchestration-designer.md)  
  
-   [<span data-ttu-id="488c2-113">创建和使用业务规则</span><span class="sxs-lookup"><span data-stu-id="488c2-113">Creating and Using Business Rules</span></span>](../core/creating-and-using-business-rules.md)  
  
-   [<span data-ttu-id="488c2-114">使用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="488c2-114">Using Web Services</span></span>](../core/using-web-services.md)  
  
-   [<span data-ttu-id="488c2-115">使用 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="488c2-115">Using WCF Services</span></span>](../core/using-wcf-services.md)  
  
-   [<span data-ttu-id="488c2-116">设计 BizTalk 应用程序的国际化注意事项</span><span class="sxs-lookup"><span data-stu-id="488c2-116">International Considerations for Designing BizTalk Applications</span></span>](../core/international-considerations-for-designing-biztalk-applications.md)  
  
-   [<span data-ttu-id="488c2-117">将 BizTalk 程序集从 Visual Studio 部署到 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="488c2-117">Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application</span></span>](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)  
  
-   [<span data-ttu-id="488c2-118">创建单一登录应用程序</span><span class="sxs-lookup"><span data-stu-id="488c2-118">Creating a Single Sign-On Application</span></span>](../core/creating-a-single-sign-on-application.md)  
  
-   [<span data-ttu-id="488c2-119">使用 BizTalk 程序集查看器查看程序集</span><span class="sxs-lookup"><span data-stu-id="488c2-119">Viewing Assemblies with the BizTalk Assembly Viewer</span></span>](../core/viewing-assemblies-with-the-biztalk-assembly-viewer.md)  
  
-   [<span data-ttu-id="488c2-120">实现消息安全性</span><span class="sxs-lookup"><span data-stu-id="488c2-120">Implementing Message Security</span></span>](../core/implementing-message-security.md)  
  
## <a name="see-also"></a><span data-ttu-id="488c2-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="488c2-121">See Also</span></span>  
 <span data-ttu-id="488c2-122">[了解 BizTalk 应用程序部署和管理](../core/understanding-biztalk-application-deployment-and-management.md) </span><span class="sxs-lookup"><span data-stu-id="488c2-122">[Understanding BizTalk Application Deployment and Management](../core/understanding-biztalk-application-deployment-and-management.md) </span></span>  
 <span data-ttu-id="488c2-123">[BizTalk 应用程序部署和管理清单](../core/biztalk-application-deployment-and-management-checklists.md) </span><span class="sxs-lookup"><span data-stu-id="488c2-123">[BizTalk Application Deployment and Management Checklists](../core/biztalk-application-deployment-and-management-checklists.md) </span></span>  
 [<span data-ttu-id="488c2-124">BizTalk 应用程序部署和管理演练</span><span class="sxs-lookup"><span data-stu-id="488c2-124">BizTalk Application Deployment and Management Walkthroughs</span></span>](http://msdn.microsoft.com/library/5321f8e0-1e2a-4ac4-a4a2-fc244071bc5b)