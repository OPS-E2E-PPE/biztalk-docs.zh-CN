---
title: 添加和删除项目时，会发生什么情况 |Microsoft Docs
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
ms.openlocfilehash: dbda3968ec4337ccf3b00bf1b1698d73c9232c47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401079"
---
# <a name="what-happens-when-artifacts-are-added-and-removed"></a><span data-ttu-id="15d69-102">添加和删除项目时，会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="15d69-102">What Happens When Artifacts Are Added and Removed</span></span>
<span data-ttu-id="15d69-103">本主题介绍当将项目添加到应用程序时，会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="15d69-103">This topic describes what happens when you add artifacts to an application.</span></span> <span data-ttu-id="15d69-104">通过使用 BizTalk Server 管理控制台或 BTSTask 命令行工具，可以向应用程序添加基于文件的项目。</span><span class="sxs-lookup"><span data-stu-id="15d69-104">You can add file-based artifacts to an application by using the BizTalk Server Administration console or the BTSTask command-line tool.</span></span> <span data-ttu-id="15d69-105">基于文件的项目包括以下类型：</span><span class="sxs-lookup"><span data-stu-id="15d69-105">File-based artifacts include the following types:</span></span>  
  
-   <span data-ttu-id="15d69-106">BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="15d69-106">BizTalk assemblies</span></span>  
  
-   <span data-ttu-id="15d69-107">不是特定于 BizTalk 的.NET 程序集</span><span class="sxs-lookup"><span data-stu-id="15d69-107">.NET assemblies that are not BizTalk-specific</span></span>  
  
-   <span data-ttu-id="15d69-108">绑定 (.xml) 文件</span><span class="sxs-lookup"><span data-stu-id="15d69-108">Binding (.xml) files</span></span>  
  
-   <span data-ttu-id="15d69-109">COM 组件</span><span class="sxs-lookup"><span data-stu-id="15d69-109">COM components</span></span>  
  
-   <span data-ttu-id="15d69-110">证书</span><span class="sxs-lookup"><span data-stu-id="15d69-110">Certificates</span></span>  
  
-   <span data-ttu-id="15d69-111">预处理和后处理脚本</span><span class="sxs-lookup"><span data-stu-id="15d69-111">Pre- and post-processing scripts</span></span>  
  
-   <span data-ttu-id="15d69-112">策略</span><span class="sxs-lookup"><span data-stu-id="15d69-112">Policies</span></span>  
  
-   <span data-ttu-id="15d69-113">特别文件，如自述文件</span><span class="sxs-lookup"><span data-stu-id="15d69-113">Ad hoc files, such as Readme files</span></span>  
  
-   <span data-ttu-id="15d69-114">虚拟目录</span><span class="sxs-lookup"><span data-stu-id="15d69-114">Virtual directories</span></span>  
  
-   <span data-ttu-id="15d69-115">BAM 项目</span><span class="sxs-lookup"><span data-stu-id="15d69-115">BAM artifacts</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15d69-116">发送端口、 发送端口组、 接收位置和接收端口都不是基于文件的项目，不能添加到应用程序。</span><span class="sxs-lookup"><span data-stu-id="15d69-116">Send ports, send port groups, receive locations, and receive ports are not file-based artifacts and cannot be added to an application.</span></span> <span data-ttu-id="15d69-117">必须创建一个给定的应用程序中的这些项目。</span><span class="sxs-lookup"><span data-stu-id="15d69-117">You must create these artifacts within a given application.</span></span> <span data-ttu-id="15d69-118">你可以然后将它们移动到不同的应用程序，如果你想。</span><span class="sxs-lookup"><span data-stu-id="15d69-118">You can then move them to a different application, if you want.</span></span> <span data-ttu-id="15d69-119">业务流程、 架构、 映射和管道是所有部署和管理包含它们的程序集的一部分。</span><span class="sxs-lookup"><span data-stu-id="15d69-119">Orchestrations, schemas, maps and pipelines are all deployed and managed as part of the assemblies that contain them.</span></span>  
  
 <span data-ttu-id="15d69-120">当将项目添加到应用程序时的项目是与 BizTalk 管理数据库中的应用程序相关联和基于文件的项目的数据添加到管理数据库。</span><span class="sxs-lookup"><span data-stu-id="15d69-120">When you add an artifact to an application, the artifact is associated with the application in the BizTalk Management database, and file-based data for the artifact is added to the Management database as well.</span></span> <span data-ttu-id="15d69-121">因此，您可以轻松地传输应用程序和项目从一个 BizTalk 组到另一个，因为您可以将应用程序和其项目的数据导出到.msi 文件从管理数据库，然后将其导入的管理数据库中不同的 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="15d69-121">This allows you to easily transport applications and artifacts from one BizTalk group to another because you can export the application and the data for its artifacts into an .msi file from the Management database, and then import it into a Management database in a different BizTalk group.</span></span>  
  
 <span data-ttu-id="15d69-122">当向应用程序添加绑定文件时，可以指定在其中你想要应用绑定的目标部署环境。</span><span class="sxs-lookup"><span data-stu-id="15d69-122">When you add a binding file to an application, you can specify the target deployment environment in which you want the bindings to be applied.</span></span> <span data-ttu-id="15d69-123">与导入绑定文件，不同时添加绑定文件，则不应用其绑定。</span><span class="sxs-lookup"><span data-stu-id="15d69-123">Unlike importing a binding file, when you add a binding file, its bindings are not applied.</span></span>  
  
 <span data-ttu-id="15d69-124">当向应用程序添加 BizTalk 程序集或.NET 程序集时，该程序集添加到全局程序集缓存，如果指定此选项。</span><span class="sxs-lookup"><span data-stu-id="15d69-124">When you add a BizTalk assembly or a .NET assembly to an application, the assembly is added to the global assembly cache if you specify this option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15d69-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="15d69-125">See Also</span></span>  
 <span data-ttu-id="15d69-126">[对项目采取的应用程序部署过程](../core/what-happens-to-artifacts-during-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="15d69-126">[What Happens to Artifacts During Application Deployment](../core/what-happens-to-artifacts-during-application-deployment.md) </span></span>  
 <span data-ttu-id="15d69-127">[如何创建或添加项目](../core/how-to-create-or-add-an-artifact.md) </span><span class="sxs-lookup"><span data-stu-id="15d69-127">[How to Create or Add an Artifact](../core/how-to-create-or-add-an-artifact.md) </span></span>  
 <span data-ttu-id="15d69-128">[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="15d69-128">[How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md) </span></span>  
 [<span data-ttu-id="15d69-129">如何导出 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="15d69-129">How to Export a BizTalk Application</span></span>](../core/how-to-export-a-biztalk-application.md)