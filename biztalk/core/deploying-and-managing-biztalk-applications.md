---
title: 部署和管理 BizTalk 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, managing
- Administration Console [BizTalk Server], applications
- bts06.deployment.application
- managing, applications
ms.assetid: d933ad2b-702b-48df-8ef6-a5702d0521e2
caps.latest.revision: 49
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47046b468c859799d5263b52a8989e5f8cf99d2f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390151"
---
# <a name="deploying-and-managing-biztalk-applications"></a><span data-ttu-id="d2646-102">部署和管理 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="d2646-102">Deploying and Managing BizTalk Applications</span></span>
<span data-ttu-id="d2646-103">本部分提供有关管理 BizTalk 应用程序，包括如何部署、 修改、 更新和取消部署的信息。</span><span class="sxs-lookup"><span data-stu-id="d2646-103">This section provides information about managing BizTalk applications, including how to deploy, modify, update, and undeploy them.</span></span> <span data-ttu-id="d2646-104">BizTalk 应用程序提供一种查看和管理的项，称为"项目"组成 BizTalk 业务解决方案的方法。</span><span class="sxs-lookup"><span data-stu-id="d2646-104">BizTalk applications provide a way to view and manage the items, called "artifacts," that make up a BizTalk business solution.</span></span> <span data-ttu-id="d2646-105">项目的示例包括 BizTalk 程序集、.NET 程序集、 架构、 映射、 绑定和证书。</span><span class="sxs-lookup"><span data-stu-id="d2646-105">Examples of artifacts are BizTalk assemblies, .NET assemblies, schemas, maps, bindings, and certificates.</span></span>  
  
 <span data-ttu-id="d2646-106">您可以创建 BizTalk 应用程序并向其添加项目。</span><span class="sxs-lookup"><span data-stu-id="d2646-106">You can create a BizTalk application and add artifacts to it.</span></span> <span data-ttu-id="d2646-107">你可以然后查看、 打包、 部署和管理应用程序和其项目作为单个实体内的 BizTalk 管理控制台或通过使用 BTSTask 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="d2646-107">You can then view, package, deploy, and manage the application and its artifacts as a single entity from within the BizTalk Administration console or by using the BTSTask command-line tool.</span></span>  
  
 <span data-ttu-id="d2646-108">有关 BizTalk 应用程序部署和维护的背景信息，请参阅[了解 BizTalk 应用程序部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)。</span><span class="sxs-lookup"><span data-stu-id="d2646-108">For background information about BizTalk application deployment and maintenance, see [Understanding BizTalk Application Deployment and Management](../core/understanding-biztalk-application-deployment-and-management.md).</span></span> <span data-ttu-id="d2646-109">有关部署简单的应用程序的分步说明，这将使您熟悉的应用程序部署功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[演练：部署基本 BizTalk 应用程序](../core/walkthrough-deploying-a-basic-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="d2646-109">For step-by-step instructions on deploying a simple application, which will familiarize you with the application deployment features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Walkthrough: Deploying a Basic BizTalk Application](../core/walkthrough-deploying-a-basic-biztalk-application.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d2646-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="d2646-110">In This Section</span></span>  
  
-   [<span data-ttu-id="d2646-111">部署 BizTalk 应用程序的最佳做法</span><span class="sxs-lookup"><span data-stu-id="d2646-111">Best Practices for Deploying a BizTalk Application</span></span>](../core/best-practices-for-deploying-a-biztalk-application.md)  
  
-   [<span data-ttu-id="d2646-112">BizTalk 应用程序的部署和管理清单</span><span class="sxs-lookup"><span data-stu-id="d2646-112">BizTalk Application Deployment and Management Checklists</span></span>](../core/biztalk-application-deployment-and-management-checklists.md)  
  
-   [<span data-ttu-id="d2646-113">演练：部署基本 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="d2646-113">Walkthrough: Deploying a Basic BizTalk Application</span></span>](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md) 
  
-   [<span data-ttu-id="d2646-114">了解 BizTalk 应用程序的部署和管理</span><span class="sxs-lookup"><span data-stu-id="d2646-114">Understanding BizTalk Application Deployment and Management</span></span>](../core/understanding-biztalk-application-deployment-and-management.md)  
  
-   [<span data-ttu-id="d2646-115">如何启动和停止 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="d2646-115">How to Start and Stop a BizTalk Application</span></span>](../core/how-to-start-and-stop-a-biztalk-application.md)  
  
-   [<span data-ttu-id="d2646-116">创建和修改 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="d2646-116">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)  
  
-   [<span data-ttu-id="d2646-117">管理项目</span><span class="sxs-lookup"><span data-stu-id="d2646-117">Managing Artifacts</span></span>](../core/managing-artifacts.md)  
  
-   [<span data-ttu-id="d2646-118">自定义绑定文件</span><span class="sxs-lookup"><span data-stu-id="d2646-118">Customizing Binding Files</span></span>](../core/customizing-binding-files.md)  
  
-   [<span data-ttu-id="d2646-119">使用预处理脚本和后期处理脚本自定义应用程序部署</span><span class="sxs-lookup"><span data-stu-id="d2646-119">Using Pre- and Post-processing Scripts to Customize Application Deployment</span></span>](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)  
  
-   [<span data-ttu-id="d2646-120">部署 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="d2646-120">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)  
  
-   [<span data-ttu-id="d2646-121">更新 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="d2646-121">Updating BizTalk Applications</span></span>](../core/updating-biztalk-applications.md)  
  
-   [<span data-ttu-id="d2646-122">取消部署 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="d2646-122">Undeploying BizTalk Applications</span></span>](../core/undeploying-biztalk-applications.md)