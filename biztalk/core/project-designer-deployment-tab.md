---
title: 项目设计器： 部署选项卡 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- properties, Configuration database [BizTalk Server]
- Redeploy property
- configuration properties [deployment], Server property
- Server property
- configuration properties [deployment], Install to Global Assembly Cache (GAC) property
- properties, Management database
- Install to Global Assembly Cache (GAC) property
- Configuration database [BizTalk Server], properties
- Management database, properties
- Administration Group property
- configuration properties [deployment], Redeploy property
- configuration properties [deployment], Management database property
- configuration properties [deployment], Administration Group property
ms.assetid: 5b64f99c-4ec6-4ed3-8590-46420e2f75b8
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 972f3956a19d66d47238ee8170584b4faf6ba886
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264941"
---
# <a name="project-designer-deployment-tab"></a><span data-ttu-id="c21f9-102">项目设计器：“部署”选项卡</span><span class="sxs-lookup"><span data-stu-id="c21f9-102">Project Designer: Deployment Tab</span></span>
<span data-ttu-id="c21f9-103">**部署**项目设计器的属性选项卡允许你配置 BizTalk 项目的部署属性。</span><span class="sxs-lookup"><span data-stu-id="c21f9-103">The **Deployment** property tab of the Project Designer allows you to configure the deployment attributes for the BizTalk project.</span></span> <span data-ttu-id="c21f9-104">你必须配置这两**服务器**和**配置数据库**（也称为 BizTalk 管理数据库） 与用于部署成功的集的属性。</span><span class="sxs-lookup"><span data-stu-id="c21f9-104">You must configure both the **Server** and the **Configuration Database** (also known as the BizTalk Management database) properties as a set for deployment to be successful.</span></span>  
  
## <a name="application-name"></a><span data-ttu-id="c21f9-105">应用程序名称</span><span class="sxs-lookup"><span data-stu-id="c21f9-105">Application Name</span></span>  
 <span data-ttu-id="c21f9-106">指定在其中部署程序集的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c21f9-106">Specify the BizTalk application in which to deploy the assembly.</span></span> <span data-ttu-id="c21f9-107">如果此项为空，则项目将部署到默认应用程序中。</span><span class="sxs-lookup"><span data-stu-id="c21f9-107">If this is empty, the project will be deployed into the default application.</span></span>  
  
## <a name="configuration-database"></a><span data-ttu-id="c21f9-108">配置数据库</span><span class="sxs-lookup"><span data-stu-id="c21f9-108">Configuration Database</span></span>  
 <span data-ttu-id="c21f9-109">使用此字段可为已部署的程序集指定 BizTalk 配置数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="c21f9-109">You use this field to specify the name of the BizTalk Configuration database for the deployed assembly.</span></span> <span data-ttu-id="c21f9-110">此项适用于已将 BizTalk 项目配置为部署项目的情况。</span><span class="sxs-lookup"><span data-stu-id="c21f9-110">This applies if you have configured the BizTalk project as a deployment project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c21f9-111">BizTalk 配置数据库也称为 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="c21f9-111">The BizTalk Configuration database is also referred to as the BizTalk Management database.</span></span>  
  
 <span data-ttu-id="c21f9-112">默认配置数据库的名称为 BizTalkMgmtDb。</span><span class="sxs-lookup"><span data-stu-id="c21f9-112">The default Configuration database name is BizTalkMgmtDb.</span></span>  
  
## <a name="server"></a><span data-ttu-id="c21f9-113">Server</span><span class="sxs-lookup"><span data-stu-id="c21f9-113">Server</span></span>  
 <span data-ttu-id="c21f9-114">这是配置存储库（也称为 BizTalk 管理数据库或配置数据库）所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="c21f9-114">This is the name of the server where the Configuration repository (also known as the BizTalk Management or Configuration database) is located.</span></span> <span data-ttu-id="c21f9-115">如果将 BizTalk 项目配置为“部署”，则会将该 BizTalk 项目部署到此服务器。</span><span class="sxs-lookup"><span data-stu-id="c21f9-115">You deploy the BizTalk project to this server if you configure the BizTalk project as "Deployment."</span></span>  
  
