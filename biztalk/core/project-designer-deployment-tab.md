---
title: 项目设计器：部署选项卡 |Microsoft Docs
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
ms.openlocfilehash: b6cf82e112834dbacc021e3ce5564866a2e8cbbb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395618"
---
# <a name="project-designer-deployment-tab"></a><span data-ttu-id="fe73d-102">项目设计器：部署选项卡</span><span class="sxs-lookup"><span data-stu-id="fe73d-102">Project Designer: Deployment Tab</span></span>
<span data-ttu-id="fe73d-103">**部署**项目设计器的属性选项卡允许你配置的 BizTalk 项目的部署属性。</span><span class="sxs-lookup"><span data-stu-id="fe73d-103">The **Deployment** property tab of the Project Designer allows you to configure the deployment attributes for the BizTalk project.</span></span> <span data-ttu-id="fe73d-104">您必须同时配置两者**服务器**并**配置数据库**（也称为 BizTalk 管理数据库） 属性作为组进行部署才能成功。</span><span class="sxs-lookup"><span data-stu-id="fe73d-104">You must configure both the **Server** and the **Configuration Database** (also known as the BizTalk Management database) properties as a set for deployment to be successful.</span></span>  
  
## <a name="application-name"></a><span data-ttu-id="fe73d-105">应用程序名称</span><span class="sxs-lookup"><span data-stu-id="fe73d-105">Application Name</span></span>  
 <span data-ttu-id="fe73d-106">指定要在其中部署该程序集的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="fe73d-106">Specify the BizTalk application in which to deploy the assembly.</span></span> <span data-ttu-id="fe73d-107">如果它为空，则项目将部署到默认应用程序。</span><span class="sxs-lookup"><span data-stu-id="fe73d-107">If this is empty, the project will be deployed into the default application.</span></span>  
  
## <a name="configuration-database"></a><span data-ttu-id="fe73d-108">配置数据库</span><span class="sxs-lookup"><span data-stu-id="fe73d-108">Configuration Database</span></span>  
 <span data-ttu-id="fe73d-109">使用此字段为部署的程序集指定 BizTalk 配置数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="fe73d-109">You use this field to specify the name of the BizTalk Configuration database for the deployed assembly.</span></span> <span data-ttu-id="fe73d-110">如果将 BizTalk 项目配置为部署项目是如此。</span><span class="sxs-lookup"><span data-stu-id="fe73d-110">This applies if you have configured the BizTalk project as a deployment project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe73d-111">BizTalk 配置数据库也称为 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="fe73d-111">The BizTalk Configuration database is also referred to as the BizTalk Management database.</span></span>  
  
 <span data-ttu-id="fe73d-112">默认配置的数据库名称为 BizTalkMgmtDb。</span><span class="sxs-lookup"><span data-stu-id="fe73d-112">The default Configuration database name is BizTalkMgmtDb.</span></span>  
  
## <a name="server"></a><span data-ttu-id="fe73d-113">“服务器”</span><span class="sxs-lookup"><span data-stu-id="fe73d-113">Server</span></span>  
 <span data-ttu-id="fe73d-114">这是服务器的配置存储库 （也称为 BizTalk 管理数据库或配置数据库） 所在的名称。</span><span class="sxs-lookup"><span data-stu-id="fe73d-114">This is the name of the server where the Configuration repository (also known as the BizTalk Management or Configuration database) is located.</span></span> <span data-ttu-id="fe73d-115">如果配置为"部署"。 在 BizTalk 项目到此服务器部署 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="fe73d-115">You deploy the BizTalk project to this server if you configure the BizTalk project as "Deployment."</span></span>  
  
## <a name="redeploy"></a><span data-ttu-id="fe73d-116">重新部署</span><span class="sxs-lookup"><span data-stu-id="fe73d-116">Redeploy</span></span>  
 <span data-ttu-id="fe73d-117">您使用**重新部署**属性来确定是否删除现有配置并重新创建配置每次部署程序集。</span><span class="sxs-lookup"><span data-stu-id="fe73d-117">You use the **Redeploy** property to determine whether to delete the existing configuration and re-create the configuration each time you deploy the assembly.</span></span> <span data-ttu-id="fe73d-118">默认值是 `True`。</span><span class="sxs-lookup"><span data-stu-id="fe73d-118">The default value is `True`.</span></span>  
  
## <a name="install-to-global-assembly-cache"></a><span data-ttu-id="fe73d-119">安装到全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="fe73d-119">Install to Global Assembly Cache</span></span>  
 <span data-ttu-id="fe73d-120">您使用**安装到全局程序集缓存**属性以指示如果[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]需要 BizTalk 程序集安装到全局程序集缓存 (GAC)。</span><span class="sxs-lookup"><span data-stu-id="fe73d-120">You use the **Install to Global Assembly Cache** property to indicate if [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] needs to install the BizTalk assembly to the global assembly cache (GAC).</span></span>  
  
## <a name="restart-host-instances"></a><span data-ttu-id="fe73d-121">重新启动主机实例</span><span class="sxs-lookup"><span data-stu-id="fe73d-121">Restart Host Instances</span></span>  
 <span data-ttu-id="fe73d-122">如果您设置**重新启动主机实例**到**True**，将部署项目时重新启动本地计算机上的主机实例[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fe73d-122">If you set **Restart Host Instances** to **True**, the host instances on the local computer will be restarted when the project is deployed by [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="fe73d-123">这可在开发周期时，您要进行更改，并经常重新部署;您不需要手动重新启动相关的主机实例。</span><span class="sxs-lookup"><span data-stu-id="fe73d-123">This is useful during the development cycle when you are making changes and frequently redeploying; you will not have to manually restart related host instances.</span></span>  
  
 <span data-ttu-id="fe73d-124">如果不重新启动相关的主机实例，最新的更改可能不反映在 BizTalk 应用程序中，因为旧版本仍可进行缓存。</span><span class="sxs-lookup"><span data-stu-id="fe73d-124">If you do not restart related host instances, your latest changes may not be reflected in your BizTalk application because the old version may still be cached.</span></span> <span data-ttu-id="fe73d-125">重新启动主机实例将清除缓存的程序集。</span><span class="sxs-lookup"><span data-stu-id="fe73d-125">Restarting the host instance purges cached assemblies.</span></span>  
  
## <a name="enable-unit-testing"></a><span data-ttu-id="fe73d-126">启用单元测试</span><span class="sxs-lookup"><span data-stu-id="fe73d-126">Enable Unit Testing</span></span>  
 <span data-ttu-id="fe73d-127">指定是否启用单元测试项目。</span><span class="sxs-lookup"><span data-stu-id="fe73d-127">Specified whether to enable unit testing for the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe73d-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe73d-128">See Also</span></span>  
 <span data-ttu-id="fe73d-129">[如何部署 BizTalk 程序集从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="fe73d-129">[How to Deploy a BizTalk Assembly from Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md) </span></span>  
 [<span data-ttu-id="fe73d-130">BizTalk 项目属性窗口</span><span class="sxs-lookup"><span data-stu-id="fe73d-130">BizTalk Project Properties Window</span></span>](../core/biztalk-project-properties-window.md)