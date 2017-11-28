---
title: "部署和管理 BizTalk 应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications, managing
- Administration Console [BizTalk Server], applications
- bts06.deployment.application
- managing, applications
ms.assetid: d933ad2b-702b-48df-8ef6-a5702d0521e2
caps.latest.revision: "49"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f355c66f7550f5e4cf2b04cfc8bb1f705cc6ade7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-and-managing-biztalk-applications"></a><span data-ttu-id="ab722-102">部署和管理 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="ab722-102">Deploying and Managing BizTalk Applications</span></span>
<span data-ttu-id="ab722-103">本部分提供有关管理 BizTalk 应用程序的信息，包括如何部署、修改、更新以及取消部署 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ab722-103">This section provides information about managing BizTalk applications, including how to deploy, modify, update, and undeploy them.</span></span> <span data-ttu-id="ab722-104">BizTalk 应用程序提供查看和管理构成 BizTalk 业务解决方案的项（称为“项目”）的方法。</span><span class="sxs-lookup"><span data-stu-id="ab722-104">BizTalk applications provide a way to view and manage the items, called "artifacts," that make up a BizTalk business solution.</span></span> <span data-ttu-id="ab722-105">例如，BizTalk 程序集、.NET 程序集、架构、映射、绑定和证书都是项目。</span><span class="sxs-lookup"><span data-stu-id="ab722-105">Examples of artifacts are BizTalk assemblies, .NET assemblies, schemas, maps, bindings, and certificates.</span></span>  
  
 <span data-ttu-id="ab722-106">您可以创建 BizTalk 应用程序并向其添加项目。</span><span class="sxs-lookup"><span data-stu-id="ab722-106">You can create a BizTalk application and add artifacts to it.</span></span> <span data-ttu-id="ab722-107">然后，可以通过 BizTalk Server 管理控制台或者使用 BTSTask 命令行工具将该应用程序及其项目作为单个实体来查看、打包、部署和管理。</span><span class="sxs-lookup"><span data-stu-id="ab722-107">You can then view, package, deploy, and manage the application and its artifacts as a single entity from within the BizTalk Administration console or by using the BTSTask command-line tool.</span></span>  
  
 <span data-ttu-id="ab722-108">有关 BizTalk 应用程序部署和维护的背景信息，请参阅[了解 BizTalk 应用程序部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)。</span><span class="sxs-lookup"><span data-stu-id="ab722-108">For background information about BizTalk application deployment and maintenance, see [Understanding BizTalk Application Deployment and Management](../core/understanding-biztalk-application-deployment-and-management.md).</span></span> <span data-ttu-id="ab722-109">有关部署简单的应用程序的分步说明，这将使您熟悉的应用程序部署功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[演练： 将基本的 BizTalk 应用程序部署](../core/walkthrough-deploying-a-basic-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="ab722-109">For step-by-step instructions on deploying a simple application, which will familiarize you with the application deployment features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Walkthrough: Deploying a Basic BizTalk Application](../core/walkthrough-deploying-a-basic-biztalk-application.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ab722-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="ab722-110">In This Section</span></span>  
  
-   [<span data-ttu-id="ab722-111">部署 BizTalk 应用程序的最佳做法</span><span class="sxs-lookup"><span data-stu-id="ab722-111">Best Practices for Deploying a BizTalk Application</span></span>](../core/best-practices-for-deploying-a-biztalk-application.md)  
  
-   [<span data-ttu-id="ab722-112">BizTalk 应用程序部署和管理清单</span><span class="sxs-lookup"><span data-stu-id="ab722-112">BizTalk Application Deployment and Management Checklists</span></span>](../core/biztalk-application-deployment-and-management-checklists.md)  
  
-   [<span data-ttu-id="ab722-113">演练： 部署基本 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="ab722-113">Walkthrough: Deploying a Basic BizTalk Application</span></span>](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md) 
  
-   [<span data-ttu-id="ab722-114">了解 BizTalk 应用程序部署和管理</span><span class="sxs-lookup"><span data-stu-id="ab722-114">Understanding BizTalk Application Deployment and Management</span></span>](../core/understanding-biztalk-application-deployment-and-management.md)  
  
-   [<span data-ttu-id="ab722-115">如何启动和停止 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="ab722-115">How to Start and Stop a BizTalk Application</span></span>](../core/how-to-start-and-stop-a-biztalk-application.md)  
  
-   [<span data-ttu-id="ab722-116">创建和修改 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="ab722-116">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)  
  
-   [<span data-ttu-id="ab722-117">管理项目</span><span class="sxs-lookup"><span data-stu-id="ab722-117">Managing Artifacts</span></span>](../core/managing-artifacts.md)  
  
-   [<span data-ttu-id="ab722-118">自定义绑定文件</span><span class="sxs-lookup"><span data-stu-id="ab722-118">Customizing Binding Files</span></span>](../core/customizing-binding-files.md)  
  
-   [<span data-ttu-id="ab722-119">前期和后期处理脚本用于自定义应用程序部署</span><span class="sxs-lookup"><span data-stu-id="ab722-119">Using Pre- and Post-processing Scripts to Customize Application Deployment</span></span>](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)  
  
-   [<span data-ttu-id="ab722-120">部署 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="ab722-120">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)  
  
-   [<span data-ttu-id="ab722-121">更新 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="ab722-121">Updating BizTalk Applications</span></span>](../core/updating-biztalk-applications.md)  
  
-   [<span data-ttu-id="ab722-122">正在取消部署的 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="ab722-122">Undeploying BizTalk Applications</span></span>](../core/undeploying-biztalk-applications.md)