---
title: 方案： 部署新的应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, applications
- applications, deploying
- deploying [applications], examples
- applications, examples
- examples, deploying
ms.assetid: 6d34a626-9fd4-4c33-a067-b66333eec01f
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 938767237d21b74829c786bdd5d57c7d9df15c2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269205"
---
# <a name="scenario-deploying-a-new-application"></a><span data-ttu-id="89395-102">方案： 将新的应用程序部署</span><span class="sxs-lookup"><span data-stu-id="89395-102">Scenario: Deploying a New Application</span></span>
<span data-ttu-id="89395-103">本主题说明了将应用程序部署到一个以前从未部署它的新环境的方案；例如，将已在过渡环境中配置的应用程序部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="89395-103">This topic describes the scenario of deploying an application into a new environment where it has not been deployed before; for example, deploying an application that has been configured in a staging environment into a production environment.</span></span>  
  
 <span data-ttu-id="89395-104">中所述[应用程序部署过程](../core/the-application-deployment-process.md)，当你想要将应用程序从一个环境移动到另一个原因是，导出应用程序置于.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="89395-104">As described in [The Application Deployment Process](../core/the-application-deployment-process.md), when you want to move an application from one environment to another, you export the application into an .msi file.</span></span> <span data-ttu-id="89395-105">然后，可在新环境中将 .msi 文件导入 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="89395-105">You then import the .msi file into the BizTalk group in the new environment.</span></span> <span data-ttu-id="89395-106">您还应该将该应用程序安装在将运行它的组中的计算机上。</span><span class="sxs-lookup"><span data-stu-id="89395-106">You also install the application on the computers in that group that will run the application.</span></span> <span data-ttu-id="89395-107">要使该应用程序正常运行，必须将其安装在将运行它的计算机上，并且启动它。</span><span class="sxs-lookup"><span data-stu-id="89395-107">Before it can begin functioning, you must install the application on each computer that will run it and also start the application.</span></span>  
  
 <span data-ttu-id="89395-108">在下图中，Application1 从 .msi 文件导入 BizTalk Group B。</span><span class="sxs-lookup"><span data-stu-id="89395-108">In the following diagram, Application1 is imported from an .msi file into BizTalk Group B.</span></span>  
  
 <span data-ttu-id="89395-109">![将 BizTalk 应用程序部署](../core/media/deployapplication.gif "DeployApplication")</span><span class="sxs-lookup"><span data-stu-id="89395-109">![Deploying a BizTalk application](../core/media/deployapplication.gif "DeployApplication")</span></span>  
  
 <span data-ttu-id="89395-110">此过程按下述方式将项目导入各种 BizTalk Server 数据库：</span><span class="sxs-lookup"><span data-stu-id="89395-110">This imports artifacts into the various BizTalk Server databases as follows:</span></span>  
  
-   <span data-ttu-id="89395-111">BizTalk 程序集、.NET 程序集、绑定、绑定文件、BAM 模板、COM 组件、证书和文本文件都将添加到 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="89395-111">The BizTalk assembly, .NET assembly, bindings, binding file, BAM template, COM component, certificate, and text file are all added to the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="89395-112">策略和词汇添加到规则引擎数据库。</span><span class="sxs-lookup"><span data-stu-id="89395-112">The policy and vocabulary are added to the Rule Engine database.</span></span>  
  
-   <span data-ttu-id="89395-113">BAM 模板和 BAM 定义文件都添加到 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="89395-113">The BAM template and BAM definition file are both added to the BAM Primary Import database.</span></span>  
  
 <span data-ttu-id="89395-114">所有这些项目还要与 BizTalk 管理数据库中的 Application1 相关联。</span><span class="sxs-lookup"><span data-stu-id="89395-114">Each of these artifacts is also associated with Application1 in the BizTalk Management database.</span></span>  
  
 <span data-ttu-id="89395-115">应用程序还会从 .msi 文件安装在本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="89395-115">The application is also installed on a local computer from the .msi file.</span></span> <span data-ttu-id="89395-116">此过程按下述方式安装 .msi 文件中包括的各种项目：</span><span class="sxs-lookup"><span data-stu-id="89395-116">This installs various artifacts that are included in the .msi file, as follows:</span></span>  
  
-   <span data-ttu-id="89395-117">虚拟目录（即命名的 VirtualDirectory）在 Internet 信息服务 (IIS) 数据库中创建。</span><span class="sxs-lookup"><span data-stu-id="89395-117">The virtual directory, named VirtualDirectory, is created in the Internet Information Services (IIS) metabase.</span></span>  
  
-   <span data-ttu-id="89395-118">证书添加到本地证书存储区。</span><span class="sxs-lookup"><span data-stu-id="89395-118">The certificate is added to the local certificate store.</span></span>  
  
-   <span data-ttu-id="89395-119">文本文件和 COM 组件复制到本地文件系统。</span><span class="sxs-lookup"><span data-stu-id="89395-119">The text file and COM component are copied to the local file system.</span></span>  
  
-   <span data-ttu-id="89395-120">BizTalk 程序集和 .NET 程序集添加到全局程序集缓存 (GAC)（如果已为它们选择此部署选项）。</span><span class="sxs-lookup"><span data-stu-id="89395-120">The BizTalk assembly and .NET assembly are added to the global assembly cache (GAC), if this deployment option was selected for them.</span></span>  
  
-   <span data-ttu-id="89395-121">.NET 程序集和 COM 组件添加到 Windows 注册表（如果已为它们选择该部署选项）。</span><span class="sxs-lookup"><span data-stu-id="89395-121">The .NET assembly and COM component are added to the Windows registry, if that deployment option was selected for them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89395-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89395-122">See Also</span></span>  
 <span data-ttu-id="89395-123">[应用程序部署和管理方案](../core/application-deployment-and-management-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="89395-123">[Application Deployment and Management Scenarios](../core/application-deployment-and-management-scenarios.md) </span></span>  
 [<span data-ttu-id="89395-124">部署 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="89395-124">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)