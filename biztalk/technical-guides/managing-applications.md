---
title: "管理应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef1039fb-7460-444b-a45e-2783bdc7c109
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52e525499671a04228763c6792961c3204a3a2d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="managing-applications"></a><span data-ttu-id="6bbff-102">管理应用程序</span><span class="sxs-lookup"><span data-stu-id="6bbff-102">Managing Applications</span></span>
<span data-ttu-id="6bbff-103">BizTalk 应用程序是应用程序项目，比如业务流程、 管道、 架构、 映射和端口的逻辑容器。</span><span class="sxs-lookup"><span data-stu-id="6bbff-103">A BizTalk application is a logical container for application artifacts, such as orchestrations, pipelines, schemas, maps, and ports.</span></span> <span data-ttu-id="6bbff-104">BizTalk 应用程序，可以将相关的组件包括在同一个容器。</span><span class="sxs-lookup"><span data-stu-id="6bbff-104">BizTalk applications enable you to include related components in the same container.</span></span> <span data-ttu-id="6bbff-105">应用程序中的任何项目可以引用到该应用程序中的任何其他项目或在任何被引用的应用程序中的任何项目。</span><span class="sxs-lookup"><span data-stu-id="6bbff-105">Any artifact within an application may refer to any other artifacts within that application, or to any artifact in any referenced application.</span></span> <span data-ttu-id="6bbff-106">可以在 BizTalk 应用程序中的项目的完整列表，请参阅[BizTalk 应用程序是什么？](http://go.microsoft.com/fwlink/?LinkId=154994)</span><span class="sxs-lookup"><span data-stu-id="6bbff-106">For a complete list of artifacts that can be in a BizTalk application, see [What is a BizTalk Application?](http://go.microsoft.com/fwlink/?LinkId=154994)</span></span> <span data-ttu-id="6bbff-107">(http://go.microsoft.com/fwlink/?LinkId=154994)。</span><span class="sxs-lookup"><span data-stu-id="6bbff-107">(http://go.microsoft.com/fwlink/?LinkId=154994).</span></span>  
  
 <span data-ttu-id="6bbff-108">BizTalk 应用程序简化许多每天[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]任务。</span><span class="sxs-lookup"><span data-stu-id="6bbff-108">BizTalk applications streamline many everyday [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tasks.</span></span> <span data-ttu-id="6bbff-109">可以部署、 管理、 启动、 停止和故障排除[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序级别。</span><span class="sxs-lookup"><span data-stu-id="6bbff-109">You can deploy, manage, start, stop, and troubleshoot [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] at the application level.</span></span> <span data-ttu-id="6bbff-110">这会导致的混淆和针对用户错误的风险更低。</span><span class="sxs-lookup"><span data-stu-id="6bbff-110">This results in less confusion and less risk of error for users.</span></span> <span data-ttu-id="6bbff-111">BizTalk 应用程序容器包含</span><span class="sxs-lookup"><span data-stu-id="6bbff-111">A BizTalk application container contains</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6bbff-112">由 Visual Studio 环境部署到它的程序集。</span><span class="sxs-lookup"><span data-stu-id="6bbff-112"> assemblies that are deployed to it by the Visual Studio environment.</span></span> <span data-ttu-id="6bbff-113">应用程序还可能包含接收端口、 接收位置、 发送端口、 属性的跟踪设置，和角色的链接。</span><span class="sxs-lookup"><span data-stu-id="6bbff-113">The application may also contain receive ports, receive locations, send ports, property tracking settings, and role links.</span></span> <span data-ttu-id="6bbff-114">也可以手动添加[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]程序集的应用程序或移动到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从其他应用程序的程序集。</span><span class="sxs-lookup"><span data-stu-id="6bbff-114">You can manually add [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies to the application, or move [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies from other applications.</span></span> <span data-ttu-id="6bbff-115">此外，你可以添加非[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]程序集和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]如业务规则引擎 (BRE) 策略和 BAM 定义文件的项目。</span><span class="sxs-lookup"><span data-stu-id="6bbff-115">In addition, you can add non-[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] artifacts such as Business Rule Engine (BRE) policies and BAM definition files.</span></span> <span data-ttu-id="6bbff-116">隐式应用程序将还包含的所有绑定都由它们的当前设置。</span><span class="sxs-lookup"><span data-stu-id="6bbff-116">Implicitly, the application also contains all of the bindings that are represented by their current settings.</span></span>  
  
 <span data-ttu-id="6bbff-117">你可以创建预或后续处理脚本来执行操作，导入应用程序时，安装或卸载。</span><span class="sxs-lookup"><span data-stu-id="6bbff-117">You can create pre- or post-processing scripts to perform actions when an application is imported, installed, or uninstalled.</span></span> <span data-ttu-id="6bbff-118">有关使用此类脚本的详细信息，请参阅[使用自定义应用程序部署到的前期和后期处理脚本](http://go.microsoft.com/fwlink/?LinkId=154995)(http://go.microsoft.com/fwlink/?LinkId=154995)。</span><span class="sxs-lookup"><span data-stu-id="6bbff-118">For more information about using such scripts, see [Using Pre- and Post-processing Scripts to Customize Application Deployment](http://go.microsoft.com/fwlink/?LinkId=154995) (http://go.microsoft.com/fwlink/?LinkId=154995).</span></span>  
  
 <span data-ttu-id="6bbff-119">本部分介绍如何部署，版本，并更新应用程序或单个项目。</span><span class="sxs-lookup"><span data-stu-id="6bbff-119">This section describes how to deploy, version, and update applications or individual artifacts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6bbff-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="6bbff-120">In This Section</span></span>  
  
-   [<span data-ttu-id="6bbff-121">部署应用程序</span><span class="sxs-lookup"><span data-stu-id="6bbff-121">Deploying an Application</span></span>](../technical-guides/deploying-an-application.md)  
  
-   [<span data-ttu-id="6bbff-122">更新应用程序</span><span class="sxs-lookup"><span data-stu-id="6bbff-122">Updating an Application</span></span>](../technical-guides/updating-an-application.md)