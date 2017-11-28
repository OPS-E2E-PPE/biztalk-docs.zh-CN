---
title: "管理.NET 程序集、 证书和其他资源 |Microsoft 文档"
description: "若要添加绑定文件、 证书、 程序集、 虚拟目录、 文件和 BizTalk Server 中的详细信息的链接"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: efe27a11-19d8-4eb3-9f8c-f4336e4c3d66
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdb74762bdf08e6e9e2a79650a26dedb0915ea8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="manage-net-assemblies-certificates-and-other-resources"></a><span data-ttu-id="28ca2-103">管理.NET 程序集、 证书和其他资源</span><span class="sxs-lookup"><span data-stu-id="28ca2-103">Manage .NET Assemblies, Certificates, and Other Resources</span></span>

## <a name="overview"></a><span data-ttu-id="28ca2-104">概述</span><span class="sxs-lookup"><span data-stu-id="28ca2-104">Overview</span></span>
<span data-ttu-id="28ca2-105">本部分介绍如何使用 BizTalk Server 管理控制台或 BTSTask 命令行工具管理 BizTalk 应用程序的以下几类资源项目。</span><span class="sxs-lookup"><span data-stu-id="28ca2-105">This section provides instructions on using the BizTalk Server Administration console and the BTSTask command-line tool to manage the following types of resource artifacts for a BizTalk application.</span></span> <span data-ttu-id="28ca2-106">由于无法通过 Visual Studio 将这些资源项目自动部署到 BizTalk 应用程序中，因而必须手动将它们添加至应用程序。</span><span class="sxs-lookup"><span data-stu-id="28ca2-106">These resource artifacts cannot be automatically deployed into a BizTalk application from Visual Studio, so you must add them manually to the application.</span></span> <span data-ttu-id="28ca2-107">但是，将它们添加至某个应用程序后，即可将它们作为一个单元随同此应用程序和此应用程序的其他项目一起导入、导出和安装。</span><span class="sxs-lookup"><span data-stu-id="28ca2-107">Once added to an application, however, you can import, export, and install them as a unit with the application and its other artifacts.</span></span>  
  
-   <span data-ttu-id="28ca2-108">**文件。**</span><span class="sxs-lookup"><span data-stu-id="28ca2-108">**Files.**</span></span> <span data-ttu-id="28ca2-109">可以包括特别文件，如自述文件。</span><span class="sxs-lookup"><span data-stu-id="28ca2-109">You can include ad hoc files, such as a Readme file.</span></span> <span data-ttu-id="28ca2-110">在安装应用程序时，将把文件复制到安装文件夹中。</span><span class="sxs-lookup"><span data-stu-id="28ca2-110">When you install the application, files are copied to the installation folder.</span></span>  
  
-   <span data-ttu-id="28ca2-111">**证书。**</span><span class="sxs-lookup"><span data-stu-id="28ca2-111">**Certificates.**</span></span> <span data-ttu-id="28ca2-112">可以向应用程序添加证书文件，以便可以将证书与应用程序打包在一起从一个 BizTalk 组传输到另一个组。</span><span class="sxs-lookup"><span data-stu-id="28ca2-112">You can add a certificate file to an application so that you can transport the certificate from one BizTalk group to another, packaged with an application.</span></span> <span data-ttu-id="28ca2-113">可将证书指定给发送端口和接收位置来验证标识和建立安全链接。</span><span class="sxs-lookup"><span data-stu-id="28ca2-113">You assign certificates to send ports and receive locations to verify identities and to establish secure links.</span></span>  
  
-   <span data-ttu-id="28ca2-114">**COM 和 COM + 组件。**</span><span class="sxs-lookup"><span data-stu-id="28ca2-114">**COM and COM+ components.**</span></span> <span data-ttu-id="28ca2-115">可以将托管 COM 和托管 COM+ 组件包括在 BizTalk 程序中，以提供其他功能。</span><span class="sxs-lookup"><span data-stu-id="28ca2-115">You can include managed COM and managed COM+ components to provide additional functionality in a BizTalk application.</span></span>  
  
-   <span data-ttu-id="28ca2-116">**.NET 程序集。**</span><span class="sxs-lookup"><span data-stu-id="28ca2-116">**.NET assemblies.**</span></span> <span data-ttu-id="28ca2-117">可以将不是特殊 BizTalk 程序集的 .NET 程序集包括在 BizTalk 应用程序中。</span><span class="sxs-lookup"><span data-stu-id="28ca2-117">You can include .NET assemblies that are not specifically BizTalk assemblies in a BizTalk application.</span></span> <span data-ttu-id="28ca2-118">（BizTalk 程序集是包含 BizTalk 业务流程、管道、架构和映射的 .NET 程序集。）</span><span class="sxs-lookup"><span data-stu-id="28ca2-118">(BizTalk assemblies are .NET assemblies that contain BizTalk orchestrations, pipelines, schemas, or maps.)</span></span>  
  
