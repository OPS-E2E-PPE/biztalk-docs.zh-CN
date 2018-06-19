---
title: 如何从应用程序删除业务流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, orchestrations
- deleting, orchestrations
- managing [orchestrations], deleting
- orchestrations, applications
- orchestrations, deleting
ms.assetid: e6d635ea-3513-42de-a667-b56c536e5328
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef4909f5430ae2d0435d519823abe9735cbc1cc4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255189"
---
# <a name="how-to-remove-an-orchestration-from-an-application"></a><span data-ttu-id="9e440-102">如何从应用程序删除业务流程</span><span class="sxs-lookup"><span data-stu-id="9e440-102">How to Remove an Orchestration from an Application</span></span>
<span data-ttu-id="9e440-103">本主题介绍如何使用 BizTalk Server 管理控制台或命令行从 BizTalk 应用程序中删除业务流程。</span><span class="sxs-lookup"><span data-stu-id="9e440-103">This topic describes how to use the BizTalk Server Administration console or the command line to remove an orchestration from a BizTalk application.</span></span> <span data-ttu-id="9e440-104">从应用程序中删除业务流程，也会将该业务流程从 BizTalk 组的 BizTalk 管理数据库中删除。</span><span class="sxs-lookup"><span data-stu-id="9e440-104">Removing an orchestration from an application also deletes it from the BizTalk Management database for the BizTalk group.</span></span>  
  
 <span data-ttu-id="9e440-105">删除业务流程时，将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9e440-105">When you remove an orchestration, the following occurs:</span></span>  
  
-   <span data-ttu-id="9e440-106">将从 BizTalk 管理数据库中删除该业务流程。</span><span class="sxs-lookup"><span data-stu-id="9e440-106">The orchestration is deleted from the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="9e440-107">将删除 BizTalk 管理数据库中包含该业务流程的 BizTalk 程序集，如果该程序集还存在于本地文件系统或全局程序集缓存 (GAC) 中，则不会将这两个位置中的该程序集删除。</span><span class="sxs-lookup"><span data-stu-id="9e440-107">The BizTalk assembly that contains the orchestration is deleted from the BizTalk Management database, but is not removed from the local file system or the global assembly cache (GAC), if it exists in these locations.</span></span>  
  
