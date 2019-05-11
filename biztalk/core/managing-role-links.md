---
title: 管理角色链接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8860e11-3d2c-450f-a7d2-cc116478999c
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 358f98e35503abeceb41d8e0f799044ceb6539b8
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530369"
---
# <a name="manage-role-links"></a><span data-ttu-id="ac1a0-102">管理角色链接</span><span class="sxs-lookup"><span data-stu-id="ac1a0-102">Manage Role Links</span></span>

## <a name="overview"></a><span data-ttu-id="ac1a0-103">概述</span><span class="sxs-lookup"><span data-stu-id="ac1a0-103">Overview</span></span>
<span data-ttu-id="ac1a0-104">本部分说明了使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来管理 BizTalk 应用程序中的角色链接。</span><span class="sxs-lookup"><span data-stu-id="ac1a0-104">This section provides instructions on using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to manage role links in a BizTalk application.</span></span> <span data-ttu-id="ac1a0-105">角色链接定义商业交易中所涉及参与方之间的关系，并指定双向交互中使用的消息和端口类型。</span><span class="sxs-lookup"><span data-stu-id="ac1a0-105">A role link defines the relationship between parties involved in a business transaction and specifies the message and port types used in the interaction in both directions.</span></span> <span data-ttu-id="ac1a0-106">角色链接的背景信息，请参阅[业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="ac1a0-106">For background information on role links, see [Using Role Links in Orchestrations](../core/using-role-links-in-orchestrations.md).</span></span>  

## <a name="added-to-application"></a><span data-ttu-id="ac1a0-107">添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="ac1a0-107">Added to application</span></span>  
 <span data-ttu-id="ac1a0-108">角色链接内置于[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]并编译到 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="ac1a0-108">Role links are built in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and compiled into BizTalk assemblies.</span></span> <span data-ttu-id="ac1a0-109">不能单独; 添加到应用程序的角色链接角色链接添加到应用程序，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ac1a0-109">You cannot add role links to an application individually; a role link is added to an application as follows:</span></span>  
  
- <span data-ttu-id="ac1a0-110">添加 BizTalk 程序集包含角色链接的应用程序，如中所述[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="ac1a0-110">When you add a BizTalk assembly containing a role link to the application, as described in [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
- <span data-ttu-id="ac1a0-111">某一.msi 文件导入包含 BizTalk 程序集包含角色链接，如中所述的应用程序[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="ac1a0-111">When you import an .msi file into an application that includes a BizTalk assembly containing a role link, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
- <span data-ttu-id="ac1a0-112">当开发人员部署到应用程序包含角色链接中的程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，如中所述[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="ac1a0-112">When a developer deploys into an application an assembly containing a role link from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  

## <a name="deploy-to-production"></a><span data-ttu-id="ac1a0-113">部署到生产环境</span><span class="sxs-lookup"><span data-stu-id="ac1a0-113">Deploy to production</span></span>  
 <span data-ttu-id="ac1a0-114">BizTalk 应用程序开发人员创建角色链接，以实现业务事务，例如你的组织和供应商中涉及的两个或多个参与方之间的通信。</span><span class="sxs-lookup"><span data-stu-id="ac1a0-114">The BizTalk application developer creates role links to implement communications between two or more parties involved in a business transaction, such as your organization and a supplier.</span></span> <span data-ttu-id="ac1a0-115">开发人员不一定是指定在事务中，仅其角色所涉及的参与方。</span><span class="sxs-lookup"><span data-stu-id="ac1a0-115">The developer does not necessarily specify the parties that are involved in the transaction, only their roles.</span></span> <span data-ttu-id="ac1a0-116">若要部署的应用程序包含角色链接到生产环境并启用参与方之间的实际通信，下面的配置必须执行，如本部分中所述：</span><span class="sxs-lookup"><span data-stu-id="ac1a0-116">To deploy an application that includes a role link to a production environment and enable actual communication between the parties, the following configuration must be performed, as described in this section:</span></span>  
  
- <span data-ttu-id="ac1a0-117">如果它未按时完成开发过程中，一个参与方必须分配到角色链接中定义的每个角色。</span><span class="sxs-lookup"><span data-stu-id="ac1a0-117">If it wasn't done during the development process, a party must be assigned to each role defined in the role link.</span></span> <span data-ttu-id="ac1a0-118">这称为"登记"参与方的角色。</span><span class="sxs-lookup"><span data-stu-id="ac1a0-118">This is called "enlisting" a party for a role.</span></span> <span data-ttu-id="ac1a0-119">如果不再需要该参与方分配的角色，可以稍后取消登记参与方。</span><span class="sxs-lookup"><span data-stu-id="ac1a0-119">You can later unenlist the party if you no longer want the party to have the assigned role.</span></span>  
  
- <span data-ttu-id="ac1a0-120">将托管应用程序的 BizTalk 主机实例上，每个参与方的角色链接中定义的逻辑端口必须绑定到物理端口。</span><span class="sxs-lookup"><span data-stu-id="ac1a0-120">The logical ports for each party defined within the role link must be bound to physical ports on the BizTalk host instances that will host the application.</span></span>  
  
  <span data-ttu-id="ac1a0-121">有关开发角色链接的详细信息，请参阅[业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="ac1a0-121">For more information about developing role links, see [Using Role Links in Orchestrations](../core/using-role-links-in-orchestrations.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac1a0-122">Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="ac1a0-122">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="ac1a0-123">有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="ac1a0-123">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="ac1a0-124">下一步</span><span class="sxs-lookup"><span data-stu-id="ac1a0-124">Next step</span></span>
  
-   [<span data-ttu-id="ac1a0-125">如何登记或取消登记角色参与方</span><span class="sxs-lookup"><span data-stu-id="ac1a0-125">How to Enlist or Unenlist a Party for a Role</span></span>](../core/how-to-enlist-or-unenlist-a-party-for-a-role.md)