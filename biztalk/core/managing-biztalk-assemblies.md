---
title: 管理 BizTalk 程序集 |Microsoft Docs
description: 若要使用在 BizTalk Server 中，包括添加、 更新、 查看依赖项，以及删除程序集的程序集的链接
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62cc92f5-a1ea-46e4-88e6-b8a71a0c40a2
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97dd8462aa0656334707d3eea55128b6e1702806
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001782"
---
# <a name="manage-biztalk-assemblies"></a><span data-ttu-id="a8f2e-103">管理 BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="a8f2e-103">Manage BizTalk Assemblies</span></span>

## <a name="overview"></a><span data-ttu-id="a8f2e-104">概述</span><span class="sxs-lookup"><span data-stu-id="a8f2e-104">Overview</span></span>
<span data-ttu-id="a8f2e-105">本部分介绍在将 BizTalk 程序集部署到 BizTalk 组后，如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台或 BTSTask 命令行工具对其进行管理。</span><span class="sxs-lookup"><span data-stu-id="a8f2e-105">This section provides instructions on using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console or the BTSTask command-line tool to manage BizTalk assemblies after they have been deployed into a BizTalk group.</span></span> <span data-ttu-id="a8f2e-106">BizTalk 程序集是一个 Microsoft Windows DLL 文件，包含 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务解决方案中要使用的资源信息，如业务流程、管道、架构和映射。</span><span class="sxs-lookup"><span data-stu-id="a8f2e-106">A BizTalk assembly is a Microsoft Windows DLL file that contains resource information, such as orchestrations, pipelines, schemas, and maps to be used in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] business solution.</span></span> <span data-ttu-id="a8f2e-107">BizTalk 程序集的背景信息，请参阅[BizTalk 程序集](../core/biztalk-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="a8f2e-107">For background information on BizTalk assemblies, see [BizTalk Assemblies](../core/biztalk-assemblies.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a8f2e-108">部署或取消部署属性架构可能会暴露敏感数据，进而在跟踪中暴露敏感信息。</span><span class="sxs-lookup"><span data-stu-id="a8f2e-108">Deploying or undeploying a property schema may expose sensitive data, and subsequently expose sensitive information during tracking.</span></span> <span data-ttu-id="a8f2e-109">只要部署或取消部署包含属性架构的程序集，事件查看器就会在 Windows 应用程序事件日志中记录该事件。</span><span class="sxs-lookup"><span data-stu-id="a8f2e-109">Whenever an assembly containing a property schema is deployed or undeployed, the event viewer logs an event in the Windows Application Event Log.</span></span> <span data-ttu-id="a8f2e-110">您应该在事件日志中检查这些消息，以确保所有程序集部署活动均符合您的敏感数据策略。</span><span class="sxs-lookup"><span data-stu-id="a8f2e-110">You should check the event log for these messages to ensure that all assembly deployment activities are in line with your policies for any sensitive data.</span></span> <span data-ttu-id="a8f2e-111">(部署为事件日志中生成的消息:"用户"{1}"已部署程序集"{0}"包含属性架构"。</span><span class="sxs-lookup"><span data-stu-id="a8f2e-111">(The message generated to the Event Log for deployment is: "The user "{1}" deployed the assembly "{0}" containing property schemas."</span></span> <span data-ttu-id="a8f2e-112">取消部署为事件日志中生成的消息:"用户"{1}"已取消部署程序集"{0}"包含属性架构"。)</span><span class="sxs-lookup"><span data-stu-id="a8f2e-112">The message generated to the Event Log for undeployment is: "The user "{1}" undeployed the assembly "{0}" containing property schemas.")</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="a8f2e-113">Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="a8f2e-113">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="a8f2e-114">有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="a8f2e-114">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="a8f2e-115">开发人员可使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]开发 BizTalk 程序集，如中所述[开发 BizTalk Server 应用程序](../core/developing-biztalk-server-applications.md)，并可以将其从部署[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中所述[部署从 Visual Studio 到 BizTalk 应用程序的 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="a8f2e-115">The developer uses [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to develop BizTalk assemblies, as described in [Developing BizTalk Server Applications](../core/developing-biztalk-server-applications.md), and can deploy them from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span> <span data-ttu-id="a8f2e-116">开发人员也可以通过在开发过程中使用管理控制台来管理 BizTalk 程序集，如本部分所述。</span><span class="sxs-lookup"><span data-stu-id="a8f2e-116">The developer can also manage BizTalk assemblies during the development process by using either the administration console, as described in this section.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a8f2e-117">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a8f2e-117">Next steps</span></span> 
  
-   [<span data-ttu-id="a8f2e-118">向应用程序中添加 BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="a8f2e-118">Add a BizTalk Assembly to an Application</span></span>](../core/how-to-add-a-biztalk-assembly-to-an-application.md)  
  
-   [<span data-ttu-id="a8f2e-119">修改 BizTalk 程序集的部署选项</span><span class="sxs-lookup"><span data-stu-id="a8f2e-119">Modify the Deployment Options of a BizTalk Assembly</span></span>](../core/how-to-modify-the-deployment-options-of-a-biztalk-assembly.md)  
  
-   [<span data-ttu-id="a8f2e-120">查看 BizTalk 程序集的依赖关系</span><span class="sxs-lookup"><span data-stu-id="a8f2e-120">View the Dependencies for a BizTalk Assembly</span></span>](../core/how-to-view-the-dependencies-for-a-biztalk-assembly.md)  
  
-   [<span data-ttu-id="a8f2e-121">从应用程序中删除 BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="a8f2e-121">Remove a BizTalk Assembly from an Application</span></span>](../core/how-to-remove-a-biztalk-assembly-from-an-application.md)