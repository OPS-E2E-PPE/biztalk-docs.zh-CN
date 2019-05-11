---
title: 方案：部署新的应用程序 |Microsoft Docs
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
ms.openlocfilehash: 932f8e8692b3f0d2061550bebbc7faf7a8175b2e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308569"
---
# <a name="scenario-deploying-a-new-application"></a><span data-ttu-id="1bb03-102">方案：部署新的应用程序</span><span class="sxs-lookup"><span data-stu-id="1bb03-102">Scenario: Deploying a New Application</span></span>
<span data-ttu-id="1bb03-103">本主题介绍的方案的应用程序部署到新环境，它具有之前未部署;例如，部署已在过渡环境到生产环境中配置的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1bb03-103">This topic describes the scenario of deploying an application into a new environment where it has not been deployed before; for example, deploying an application that has been configured in a staging environment into a production environment.</span></span>  
  
 <span data-ttu-id="1bb03-104">如中所述[应用程序部署过程](../core/the-application-deployment-process.md)，当你想要将应用程序从一个环境移动到另一个原因是，导出到.msi 文件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1bb03-104">As described in [The Application Deployment Process](../core/the-application-deployment-process.md), when you want to move an application from one environment to another, you export the application into an .msi file.</span></span> <span data-ttu-id="1bb03-105">然后将.msi 文件导入新的环境中的 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="1bb03-105">You then import the .msi file into the BizTalk group in the new environment.</span></span> <span data-ttu-id="1bb03-106">此外将运行该应用程序的组中的计算机上安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="1bb03-106">You also install the application on the computers in that group that will run the application.</span></span> <span data-ttu-id="1bb03-107">它可以开始工作之前，必须将运行它，并还启动该应用程序的每台计算机上安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="1bb03-107">Before it can begin functioning, you must install the application on each computer that will run it and also start the application.</span></span>  
  
 <span data-ttu-id="1bb03-108">在下图中，Application1 从导入的.msi 文件到 BizTalk Group b。</span><span class="sxs-lookup"><span data-stu-id="1bb03-108">In the following diagram, Application1 is imported from an .msi file into BizTalk Group B.</span></span>  
  
 <span data-ttu-id="1bb03-109">![BizTalk 应用程序部署](../core/media/deployapplication.gif "缓解")</span><span class="sxs-lookup"><span data-stu-id="1bb03-109">![Deploying a BizTalk application](../core/media/deployapplication.gif "DeployApplication")</span></span>  
  
 <span data-ttu-id="1bb03-110">这将导入项目到各种 BizTalk Server 数据库，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1bb03-110">This imports artifacts into the various BizTalk Server databases as follows:</span></span>  
  
- <span data-ttu-id="1bb03-111">BizTalk 程序集、.NET 程序集、 绑定、 绑定文件、 BAM 模板、 COM 组件、 证书和文本文件都添加到 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="1bb03-111">The BizTalk assembly, .NET assembly, bindings, binding file, BAM template, COM component, certificate, and text file are all added to the BizTalk Management database.</span></span>  
  
- <span data-ttu-id="1bb03-112">策略和词汇添加到规则引擎数据库中。</span><span class="sxs-lookup"><span data-stu-id="1bb03-112">The policy and vocabulary are added to the Rule Engine database.</span></span>  
  
- <span data-ttu-id="1bb03-113">BAM 模板和 BAM 定义文件将添加到 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="1bb03-113">The BAM template and BAM definition file are both added to the BAM Primary Import database.</span></span>  
  
  <span data-ttu-id="1bb03-114">所有这些项目也是 BizTalk 管理数据库中与应用程序 1 相关联。</span><span class="sxs-lookup"><span data-stu-id="1bb03-114">Each of these artifacts is also associated with Application1 in the BizTalk Management database.</span></span>  
  
  <span data-ttu-id="1bb03-115">此外从.msi 文件在本地计算机上安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="1bb03-115">The application is also installed on a local computer from the .msi file.</span></span> <span data-ttu-id="1bb03-116">这将安装包含在.msi 文件中，按如下所示的各种项目：</span><span class="sxs-lookup"><span data-stu-id="1bb03-116">This installs various artifacts that are included in the .msi file, as follows:</span></span>  
  
- <span data-ttu-id="1bb03-117">在 Internet 信息服务 (IIS) 元数据库中创建名为 VirtualDirectory，虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="1bb03-117">The virtual directory, named VirtualDirectory, is created in the Internet Information Services (IIS) metabase.</span></span>  
  
- <span data-ttu-id="1bb03-118">将证书添加到本地证书存储中。</span><span class="sxs-lookup"><span data-stu-id="1bb03-118">The certificate is added to the local certificate store.</span></span>  
  
- <span data-ttu-id="1bb03-119">文本文件和 COM 组件复制到本地文件系统中。</span><span class="sxs-lookup"><span data-stu-id="1bb03-119">The text file and COM component are copied to the local file system.</span></span>  
  
- <span data-ttu-id="1bb03-120">BizTalk 程序集和.NET 程序集添加到全局程序集缓存 (GAC) 中，如果已为它们选择此部署选项。</span><span class="sxs-lookup"><span data-stu-id="1bb03-120">The BizTalk assembly and .NET assembly are added to the global assembly cache (GAC), if this deployment option was selected for them.</span></span>  
  
- <span data-ttu-id="1bb03-121">.NET 程序集和 COM 组件添加到 Windows 注册表中，如果已为它们选择该部署选项。</span><span class="sxs-lookup"><span data-stu-id="1bb03-121">The .NET assembly and COM component are added to the Windows registry, if that deployment option was selected for them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bb03-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="1bb03-122">See Also</span></span>  
 <span data-ttu-id="1bb03-123">[应用程序部署和管理方案](../core/application-deployment-and-management-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="1bb03-123">[Application Deployment and Management Scenarios](../core/application-deployment-and-management-scenarios.md) </span></span>  
 [<span data-ttu-id="1bb03-124">部署 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="1bb03-124">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)