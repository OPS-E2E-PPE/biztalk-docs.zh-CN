---
title: 如何从应用程序和 BizTalk 组中删除策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, policies
- managing [policies], applications
- managing [policies], deleting
- groups, policies
- managing [policies], groups
- applications, policies
ms.assetid: e9882cb3-8808-4258-a107-a24905290288
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: beca719538949bd82b1d9ea442fb12c61c607e14
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335068"
---
# <a name="how-to-remove-a-policy-from-an-application-and-the-biztalk-group"></a><span data-ttu-id="d4c5d-102">如何从应用程序和 BizTalk 组中删除策略</span><span class="sxs-lookup"><span data-stu-id="d4c5d-102">How to Remove a Policy from an Application and the BizTalk Group</span></span>
<span data-ttu-id="d4c5d-103">本主题介绍如何使用 BizTalk Server 管理控制台或命令行从应用程序和 BizTalk 组的规则引擎数据库中删除策略。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-103">This topic describes how to use the BizTalk Server Administration console or the command-line to remove a policy from an application and the Rule Engine database for the BizTalk group.</span></span>  
  
 <span data-ttu-id="d4c5d-104">然后再删除策略，请记住以下重要事项：</span><span class="sxs-lookup"><span data-stu-id="d4c5d-104">Before removing a policy, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="d4c5d-105">无法删除已部署的策略。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-105">You cannot remove a deployed policy.</span></span> <span data-ttu-id="d4c5d-106">您必须首先取消部署策略，如中所述[如何部署或取消部署策略](../core/how-to-deploy-or-undeploy-a-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-106">You must first undeploy the policy, as described in [How to Deploy or Undeploy a Policy](../core/how-to-deploy-or-undeploy-a-policy.md).</span></span> <span data-ttu-id="d4c5d-107">取消部署策略使它处于非活动状态，以便它不再使用 BizTalk 组中的任何应用程序中的函数。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-107">Undeploying a policy makes it inactive so that it no longer functions in any application that uses it in the BizTalk group.</span></span>  
  
-   <span data-ttu-id="d4c5d-108">删除一个策略，将其删除从规则引擎数据库中。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-108">Removing a policy deletes it from the Rule Engine database.</span></span> <span data-ttu-id="d4c5d-109">如果你想要再次使用此策略，您应将其导出到一个.xml 文件，然后再删除它。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-109">If you want to use this policy again, you should export it to an .xml file before removing it.</span></span> <span data-ttu-id="d4c5d-110">有关说明，请参阅[如何导出策略](../core/how-to-export-a-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-110">For instructions, see [How to Export a Policy](../core/how-to-export-a-policy.md).</span></span>  
  
-   <span data-ttu-id="d4c5d-111">如果策略由其他应用程序，它将不再有效的其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-111">If the policy is used by other applications, it will no longer be in effect for the other applications.</span></span> <span data-ttu-id="d4c5d-112">验证不再想要为其删除之前对其进行引用的任何其他应用程序使用策略。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-112">Verify that you no longer want to use the policy for any other applications that reference it before you remove it.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d4c5d-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="d4c5d-113">Prerequisites</span></span>  
 <span data-ttu-id="d4c5d-114">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-114">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="d4c5d-115">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-115">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-remove-a-policy"></a><span data-ttu-id="d4c5d-116">若要删除策略</span><span class="sxs-lookup"><span data-stu-id="d4c5d-116">To remove a policy</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="d4c5d-117">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="d4c5d-117">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="d4c5d-118">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="d4c5d-119">在控制台树中，展开**BizTalk Server 管理**，展开包含该策略的 BizTalk 组删除，，然后展开包含该策略的应用程序</span><span class="sxs-lookup"><span data-stu-id="d4c5d-119">In the console tree, expand  **BizTalk Server Administration**, expand the BizTalk group containing the policy to remove, and then expand the application containing the policy</span></span>  
  
3. <span data-ttu-id="d4c5d-120">单击**策略**，右键单击该策略，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-120">Click **Policies**, right-click the policy, and then click **Remove**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="d4c5d-121">使用命令行</span><span class="sxs-lookup"><span data-stu-id="d4c5d-121">Using the command line</span></span>  
  
1. <span data-ttu-id="d4c5d-122">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-122">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="d4c5d-123">键入以下命令，替换适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="d4c5d-123">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="d4c5d-124">**BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span><span class="sxs-lookup"><span data-stu-id="d4c5d-124">**BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="d4c5d-125">例如：</span><span class="sxs-lookup"><span data-stu-id="d4c5d-125">Example:</span></span>  
  
    <span data-ttu-id="d4c5d-126">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"Rule/Policy1/1.0"**</span><span class="sxs-lookup"><span data-stu-id="d4c5d-126">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"Rule/Policy1/1.0"**</span></span>  
  
   |<span data-ttu-id="d4c5d-127">参数</span><span class="sxs-lookup"><span data-stu-id="d4c5d-127">Parameter</span></span>|<span data-ttu-id="d4c5d-128">Description</span><span class="sxs-lookup"><span data-stu-id="d4c5d-128">Description</span></span>|  
   |---------------|-----------------|  
   |<span data-ttu-id="d4c5d-129">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="d4c5d-129">**/ApplicationName**</span></span>|<span data-ttu-id="d4c5d-130">包含策略的 BizTalk 应用程序若要删除的名称。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-130">Name of the BizTalk application containing the policy to delete.</span></span> <span data-ttu-id="d4c5d-131">如果未指定此参数，则使用默认应用程序。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-131">If this parameter is not specified, the default application is used.</span></span>|  
   |<span data-ttu-id="d4c5d-132">**/Luid**</span><span class="sxs-lookup"><span data-stu-id="d4c5d-132">**/Luid**</span></span>|<span data-ttu-id="d4c5d-133">策略的本地唯一标识符 (LUID)。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-133">Locally unique identifier (LUID) of the policy.</span></span> <span data-ttu-id="d4c5d-134">可通过获得 LUID **ListApp**命令，如中所述[ListApp 命令](../core/listapp-command.md)。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-134">You can obtain the LUID by using the **ListApp** command, as described in [ListApp Command](../core/listapp-command.md).</span></span>|  
   |<span data-ttu-id="d4c5d-135">**/Server**</span><span class="sxs-lookup"><span data-stu-id="d4c5d-135">**/Server**</span></span>|<span data-ttu-id="d4c5d-136">承载 BizTalk 管理数据库的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-136">Name of the SQL Server instance hosting the BizTalk Management database.</span></span> <span data-ttu-id="d4c5d-137">如果指定的 Database 参数被必需。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-137">Required if you specify the Database parameter.</span></span> <span data-ttu-id="d4c5d-138">如果未指定服务器和数据库参数，使用组的默认 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-138">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
   |<span data-ttu-id="d4c5d-139">**/Database**</span><span class="sxs-lookup"><span data-stu-id="d4c5d-139">**/Database**</span></span>|<span data-ttu-id="d4c5d-140">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-140">Name of the BizTalk Management database.</span></span> <span data-ttu-id="d4c5d-141">如果指定的 Server 参数被必需。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-141">Required if you specify the Server parameter.</span></span> <span data-ttu-id="d4c5d-142">如果未指定服务器和数据库参数，使用组的默认 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="d4c5d-142">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4c5d-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4c5d-143">See Also</span></span>  
 [<span data-ttu-id="d4c5d-144">管理策略</span><span class="sxs-lookup"><span data-stu-id="d4c5d-144">Managing Policies</span></span>](../core/managing-policies.md)