---
title: 当添加和删除项目时，会发生什么情况 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, artifacts
- artifacts, deleting
- artifacts, creating
- deleting, artifacts
ms.assetid: 811166ba-3ff4-4224-9d84-a2f4ed31bf4d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 464964714993205ef65d5a67de3399935f79320f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288877"
---
# <a name="what-happens-when-artifacts-are-added-and-removed"></a><span data-ttu-id="675cf-102">当添加和删除项目时，会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="675cf-102">What Happens When Artifacts Are Added and Removed</span></span>
<span data-ttu-id="675cf-103">本主题介绍将项目添加到应用程序时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="675cf-103">This topic describes what happens when you add artifacts to an application.</span></span> <span data-ttu-id="675cf-104">您可以通过使用 BizTalk Server 管理控制台或 BTSTask 命令行工具，将基于文件的项目添加到应用程序中。</span><span class="sxs-lookup"><span data-stu-id="675cf-104">You can add file-based artifacts to an application by using the BizTalk Server Administration console or the BTSTask command-line tool.</span></span> <span data-ttu-id="675cf-105">基于文件的项目包括以下类型：</span><span class="sxs-lookup"><span data-stu-id="675cf-105">File-based artifacts include the following types:</span></span>  
  
-   <span data-ttu-id="675cf-106">BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="675cf-106">BizTalk assemblies</span></span>  
  
-   <span data-ttu-id="675cf-107">非特定于 BizTalk 的 .NET 程序集</span><span class="sxs-lookup"><span data-stu-id="675cf-107">.NET assemblies that are not BizTalk-specific</span></span>  
  
-   <span data-ttu-id="675cf-108">绑定 (.xml) 文件</span><span class="sxs-lookup"><span data-stu-id="675cf-108">Binding (.xml) files</span></span>  
  
-   <span data-ttu-id="675cf-109">COM 组件</span><span class="sxs-lookup"><span data-stu-id="675cf-109">COM components</span></span>  
  
-   <span data-ttu-id="675cf-110">证书</span><span class="sxs-lookup"><span data-stu-id="675cf-110">Certificates</span></span>  
  
-   <span data-ttu-id="675cf-111">预处理和后处理脚本</span><span class="sxs-lookup"><span data-stu-id="675cf-111">Pre- and post-processing scripts</span></span>  
  
-   <span data-ttu-id="675cf-112">策略</span><span class="sxs-lookup"><span data-stu-id="675cf-112">Policies</span></span>  
  
-   <span data-ttu-id="675cf-113">特别文件，如自述文件</span><span class="sxs-lookup"><span data-stu-id="675cf-113">Ad hoc files, such as Readme files</span></span>  
  
-   <span data-ttu-id="675cf-114">虚拟目录</span><span class="sxs-lookup"><span data-stu-id="675cf-114">Virtual directories</span></span>  
  
-   <span data-ttu-id="675cf-115">BAM 项目</span><span class="sxs-lookup"><span data-stu-id="675cf-115">BAM artifacts</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="675cf-116">发送端口、发送端口组、接收位置以及接收端口都不是基于文件的项目，不能添加到应用程序中。</span><span class="sxs-lookup"><span data-stu-id="675cf-116">Send ports, send port groups, receive locations, and receive ports are not file-based artifacts and cannot be added to an application.</span></span> <span data-ttu-id="675cf-117">必须在给定应用程序中创建这些项目。</span><span class="sxs-lookup"><span data-stu-id="675cf-117">You must create these artifacts within a given application.</span></span> <span data-ttu-id="675cf-118">然后，将它们移到其他应用程序中（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="675cf-118">You can then move them to a different application, if you want.</span></span> <span data-ttu-id="675cf-119">业务流程、架构、映射和管道都是作为包含它们的程序集的一部分来部署和托管的。</span><span class="sxs-lookup"><span data-stu-id="675cf-119">Orchestrations, schemas, maps and pipelines are all deployed and managed as part of the assemblies that contain them.</span></span>  
  
 <span data-ttu-id="675cf-120">将项目添加到应用程序时，该项目将与 BizTalk 管理数据库中的应用程序相关联，并且基于文件的项目数据也将被添加到管理数据库中。</span><span class="sxs-lookup"><span data-stu-id="675cf-120">When you add an artifact to an application, the artifact is associated with the application in the BizTalk Management database, and file-based data for the artifact is added to the Management database as well.</span></span> <span data-ttu-id="675cf-121">这样，您可以将一个 BizTalk 组中的应用程序和项目轻松传输到其他 BizTalk 组，因为您可以将该 BizTalk 组中项目的应用程序和数据从管理数据库导出到 .msi 文件中，然后将其导入其他 BizTalk 组的管理数据库中。</span><span class="sxs-lookup"><span data-stu-id="675cf-121">This allows you to easily transport applications and artifacts from one BizTalk group to another because you can export the application and the data for its artifacts into an .msi file from the Management database, and then import it into a Management database in a different BizTalk group.</span></span>  
  
 <span data-ttu-id="675cf-122">将绑定文件添加到应用程序时，可指定要应用绑定的目标部署环境。</span><span class="sxs-lookup"><span data-stu-id="675cf-122">When you add a binding file to an application, you can specify the target deployment environment in which you want the bindings to be applied.</span></span> <span data-ttu-id="675cf-123">与导入绑定文件不同，在添加绑定文件时，并不会应用其绑定。</span><span class="sxs-lookup"><span data-stu-id="675cf-123">Unlike importing a binding file, when you add a binding file, its bindings are not applied.</span></span>  
  
 <span data-ttu-id="675cf-124">向应用程序添加 BizTalk 程序集或 .NET 程序集时，如果指定此选项，则该程序集将会被添加到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="675cf-124">When you add a BizTalk assembly or a .NET assembly to an application, the assembly is added to the global assembly cache if you specify this option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="675cf-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="675cf-125">See Also</span></span>  
 <span data-ttu-id="675cf-126">[会发生什么情况项目在应用程序部署过程](../core/what-happens-to-artifacts-during-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="675cf-126">[What Happens to Artifacts During Application Deployment](../core/what-happens-to-artifacts-during-application-deployment.md) </span></span>  
 <span data-ttu-id="675cf-127">[如何创建或添加项目](../core/how-to-create-or-add-an-artifact.md) </span><span class="sxs-lookup"><span data-stu-id="675cf-127">[How to Create or Add an Artifact](../core/how-to-create-or-add-an-artifact.md) </span></span>  
 <span data-ttu-id="675cf-128">[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="675cf-128">[How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md) </span></span>  
 [<span data-ttu-id="675cf-129">如何导出 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="675cf-129">How to Export a BizTalk Application</span></span>](../core/how-to-export-a-biztalk-application.md)