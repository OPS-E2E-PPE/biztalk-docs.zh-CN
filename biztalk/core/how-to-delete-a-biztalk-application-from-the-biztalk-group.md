---
title: 如何从 BizTalk 组中删除 BizTalk 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- undeploying, applications
- applications, deleting
- applications, groups
- undeploying, deleting
- managing [applications], deleting
- deleting, applications
- applications, undeploying
- managing [applications], groups
- groups, applications
ms.assetid: 968a6436-ae1a-4f85-bb44-e704826a0197
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3125ef9bc0f30b944c487c2edcba70e1e270dbc4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385375"
---
# <a name="how-to-delete-a-biztalk-application-from-the-biztalk-group"></a><span data-ttu-id="e4ac6-102">如何从 BizTalk 组中删除 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="e4ac6-102">How to Delete a BizTalk Application from the BizTalk Group</span></span>
<span data-ttu-id="e4ac6-103">您可以从 BizTalk 组中删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-103">You can delete an application from the BizTalk group.</span></span> <span data-ttu-id="e4ac6-104">这从组中，BizTalk 数据库中删除其所有数据和应用程序将不再显示在 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-104">This removes all of its data from the BizTalk databases for the group, and the application no longer displays in the BizTalk Server Administration console.</span></span> <span data-ttu-id="e4ac6-105">它不会卸载该应用程序。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-105">It does not uninstall the application.</span></span>  
  
 <span data-ttu-id="e4ac6-106">删除应用程序之前，请切记以下几点：</span><span class="sxs-lookup"><span data-stu-id="e4ac6-106">Before you delete an application, bear in mind the following points:</span></span>  
  