-   <span data-ttu-id="9e440-108">由于删除了 BizTalk 程序集，因此也将从 BizTalk 管理数据库中删除该程序集所包含的所有项目。</span><span class="sxs-lookup"><span data-stu-id="9e440-108">As a consequence of the BizTalk assembly being deleted, all artifacts contained in the assembly are deleted from the BizTalk Management database as well.</span></span>  
  
 <span data-ttu-id="9e440-109">从应用程序中删除业务流程前，请切记以下几点：</span><span class="sxs-lookup"><span data-stu-id="9e440-109">Before removing an orchestration from an application, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="9e440-110">如果有其他项目依赖于此业务流程或依赖于将连带删除的程序集中包含的项目，则删除此业务流程后这些项目将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="9e440-110">If other artifacts have dependencies on this orchestration or the artifacts contained in the assembly that will also be removed, they will no longer function correctly when you remove the orchestration.</span></span> <span data-ttu-id="9e440-111">有关依赖关系的背景信息，请参阅[依赖关系和应用程序部署](../core/dependencies-and-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="9e440-111">For background information about dependencies, see [Dependencies and Application Deployment](../core/dependencies-and-application-deployment.md).</span></span>  
  
-   <span data-ttu-id="9e440-112">不能删除有正在运行的实例的业务流程。</span><span class="sxs-lookup"><span data-stu-id="9e440-112">You cannot remove an orchestration that has running instances.</span></span> <span data-ttu-id="9e440-113">必须终止任何正在运行的实例。</span><span class="sxs-lookup"><span data-stu-id="9e440-113">You must terminate any running instances.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9e440-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="9e440-114">Prerequisites</span></span>  
 <span data-ttu-id="9e440-115">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="9e440-115">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="9e440-116">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="9e440-116">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-remove-an-orchestration-from-an-application"></a><span data-ttu-id="9e440-117">从应用程序中删除业务流程</span><span class="sxs-lookup"><span data-stu-id="9e440-117">To remove an orchestration from an application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="9e440-118">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="9e440-118">Using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="9e440-119">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="9e440-119">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="9e440-120">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含你想要删除的业务流程的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9e440-120">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration that you want to remove.</span></span>  
  
3.  <span data-ttu-id="9e440-121">单击**业务流程**，业务流程中，右键单击，然后单击**Unenlist**。</span><span class="sxs-lookup"><span data-stu-id="9e440-121">Click **Orchestrations**, right-click the orchestration, and then click **Unenlist**.</span></span>  
  
4.  <span data-ttu-id="9e440-122">选择的业务流程，指向**视图**，然后单击**实例信息**。</span><span class="sxs-lookup"><span data-stu-id="9e440-122">Select the orchestration, point to **View**, and then click **Instance Information**.</span></span>  
  
5.  <span data-ttu-id="9e440-123">在查询结果窗格中，业务流程实例中，右键单击，然后单击**终止**。</span><span class="sxs-lookup"><span data-stu-id="9e440-123">In the query results pane, right-click the orchestration instances, and then click **Terminate**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9e440-124">可以取消登记、 终止正在运行的实例，并停止所有的应用程序中的业务流程一次通过使用应用程序，完全停止选项中所述[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="9e440-124">You can unenlist, terminate running instances, and stop all of the orchestrations in an application at once by using the Full Stop option for the application, as described in [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
6.  <span data-ttu-id="9e440-125">单击**业务流程**，业务流程中，右键单击，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="9e440-125">Click **Orchestrations**, right-click the orchestration, and then click **Remove**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="9e440-126">使用命令行</span><span class="sxs-lookup"><span data-stu-id="9e440-126">Using the command line</span></span>  
  
1.  <span data-ttu-id="9e440-127">如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9e440-127">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="9e440-128">键入以下命令，替换为适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="9e440-128">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
     <span data-ttu-id="9e440-129">**BTSTask RemoveResource** [**/ApplicationName:***值*] **/Luid:***值*[**/Server:***值*] [**/数据库：***值*]</span><span class="sxs-lookup"><span data-stu-id="9e440-129">**BTSTask RemoveResource** [**/ApplicationName:***value*] **/Luid:***value* [**/Server:***value*] [**/Database:***value*]</span></span>  
  
     <span data-ttu-id="9e440-130">例如：</span><span class="sxs-lookup"><span data-stu-id="9e440-130">Example:</span></span>  
  
     <span data-ttu-id="9e440-131">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations，版本 = 1.0.0.0，Culture = neutral，PublicKeyToken = 0123456789ABCDEF"**</span><span class="sxs-lookup"><span data-stu-id="9e440-131">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**</span></span>  
  
    |<span data-ttu-id="9e440-132">参数</span><span class="sxs-lookup"><span data-stu-id="9e440-132">Parameter</span></span>|<span data-ttu-id="9e440-133">Description</span><span class="sxs-lookup"><span data-stu-id="9e440-133">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="9e440-134">**/ 应用程序名称**</span><span class="sxs-lookup"><span data-stu-id="9e440-134">**/ApplicationName**</span></span>|<span data-ttu-id="9e440-135">包含要删除的业务流程的 BizTalk 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="9e440-135">Name of the BizTalk application containing the orchestration to delete.</span></span> <span data-ttu-id="9e440-136">如果名称包含空格，必须将它括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="9e440-136">If the name includes spaces, you must enclose it in double quotation marks (").</span></span> <span data-ttu-id="9e440-137">如果未指定此参数，则使用默认的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9e440-137">If this parameter is not specified, the default application is used.</span></span>|  
    |<span data-ttu-id="9e440-138">**/ Luid**</span><span class="sxs-lookup"><span data-stu-id="9e440-138">**/Luid**</span></span>|<span data-ttu-id="9e440-139">业务流程的本地唯一标识符 (LUID)。</span><span class="sxs-lookup"><span data-stu-id="9e440-139">Locally unique identifier (LUID) of the orchestration.</span></span> <span data-ttu-id="9e440-140">你可以通过使用获取而定[ListApp 命令](../core/listapp-command.md)。</span><span class="sxs-lookup"><span data-stu-id="9e440-140">You can obtain the LUID by using the [ListApp Command](../core/listapp-command.md).</span></span>|  
    |<span data-ttu-id="9e440-141">**/ 服务器**</span><span class="sxs-lookup"><span data-stu-id="9e440-141">**/Server**</span></span>|<span data-ttu-id="9e440-142">承载 BizTalk 管理数据库的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="9e440-142">Name of the SQL Server instance hosting the BizTalk Management database.</span></span> <span data-ttu-id="9e440-143">如果指定了“Database”参数，则此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="9e440-143">Required if you specify the Database parameter.</span></span> <span data-ttu-id="9e440-144">如果未指定“Server”参数和“Database”参数，则使用组的默认 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="9e440-144">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
    |<span data-ttu-id="9e440-145">**/ 数据库**</span><span class="sxs-lookup"><span data-stu-id="9e440-145">**/Database**</span></span>|<span data-ttu-id="9e440-146">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="9e440-146">Name of the BizTalk Management database.</span></span> <span data-ttu-id="9e440-147">如果指定了“Server”参数，则此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="9e440-147">Required if you specify the Server parameter.</span></span> <span data-ttu-id="9e440-148">如果未指定“Server”参数和“Database”参数，则使用组的默认 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="9e440-148">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9e440-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e440-149">See Also</span></span>  
 <span data-ttu-id="9e440-150">[管理业务流程](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="9e440-150">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 [<span data-ttu-id="9e440-151">RemoveResource 命令</span><span class="sxs-lookup"><span data-stu-id="9e440-151">RemoveResource Command</span></span>](../core/removeresource-command.md)