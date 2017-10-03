---
title: "管理角色链接 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8860e11-3d2c-450f-a7d2-cc116478999c
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07f85bfe0d16b3963b0ba18585220f508f679346
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="manage-role-links"></a><span data-ttu-id="64e12-102">管理角色的链接</span><span class="sxs-lookup"><span data-stu-id="64e12-102">Manage Role Links</span></span>

## <a name="overview"></a><span data-ttu-id="64e12-103">概述</span><span class="sxs-lookup"><span data-stu-id="64e12-103">Overview</span></span>
<span data-ttu-id="64e12-104">本部分说明如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台来管理 BizTalk 应用程序中的角色链接。</span><span class="sxs-lookup"><span data-stu-id="64e12-104">This section provides instructions on using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to manage role links in a BizTalk application.</span></span> <span data-ttu-id="64e12-105">角色链接定义商业交易参与方之间的关系并指定双向交互中使用的消息类型和端口类型。</span><span class="sxs-lookup"><span data-stu-id="64e12-105">A role link defines the relationship between parties involved in a business transaction and specifies the message and port types used in the interaction in both directions.</span></span> <span data-ttu-id="64e12-106">在角色链接上的背景信息，请参阅[在业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="64e12-106">For background information on role links, see [Using Role Links in Orchestrations](../core/using-role-links-in-orchestrations.md).</span></span>  

## <a name="added-to-application"></a><span data-ttu-id="64e12-107">添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="64e12-107">Added to application</span></span>  
 <span data-ttu-id="64e12-108">内置角色链接[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]和编译到 BizTalk 程序集中。</span><span class="sxs-lookup"><span data-stu-id="64e12-108">Role links are built in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and compiled into BizTalk assemblies.</span></span> <span data-ttu-id="64e12-109">不能向应用程序中单独地添加角色链接，而应按照以下方式向应用程序中添加角色链接：</span><span class="sxs-lookup"><span data-stu-id="64e12-109">You cannot add role links to an application individually; a role link is added to an application as follows:</span></span>  
  
-   <span data-ttu-id="64e12-110">当你添加 BizTalk 程序集包含应用程序，角色链接中所述[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="64e12-110">When you add a BizTalk assembly containing a role link to the application, as described in [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
-   <span data-ttu-id="64e12-111">当你导入的应用程序中所述包括 BizTalk 程序集包含角色链接，.msi 文件[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="64e12-111">When you import an .msi file into an application that includes a BizTalk assembly containing a role link, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
-   <span data-ttu-id="64e12-112">当开发人员将部署到应用程序包含中的角色链接的程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]中所述，[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="64e12-112">When a developer deploys into an application an assembly containing a role link from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  

## <a name="deploy-to-production"></a><span data-ttu-id="64e12-113">部署到生产环境</span><span class="sxs-lookup"><span data-stu-id="64e12-113">Deploy to production</span></span>  
 <span data-ttu-id="64e12-114">BizTalk 应用程序开发人员创建角色链接以实现商业交易中两个或多个参与方（如您的组织与供应商）之间的通信。</span><span class="sxs-lookup"><span data-stu-id="64e12-114">The BizTalk application developer creates role links to implement communications between two or more parties involved in a business transaction, such as your organization and a supplier.</span></span> <span data-ttu-id="64e12-115">开发人员不必指定参与交易的参与方，只需指定他们的角色。</span><span class="sxs-lookup"><span data-stu-id="64e12-115">The developer does not necessarily specify the parties that are involved in the transaction, only their roles.</span></span> <span data-ttu-id="64e12-116">若要将包含角色链接的应用程序部署到生产环境，并启用参与方之间的实际通信，必须执行以下配置，如本部分中所述：</span><span class="sxs-lookup"><span data-stu-id="64e12-116">To deploy an application that includes a role link to a production environment and enable actual communication between the parties, the following configuration must be performed, as described in this section:</span></span>  
  
-   <span data-ttu-id="64e12-117">必须为参与方分配一个角色链接中定义的角色（如果在开发过程中未指定）。</span><span class="sxs-lookup"><span data-stu-id="64e12-117">If it wasn't done during the development process, a party must be assigned to each role defined in the role link.</span></span> <span data-ttu-id="64e12-118">此操作称为“登记”参与方的角色。</span><span class="sxs-lookup"><span data-stu-id="64e12-118">This is called "enlisting" a party for a role.</span></span> <span data-ttu-id="64e12-119">登记后，如果您希望该参与方不再是指定的角色，则可以取消登记该参与方。</span><span class="sxs-lookup"><span data-stu-id="64e12-119">You can later unenlist the party if you no longer want the party to have the assigned role.</span></span>  
  
-   <span data-ttu-id="64e12-120">角色链接中定义的每个参与方的逻辑端口都必须绑定到应用程序的宿主 BizTalk 主机实例上的物理端口。</span><span class="sxs-lookup"><span data-stu-id="64e12-120">The logical ports for each party defined within the role link must be bound to physical ports on the BizTalk host instances that will host the application.</span></span>  
  
 <span data-ttu-id="64e12-121">有关开发角色链接的详细信息，请参阅[在业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="64e12-121">For more information about developing role links, see [Using Role Links in Orchestrations](../core/using-role-links-in-orchestrations.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64e12-122">Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="64e12-122">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="64e12-123">有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="64e12-123">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="64e12-124">下一步</span><span class="sxs-lookup"><span data-stu-id="64e12-124">Next step</span></span>
  
-   [<span data-ttu-id="64e12-125">如何登记或取消登记角色方</span><span class="sxs-lookup"><span data-stu-id="64e12-125">How to Enlist or Unenlist a Party for a Role</span></span>](../core/how-to-enlist-or-unenlist-a-party-for-a-role.md)