---
title: "部署和导出应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4106a0a7-878d-4052-8eca-02d546233048
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b33762f50f32dda58f1453fde7be37bc959af6aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-and-exporting-an-application"></a><span data-ttu-id="b8626-102">部署和导出应用程序</span><span class="sxs-lookup"><span data-stu-id="b8626-102">Deploying and Exporting an Application</span></span>
<span data-ttu-id="b8626-103">本部分包含有关如何在部署 BizTalk 应用程序中执行所涉及的步骤的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="b8626-103">This section contains detailed information about how to perform the steps involved in deploying a BizTalk application.</span></span> <span data-ttu-id="b8626-104">此部分中的主题支持以下清单：</span><span class="sxs-lookup"><span data-stu-id="b8626-104">The topics in this section support the following checklists:</span></span>  
  
-   <span data-ttu-id="b8626-105">[清单： 部署应用程序](../technical-guides/checklist-deploying-an-application.md)，其中说明了如何部署应用程序在开发环境中的，将其导出到.msi 文件中，然后将其导入生产环境中从.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="b8626-105">[Checklist: Deploying an Application](../technical-guides/checklist-deploying-an-application.md), which shows how to deploy an application in a development environment, export it into an .msi file, and then import it into a production environment from the .msi file.</span></span>  
  
-   <span data-ttu-id="b8626-106">[清单： 从到另一个应用程序导出绑定](../technical-guides/checklist-exporting-bindings-from-one-application-to-another.md)，它显示如何从应用程序到另一个应用程序在导出绑定开发或生产环境。</span><span class="sxs-lookup"><span data-stu-id="b8626-106">[Checklist: Exporting Bindings from One Application to Another](../technical-guides/checklist-exporting-bindings-from-one-application-to-another.md), which shows how to export bindings from an application into another application in either a development or production environment.</span></span>  
  
 <span data-ttu-id="b8626-107">可以使用以下工具来部署和管理 BizTalk 应用程序：</span><span class="sxs-lookup"><span data-stu-id="b8626-107">You can use the following tools to deploy and manage a BizTalk application:</span></span>  
  