-   <span data-ttu-id="e4ac6-107">必须先停止应用程序，可以将其删除。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-107">The application must be stopped before you can delete it.</span></span> <span data-ttu-id="e4ac6-108">您应该用于完全停止选项停止应用程序，如中所述[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-108">You should use the Full Stop option for stopping the application, as described in [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
-   <span data-ttu-id="e4ac6-109">仅当没有其他应用程序包含对它的引用，可以删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-109">You can delete an application only if no other applications contain references to it.</span></span> <span data-ttu-id="e4ac6-110">如果其他应用程序包含对要删除的应用程序的引用，您必须首先删除从其他应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-110">If other applications contain references to the application you want to remove, you must first remove the references from the other applications.</span></span> <span data-ttu-id="e4ac6-111">有关说明，请参阅[如何删除对另一个应用程序的引用](../core/how-to-remove-a-reference-to-another-application.md)。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-111">For instructions, see [How to Remove a Reference to Another Application](../core/how-to-remove-a-reference-to-another-application.md).</span></span>  
  
-   <span data-ttu-id="e4ac6-112">如果它包含发送端口组中另一个应用程序的发送端口的成员，则无法删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-112">You cannot delete an application if it contains a send port group of which a send port in another application is a member.</span></span> <span data-ttu-id="e4ac6-113">可以删除该应用程序之前，必须取消登记该成员发送端口。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-113">You must unenlist the member send port before you can delete the application.</span></span> <span data-ttu-id="e4ac6-114">有关说明，请参阅[如何取消登记发送端口或发送端口组](../core/how-to-unenlist-a-send-port-or-send-port-group.md)。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-114">For instructions, see [How to Unenlist a Send Port or Send Port Group](../core/how-to-unenlist-a-send-port-or-send-port-group.md).</span></span>  
  
-   <span data-ttu-id="e4ac6-115">如果它包含参与方引用的发送端口，则无法删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-115">You cannot delete an application if it contains a send port that is referenced by a party.</span></span> <span data-ttu-id="e4ac6-116">可以从参与方删除该引用，删除该发送端口，或将发送端口移至不同的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-116">You can delete the reference from the party, delete the send port, or move the send port to a different application.</span></span> <span data-ttu-id="e4ac6-117">有关执行这些任务的说明，请参阅[如何查看或编辑参与方](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca)，[如何删除发送端口](../core/how-to-delete-a-send-port.md)，或[如何将项目移到不同的应用程序](../core/how-to-move-an-artifact-to-a-different-application.md)。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-117">For instructions on performing these tasks, see [How to View or Edit a Party](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca), [How to Delete a Send Port](../core/how-to-delete-a-send-port.md), or [How to Move an Artifact to a Different Application](../core/how-to-move-an-artifact-to-a-different-application.md).</span></span>  
  
-   <span data-ttu-id="e4ac6-118">无法删除默认应用程序。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-118">You cannot delete the default application.</span></span> <span data-ttu-id="e4ac6-119">如果你想要将其删除，必须先将另一个应用程序默认值。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-119">If you want to delete it, you must first make another application the default.</span></span> <span data-ttu-id="e4ac6-120">有关说明，请参阅[如何更改默认应用程序](../core/how-to-change-the-default-application.md)。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-120">For instructions, see [How to Change the Default Application](../core/how-to-change-the-default-application.md).</span></span>  
  
-   <span data-ttu-id="e4ac6-121">如果应用程序中的业务流程具有挂起的实例，则无法删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-121">You cannot delete an application if an orchestration in the application has a suspended instance.</span></span>  
  
-   <span data-ttu-id="e4ac6-122">若要完全取消部署 BizTalk 应用程序，您必须执行中所述的步骤[如何卸载 BizTalk 应用程序](../core/how-to-uninstall-a-biztalk-application.md)，并且可能还需要删除其他文件和设置，如中所述[如何删除其他文件和 BizTalk 应用程序设置](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-122">To completely undeploy a BizTalk application, you must also take the steps described in [How to Uninstall a BizTalk Application](../core/how-to-uninstall-a-biztalk-application.md), and you may also need to remove other files and settings, as described in [How to Remove Other Files and Settings for a BizTalk Application](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e4ac6-123">先决条件</span><span class="sxs-lookup"><span data-stu-id="e4ac6-123">Prerequisites</span></span>  
 <span data-ttu-id="e4ac6-124">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-124">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="e4ac6-125">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-125">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-delete-a-biztalk-application"></a><span data-ttu-id="e4ac6-126">若要删除的 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="e4ac6-126">To delete a BizTalk application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="e4ac6-127">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="e4ac6-127">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="e4ac6-128">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-128">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="e4ac6-129">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-129">In the console tree, expand  **BizTalk Server Administration**, expand the BizTalk group, and expand **Applications**.</span></span>  
  
3. <span data-ttu-id="e4ac6-130">右键单击应用程序文件夹中，然后依次**删除**。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-130">Right-click the application folder, and then click **Delete**.</span></span>  
  
4. <span data-ttu-id="e4ac6-131">单击**是**以确认删除。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-131">Click **Yes** to confirm the deletion.</span></span>  
  
    <span data-ttu-id="e4ac6-132">BizTalk Server 将从 BizTalk 数据库删除所有应用程序数据，并从管理控制台删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-132">BizTalk Server deletes all of the application data from the BizTalk databases and removes the application from the administration console.</span></span>  
  
    <span data-ttu-id="e4ac6-133">如果 BizTalk Server 无法删除的任何应用程序项目，则删除操作失败。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-133">If BizTalk Server cannot delete any of the application artifacts, the delete operation fails.</span></span> <span data-ttu-id="e4ac6-134">在这种情况下，BizTalk Server 将尝试回滚删除操作。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-134">In this case, BizTalk Server attempts to roll back the delete operation.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="e4ac6-135">使用命令行</span><span class="sxs-lookup"><span data-stu-id="e4ac6-135">Using the command line</span></span>  
  
1. <span data-ttu-id="e4ac6-136">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-136">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="e4ac6-137">键入以下命令，替换适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="e4ac6-137">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="e4ac6-138">**BTSTask RemoveApp /ApplicationName:** *value* [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span><span class="sxs-lookup"><span data-stu-id="e4ac6-138">**BTSTask RemoveApp /ApplicationName:** *value* [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="e4ac6-139">例如：</span><span class="sxs-lookup"><span data-stu-id="e4ac6-139">Example:</span></span>  
  
    <span data-ttu-id="e4ac6-140">**BTSTask RemoveApp /ApplicationName:MyApplication**</span><span class="sxs-lookup"><span data-stu-id="e4ac6-140">**BTSTask RemoveApp /ApplicationName:MyApplication**</span></span>  
  
   |<span data-ttu-id="e4ac6-141">参数</span><span class="sxs-lookup"><span data-stu-id="e4ac6-141">Parameter</span></span>|<span data-ttu-id="e4ac6-142">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="e4ac6-142">Value</span></span>|  
   |---------------|-----------|  
   |<span data-ttu-id="e4ac6-143">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="e4ac6-143">**/ApplicationName**</span></span>|<span data-ttu-id="e4ac6-144">若要删除的 BizTalk 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-144">Name of the BizTalk application to delete.</span></span> <span data-ttu-id="e4ac6-145">如果名称包含空格，则必须将其括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-145">If the name includes spaces, you must enclose it in double quotation marks (").</span></span>|  
   |<span data-ttu-id="e4ac6-146">**/Server**</span><span class="sxs-lookup"><span data-stu-id="e4ac6-146">**/Server**</span></span>|<span data-ttu-id="e4ac6-147">承载 BizTalk 管理数据库的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-147">Name of the SQL Server instance hosting the BizTalk Management database.</span></span> <span data-ttu-id="e4ac6-148">如果指定的 Database 参数被必需。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-148">Required if you specify the Database parameter.</span></span> <span data-ttu-id="e4ac6-149">如果未指定服务器和数据库参数，使用组的默认 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-149">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
   |<span data-ttu-id="e4ac6-150">**/Database**</span><span class="sxs-lookup"><span data-stu-id="e4ac6-150">**/Database**</span></span>|<span data-ttu-id="e4ac6-151">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-151">Name of the BizTalk Management database.</span></span> <span data-ttu-id="e4ac6-152">如果指定的 Server 参数被必需。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-152">Required if you specify the Server parameter.</span></span> <span data-ttu-id="e4ac6-153">如果未指定服务器和数据库参数，使用组的默认 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="e4ac6-153">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e4ac6-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4ac6-154">See Also</span></span>  
 <span data-ttu-id="e4ac6-155">[正在取消部署 BizTalk 应用程序](../core/undeploying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="e4ac6-155">[Undeploying BizTalk Applications](../core/undeploying-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="e4ac6-156">部署 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="e4ac6-156">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)