-   <span data-ttu-id="28ca2-119">**BAM 定义文件。**</span><span class="sxs-lookup"><span data-stu-id="28ca2-119">**BAM definition files.**</span></span> <span data-ttu-id="28ca2-120">为使 BAM 部署更为方便，可以创建 BizTalk 应用程序，然后向其添加 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="28ca2-120">To make BAM deployment easier, you can create a BizTalk application and add BAM definitions to it.</span></span> <span data-ttu-id="28ca2-121">然后可以使用此 BizTalk 应用程序的部署功能将 BAM 定义部署到不同的环境中。</span><span class="sxs-lookup"><span data-stu-id="28ca2-121">You can then use the BizTalk application deployment features to deploy the BAM definitions into different environments.</span></span>  
  
-   <span data-ttu-id="28ca2-122">**绑定文件。**</span><span class="sxs-lookup"><span data-stu-id="28ca2-122">**Binding files.**</span></span> <span data-ttu-id="28ca2-123">可以将绑定文件添加至应用程序，以使应用程序从一个部署环境到另一个部署环境的移动更加快捷方便。</span><span class="sxs-lookup"><span data-stu-id="28ca2-123">You can add binding files to an application to make moving an application from one deployment environment to another quicker and easier.</span></span>  
  
-   <span data-ttu-id="28ca2-124">**虚拟目录。**</span><span class="sxs-lookup"><span data-stu-id="28ca2-124">**Virtual directories.**</span></span> <span data-ttu-id="28ca2-125">可以将虚拟目录添加至应用程序，以便将它们和应用程序一起部署。</span><span class="sxs-lookup"><span data-stu-id="28ca2-125">You can add virtual directories to your application so that they will be deployed with the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28ca2-126">Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="28ca2-126">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="28ca2-127">有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="28ca2-127">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="28ca2-128">后续步骤</span><span class="sxs-lookup"><span data-stu-id="28ca2-128">Next steps</span></span>
  
-   [<span data-ttu-id="28ca2-129">将文件添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="28ca2-129">Add a File to an Application</span></span>](../core/how-to-add-a-file-to-an-application.md)  
  
-   [<span data-ttu-id="28ca2-130">将证书添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="28ca2-130">Add a Certificate to an Application</span></span>](../core/how-to-add-a-certificate-to-an-application.md)  
  
-   [<span data-ttu-id="28ca2-131">将 COM 组件添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="28ca2-131">Add a COM Component to an Application</span></span>](../core/how-to-add-a-com-component-to-an-application.md)  
  
-   [<span data-ttu-id="28ca2-132">将.NET 程序集添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="28ca2-132">Add a .NET Assembly to an Application</span></span>](../core/how-to-add-a-net-assembly-to-an-application.md)  
  
-   [<span data-ttu-id="28ca2-133">将一个 BAM 项目添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="28ca2-133">Add a BAM Artifact to an Application</span></span>](../core/how-to-add-a-bam-artifact-to-an-application.md)  
  
-   [<span data-ttu-id="28ca2-134">将绑定文件添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="28ca2-134">Add a Binding File to an Application</span></span>](../core/how-to-add-a-binding-file-to-an-application2.md)  
  
-   [<span data-ttu-id="28ca2-135">将虚拟目录添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="28ca2-135">Add a Virtual Directory to an Application</span></span>](../core/how-to-add-a-virtual-directory-to-an-application.md)  
  
-   [<span data-ttu-id="28ca2-136">修改.NET 程序集、 COM 组件、 文件或 BAM 项目的部署选项</span><span class="sxs-lookup"><span data-stu-id="28ca2-136">Modify the Deployment Options of a .NET Assembly, COM Component, File, or BAM Artifact</span></span>](../core/modify-deployment-options-of-net-assembly-com-component-file-bam-artifact.md)  
  
-   [<span data-ttu-id="28ca2-137">删除从应用程序的.NET 程序集、 证书或其他资源项目</span><span class="sxs-lookup"><span data-stu-id="28ca2-137">Remove a .NET Assembly, Certificate, or Other Resource Artifact from an Application</span></span>](../core/remove-a-net-assembly-certificate-or-resource-artifact-from-an-application.md)