## <a name="redeploy"></a><span data-ttu-id="c21f9-116">重新部署</span><span class="sxs-lookup"><span data-stu-id="c21f9-116">Redeploy</span></span>  
 <span data-ttu-id="c21f9-117">你使用**重新部署**属性以确定是否要删除现有的配置并重新创建的配置部署程序集，每次。</span><span class="sxs-lookup"><span data-stu-id="c21f9-117">You use the **Redeploy** property to determine whether to delete the existing configuration and re-create the configuration each time you deploy the assembly.</span></span> <span data-ttu-id="c21f9-118">默认值是`True`。</span><span class="sxs-lookup"><span data-stu-id="c21f9-118">The default value is `True`.</span></span>  
  
## <a name="install-to-global-assembly-cache"></a><span data-ttu-id="c21f9-119">安装到全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="c21f9-119">Install to Global Assembly Cache</span></span>  
 <span data-ttu-id="c21f9-120">你使用**安装到全局程序集缓存**属性以指示如果[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]需要将 BizTalk 程序集安装到全局程序集缓存 (GAC)。</span><span class="sxs-lookup"><span data-stu-id="c21f9-120">You use the **Install to Global Assembly Cache** property to indicate if [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] needs to install the BizTalk assembly to the global assembly cache (GAC).</span></span>  
  
## <a name="restart-host-instances"></a><span data-ttu-id="c21f9-121">重新启动主机实例</span><span class="sxs-lookup"><span data-stu-id="c21f9-121">Restart Host Instances</span></span>  
 <span data-ttu-id="c21f9-122">如果你设置**重新启动主机实例**到**True**，将项目部署时重新启动本地计算机上的主机实例[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c21f9-122">If you set **Restart Host Instances** to **True**, the host instances on the local computer will be restarted when the project is deployed by [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="c21f9-123">在开发周期中要进行更改并经常重新部署时，使用此选项将十分有用，因为您无需手动重新启动相关的主机实例。</span><span class="sxs-lookup"><span data-stu-id="c21f9-123">This is useful during the development cycle when you are making changes and frequently redeploying; you will not have to manually restart related host instances.</span></span>  
  
 <span data-ttu-id="c21f9-124">如果不重新启动相关的主机实例，则最新更改可能无法反映到 BizTalk 应用程序上，因为旧版本可能仍存在于缓存中。</span><span class="sxs-lookup"><span data-stu-id="c21f9-124">If you do not restart related host instances, your latest changes may not be reflected in your BizTalk application because the old version may still be cached.</span></span> <span data-ttu-id="c21f9-125">重新启动主机实例将清除缓存的程序集。</span><span class="sxs-lookup"><span data-stu-id="c21f9-125">Restarting the host instance purges cached assemblies.</span></span>  
  
## <a name="enable-unit-testing"></a><span data-ttu-id="c21f9-126">启用单元测试</span><span class="sxs-lookup"><span data-stu-id="c21f9-126">Enable Unit Testing</span></span>  
 <span data-ttu-id="c21f9-127">指定是否为项目启用单元测试。</span><span class="sxs-lookup"><span data-stu-id="c21f9-127">Specified whether to enable unit testing for the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c21f9-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c21f9-128">See Also</span></span>  
 <span data-ttu-id="c21f9-129">[如何部署 BizTalk 程序集，从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="c21f9-129">[How to Deploy a BizTalk Assembly from Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md) </span></span>  
 [<span data-ttu-id="c21f9-130">BizTalk 项目属性窗口</span><span class="sxs-lookup"><span data-stu-id="c21f9-130">BizTalk Project Properties Window</span></span>](../core/biztalk-project-properties-window.md)