|<span data-ttu-id="b8626-108">工具</span><span class="sxs-lookup"><span data-stu-id="b8626-108">Tool</span></span>|<span data-ttu-id="b8626-109">改用</span><span class="sxs-lookup"><span data-stu-id="b8626-109">Use</span></span>|  
|----------|---------|  
|<span data-ttu-id="b8626-110">BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="b8626-110">BizTalk Server Administration console</span></span>|<span data-ttu-id="b8626-111">此图形用户界面，可从执行的所有部署和管理 BizTalk 应用程序，包括以下操作：</span><span class="sxs-lookup"><span data-stu-id="b8626-111">From this graphical user interface, you can perform all of the deployment and management operations for a BizTalk application, including the following:</span></span><br /><br /> <span data-ttu-id="b8626-112">启动导入、 安装和导出向导</span><span class="sxs-lookup"><span data-stu-id="b8626-112">-   Starting the Import, Installation, and Export Wizards</span></span><br /><span data-ttu-id="b8626-113">-添加和删除应用程序的项目，以及进行其他修改到应用程序</span><span class="sxs-lookup"><span data-stu-id="b8626-113">-   Adding and removing an application's artifacts, and making other modifications to the application</span></span><br /><span data-ttu-id="b8626-114">生成 BizTalk 应用程序的 BizTalk Server.msi 文件</span><span class="sxs-lookup"><span data-stu-id="b8626-114">-   Generating BizTalk Server .msi files for a BizTalk application</span></span><br /><span data-ttu-id="b8626-115">-从.msi 文件安装到的计算机上的应用程序或将应用程序从.msi 文件导入另一个 BizTalk 组</span><span class="sxs-lookup"><span data-stu-id="b8626-115">-   Installing the application onto a computer from the .msi file or importing the application from the .msi file into another BizTalk group</span></span><br /><span data-ttu-id="b8626-116">-应用程序的绑定从文件导入绑定</span><span class="sxs-lookup"><span data-stu-id="b8626-116">-   Importing the bindings for an application from a binding file</span></span><br /><br /> <span data-ttu-id="b8626-117">有关管理控制台的详细信息，请参阅[使用 BizTalk Server 管理控制台](http://go.microsoft.com/fwlink/?LinkID=154689)(http://go.microsoft.com/fwlink/?LinkID=154689)。</span><span class="sxs-lookup"><span data-stu-id="b8626-117">For more information about the administration console, see [Using the BizTalk Server Administration Console](http://go.microsoft.com/fwlink/?LinkID=154689) (http://go.microsoft.com/fwlink/?LinkID=154689).</span></span>|  
|<span data-ttu-id="b8626-118">BTSTask 命令行工具</span><span class="sxs-lookup"><span data-stu-id="b8626-118">BTSTask command-line tool</span></span>|<span data-ttu-id="b8626-119">你可以从命令行执行许多应用程序管理任务。</span><span class="sxs-lookup"><span data-stu-id="b8626-119">You can perform many application management tasks from the command line.</span></span> <span data-ttu-id="b8626-120">有关命令行工具的详细信息，请参阅[BTSTask 命令行参考](http://go.microsoft.com/fwlink/?LinkId=155003)(http://go.microsoft.com/fwlink/?LinkId=155003)。</span><span class="sxs-lookup"><span data-stu-id="b8626-120">For more information about the command-line tool, see [BTSTask Command Line Reference](http://go.microsoft.com/fwlink/?LinkId=155003) (http://go.microsoft.com/fwlink/?LinkId=155003).</span></span>|  
|<span data-ttu-id="b8626-121">脚本和可编程性 Api</span><span class="sxs-lookup"><span data-stu-id="b8626-121">Scripting and programmability APIs</span></span>|<span data-ttu-id="b8626-122">可以使用 Microsoft Windows 管理规范 (WMI) 或 BizTalk 浏览器对象模型来创建和运行脚本，自动执行许多应用程序管理任务。</span><span class="sxs-lookup"><span data-stu-id="b8626-122">You can use Microsoft Windows Management Instrumentation (WMI) or the BizTalk Explorer Object Model to create and run scripts that automate many application management tasks.</span></span> <span data-ttu-id="b8626-123">有关脚本的详细信息，请参阅[WMI 类引用](http://go.microsoft.com/fwlink/?LinkId=155004)(http://go.microsoft.com/fwlink/?LinkId=155004)。</span><span class="sxs-lookup"><span data-stu-id="b8626-123">For more information about scripting, see [WMI Class Reference](http://go.microsoft.com/fwlink/?LinkId=155004) (http://go.microsoft.com/fwlink/?LinkId=155004).</span></span>|  
|[!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)]|<span data-ttu-id="b8626-124">你可以在 Visual Studio 中创建 BizTalk 程序集，使用部署命令自动将它们部署到 BizTalk 应用程序，和 BizTalk 资源管理器用于配置从 Visual Studio 中的应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="b8626-124">You can create BizTalk assemblies in Visual Studio, use the Deploy command to automatically deploy them into a BizTalk application, and use BizTalk Explorer to configure application artifacts from within Visual Studio.</span></span> <span data-ttu-id="b8626-125">有关使用 Visual Studio 中的详细信息，请参阅[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](http://go.microsoft.com/fwlink/?LinkID=154719) (http://go.microsoft.com/fwlink/?LinkID=154719)。</span><span class="sxs-lookup"><span data-stu-id="b8626-125">For more information about working within Visual Studio, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](http://go.microsoft.com/fwlink/?LinkID=154719) (http://go.microsoft.com/fwlink/?LinkID=154719).</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="b8626-126">本节内容</span><span class="sxs-lookup"><span data-stu-id="b8626-126">In This Section</span></span>  
  
-   [<span data-ttu-id="b8626-127">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="b8626-127">Creating an Application</span></span>](../technical-guides/creating-an-application.md)  
  
-   [<span data-ttu-id="b8626-128">部署程序集</span><span class="sxs-lookup"><span data-stu-id="b8626-128">Deploying an Assembly</span></span>](../technical-guides/deploying-an-assembly.md)  
  
-   [<span data-ttu-id="b8626-129">将项目添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="b8626-129">Adding Artifacts to an Application</span></span>](../technical-guides/adding-artifacts-to-an-application.md)  
  
-   [<span data-ttu-id="b8626-130">如何导出为.msi 文件的应用程序</span><span class="sxs-lookup"><span data-stu-id="b8626-130">How to Export an Application to an .msi File</span></span>](../technical-guides/how-to-export-an-application-to-an-msi-file.md)  
  
-   [<span data-ttu-id="b8626-131">如何导出绑定到绑定文件</span><span class="sxs-lookup"><span data-stu-id="b8626-131">How to Export Bindings to a Binding File</span></span>](../technical-guides/how-to-export-bindings-to-a-binding-file.md)  
  
-   [<span data-ttu-id="b8626-132">如何将绑定文件添加到应用程序 1</span><span class="sxs-lookup"><span data-stu-id="b8626-132">How to Add a Binding File to an Application1</span></span>](../technical-guides/how-to-add-a-binding-file-to-an-application1.md)  
  
-   [<span data-ttu-id="b8626-133">如何从.msi 文件导入应用程序</span><span class="sxs-lookup"><span data-stu-id="b8626-133">How to Import an Application from an .msi File</span></span>](../technical-guides/how-to-import-an-application-from-an-msi-file.md)  
  
-   [<span data-ttu-id="b8626-134">如何安装应用程序</span><span class="sxs-lookup"><span data-stu-id="b8626-134">How to Install an Application</span></span>](../technical-guides/how-to-install-an-application.md)  
  
-   [<span data-ttu-id="b8626-135">如何从绑定文件导入的绑定</span><span class="sxs-lookup"><span data-stu-id="b8626-135">How to Import Bindings from a Binding File</span></span>](../technical-guides/how-to-import-bindings-from-a-binding-file.md)  
  
-   [<span data-ttu-id="b8626-136">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="b8626-136">Testing an Application</span></span>](../technical-guides/testing-an-application.md)  
  
-   [<span data-ttu-id="b8626-137">如何添加对应用程序的引用</span><span class="sxs-lookup"><span data-stu-id="b8626-137">How to Add a Reference to an Application</span></span>](../technical-guides/how-to-add-a-reference-to-an-application.md)