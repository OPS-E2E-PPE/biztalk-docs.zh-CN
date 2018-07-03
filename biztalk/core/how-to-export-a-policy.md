---
title: 如何导出策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [policies], exporting
- policies, exporting
- exporting, policies
ms.assetid: 2e46d96a-7762-479b-be20-bd590b2a4f0a
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71d697d378e48b516e3afd2ebae82cb897af12a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011462"
---
# <a name="how-to-export-a-policy"></a><span data-ttu-id="95858-102">如何导出策略</span><span class="sxs-lookup"><span data-stu-id="95858-102">How to Export a Policy</span></span>
<span data-ttu-id="95858-103">本主题介绍如何使用 BizTalk Server 管理控制台或命令行导出一个或多个策略以及关联词汇。</span><span class="sxs-lookup"><span data-stu-id="95858-103">This topic describes how to use the BizTalk Server Administration console or the command line to export one or more policies and associated vocabularies.</span></span>  
  
 <span data-ttu-id="95858-104">导出策略时，请切记以下几点：</span><span class="sxs-lookup"><span data-stu-id="95858-104">When exporting a policy, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="95858-105">使用 BizTalk Server 管理控制台，您可以从 BizTalk 组或 BizTalk 应用程序导出策略以及要导出的词汇。</span><span class="sxs-lookup"><span data-stu-id="95858-105">Using the BizTalk Server Administration console, you can export policies from a BizTalk group or a BizTalk application as well as the vocabularies to export.</span></span> <span data-ttu-id="95858-106">使用 BTSTask，您可以从某一应用程序导出策略，并且还将导出所有关联的词汇。</span><span class="sxs-lookup"><span data-stu-id="95858-106">Using BTSTask, you can export policies from an application, and all of the associated vocabularies will be exported as well.</span></span> <span data-ttu-id="95858-107">您不能选择要导出的词汇。</span><span class="sxs-lookup"><span data-stu-id="95858-107">You cannot select the vocabularies to export.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="95858-108">在使用管理控制台时，您可以选择要导出哪些词汇。</span><span class="sxs-lookup"><span data-stu-id="95858-108">When using the administration console, you can select which vocabularies to export.</span></span> <span data-ttu-id="95858-109">我们建议您选择导出与某一策略关联的所有词汇。</span><span class="sxs-lookup"><span data-stu-id="95858-109">We recommend that you select for export all of the vocabularies associated with a policy.</span></span> <span data-ttu-id="95858-110">这样，就可以确保在目标环境中存在所需的词汇。</span><span class="sxs-lookup"><span data-stu-id="95858-110">This way, you can be sure that the required vocabularies are present in the destination environment.</span></span> <span data-ttu-id="95858-111">即使所需的词汇以前已部署到该目标环境中，但如果其关联的策略被删除，则这些词汇也会被删除。</span><span class="sxs-lookup"><span data-stu-id="95858-111">Even if the required vocabularies were previously deployed to the destination environment, if their associated policy was deleted, they would have been deleted as well.</span></span> <span data-ttu-id="95858-112">这是因为，在删除某一策略时，该策略的未由其他策略使用的所有词汇都将被删除。</span><span class="sxs-lookup"><span data-stu-id="95858-112">This is because when you delete a policy, all of its vocabularies that are not being used by another policy are deleted.</span></span>  
  
-   <span data-ttu-id="95858-113">您然后可以导入或多个策略到不同的 BizTalk 组或不同的 BizTalk 组中的应用程序中所述[如何导入策略](../core/how-to-import-a-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="95858-113">You can then import the policy or policies into a different BizTalk group or an application in a different BizTalk group, as described in [How to Import a Policy](../core/how-to-import-a-policy.md).</span></span>  
  
-   <span data-ttu-id="95858-114">在您可以导出某一策略前，该策略必须存在于 BizTalk 组的规则引擎数据库中。</span><span class="sxs-lookup"><span data-stu-id="95858-114">Before you can export a policy, it must exist in the Rule Engine database for the BizTalk group.</span></span> <span data-ttu-id="95858-115">有几种方法将策略导入到规则引擎数据库中，如中所述[如何导入策略](../core/how-to-import-a-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="95858-115">There are several ways to import a policy into the Rule Engine database, as described in [How to Import a Policy](../core/how-to-import-a-policy.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95858-116">在使用规则引擎部署向导从规则引擎数据库中删除某个策略时，该策略仍将会在管理控制台中显示，但您将无法导出该策略。</span><span class="sxs-lookup"><span data-stu-id="95858-116">When you remove a policy from the Rule Engine database by using the Rule Engine Deployment Wizard, it will still display in the administration console, but you will not be able to export it.</span></span> <span data-ttu-id="95858-117">有关规则引擎部署向导的详细信息，请参阅[如何部署和取消部署策略及词汇](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)。</span><span class="sxs-lookup"><span data-stu-id="95858-117">For more information about the Rule Engine Deployment Wizard, see [How to Deploy and Undeploy Policies and Vocabularies](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md).</span></span>  
  
-   <span data-ttu-id="95858-118">在使用管理控制台进行导出时，策略和词汇将导出到某一 .xml 文件中。</span><span class="sxs-lookup"><span data-stu-id="95858-118">When you use the administration console for exporting, the policies and vocabularies are exported into an .xml file.</span></span> <span data-ttu-id="95858-119">在使用 BTSTask 命令行工具进行导出时，策略和词汇将导出到某一应用程序 .msi 文件中。</span><span class="sxs-lookup"><span data-stu-id="95858-119">When you use the BTSTask command-line tool for exporting, the policies and vocabularies are exported into an application .msi file.</span></span>  
  
-   <span data-ttu-id="95858-120">BTSTask 并不为导出策略提供特定的命令；但是，可以使用 BTSTask 的 ExportApp 命令有选择地只导出所需策略，而不导出其他项目。</span><span class="sxs-lookup"><span data-stu-id="95858-120">BTSTask does not provide a specific command for exporting policies; however you can use the ExportApp command of BTSTask to selectively export only the policies you want, and no other artifacts.</span></span> <span data-ttu-id="95858-121">这将生成一个包含这些策略的应用程序 .msi 文件。</span><span class="sxs-lookup"><span data-stu-id="95858-121">This generates an application .msi file containing the policies.</span></span> <span data-ttu-id="95858-122">您可以使用 ImportApp 命令将该 .msi 文件导入不同的 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="95858-122">You can use the ImportApp command to import the .msi file into a different BizTalk group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="95858-123">必要條件</span><span class="sxs-lookup"><span data-stu-id="95858-123">Prerequisites</span></span>  
 <span data-ttu-id="95858-124">以下为执行本主题中步骤的前提条件：</span><span class="sxs-lookup"><span data-stu-id="95858-124">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
-   <span data-ttu-id="95858-125">您必须以 BizTalk Server Administrators 组成员的帐户身份登录。</span><span class="sxs-lookup"><span data-stu-id="95858-125">You must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="95858-126">详细了解权限的详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="95858-126">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
-   <span data-ttu-id="95858-127">必须安装业务规则引擎。</span><span class="sxs-lookup"><span data-stu-id="95858-127">The Business Rule Engine must be installed.</span></span> <span data-ttu-id="95858-128">有关详细信息，请参阅[BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)。</span><span class="sxs-lookup"><span data-stu-id="95858-128">For more information, see [Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5).</span></span>  
  
-   <span data-ttu-id="95858-129">您要导出的策略必须存在于 BizTalk 组的规则引擎数据库中。</span><span class="sxs-lookup"><span data-stu-id="95858-129">The policy that you want to export must exist in the Rule Engine database for the BizTalk group.</span></span> <span data-ttu-id="95858-130">如果您要从某一应用程序导出策略，则该策略必须也已经添加到该应用程序中。</span><span class="sxs-lookup"><span data-stu-id="95858-130">If you want to export the policy from an application, it must have also been added to the application as well.</span></span>  
  
## <a name="to-export-a-policy"></a><span data-ttu-id="95858-131">导出策略</span><span class="sxs-lookup"><span data-stu-id="95858-131">To export a policy</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="95858-132">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="95858-132">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="95858-133">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="95858-133">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="95858-134">在控制台树中，展开**BizTalk Server 管理**和相应的 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="95858-134">In the console tree, expand **BizTalk Server Administration** and expand the BizTalk group.</span></span>  
  
3. <span data-ttu-id="95858-135">如果你想要选择要从 BizTalk 组右键单击中的策略的所有导出的策略**应用程序**文件夹中，单击**导出**，然后单击**策略**。</span><span class="sxs-lookup"><span data-stu-id="95858-135">If you want to select the policies to export from all of the policies in a BizTalk group right-click the **Applications** folder, click **Export**, and then click **Policies**.</span></span>  
  
    <span data-ttu-id="95858-136">或</span><span class="sxs-lookup"><span data-stu-id="95858-136">OR</span></span>  
  
    <span data-ttu-id="95858-137">如果你想要导出的策略为特定应用程序，展开应用程序文件夹，右键单击该应用程序，单击**导出**，然后单击**策略**。</span><span class="sxs-lookup"><span data-stu-id="95858-137">If you want to export the policies in a particular application, expand the Applications folder, right-click the application, click **Export**, and then click **Policies**.</span></span>  
  
    <span data-ttu-id="95858-138">或</span><span class="sxs-lookup"><span data-stu-id="95858-138">OR</span></span>  
  
    <span data-ttu-id="95858-139">如果你想要导出特定策略，单击包含该策略的策略文件夹，右键单击该策略，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="95858-139">If you want to export only a particular policy, click the Policies folder that contains the policy, right-click the policy, and then click **Export**.</span></span>  
  
4. <span data-ttu-id="95858-140">在导出策略页上，在**要导出的策略**，选择要导出的策略。</span><span class="sxs-lookup"><span data-stu-id="95858-140">On the Export Policies page, in **Policies to export**, select the policies to export.</span></span>  
  
5. <span data-ttu-id="95858-141">在中**要导出的词汇**，选中要导出的词汇的复选框并清除不希望导出所有词汇的复选框。</span><span class="sxs-lookup"><span data-stu-id="95858-141">In **Vocabularies to export**, select the check boxes of the vocabularies to export, and clear the checkboxes of any vocabularies you do not want to export.</span></span> <span data-ttu-id="95858-142">该策略所使用的词汇将会自动选择。</span><span class="sxs-lookup"><span data-stu-id="95858-142">The vocabularies used by this policy are automatically selected.</span></span>  
  
6. <span data-ttu-id="95858-143">在中**要导出的文件**，键入要导出策略或策略的 XML 文件的路径，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="95858-143">In **File to export** into, type the path of the XML file to which to export the policy or policies, and then click **OK**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="95858-144">使用命令行</span><span class="sxs-lookup"><span data-stu-id="95858-144">Using the command line</span></span>  
  
1.  <span data-ttu-id="95858-145">使用 BTSTask ListApp 命令与 /ResourceSpec 选项来生成一个 XML 文件，其中列出了要从中导出策略，如中所述的 BizTalk 应用程序中的项目[ListApp 命令](../core/listapp-command.md)。</span><span class="sxs-lookup"><span data-stu-id="95858-145">Use the BTSTask ListApp command with the /ResourceSpec option to generate an XML file that lists the artifacts in the BizTalk application from which you want to export a policy, as described in [ListApp Command](../core/listapp-command.md).</span></span>  
  
2.  <span data-ttu-id="95858-146">编辑在前一步骤中生成的 XML 文件，删除除您要导出的策略外的所有项目。</span><span class="sxs-lookup"><span data-stu-id="95858-146">Edit the XML file generated in the previous step, deleting all of the artifacts except for the policy or policies that you want to export.</span></span>  
  
3.  <span data-ttu-id="95858-147">使用 BTSTask ExportApp 命令，并且为 /ResourceSpec 参数指定已修改的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="95858-147">Use the BTSTask ExportApp command, and specify the modified XML file for the /ResourceSpec parameter.</span></span> <span data-ttu-id="95858-148">有关详细信息，请参阅[ExportApp 命令](../core/exportapp-command.md)。</span><span class="sxs-lookup"><span data-stu-id="95858-148">For more information, see [ExportApp Command](../core/exportapp-command.md).</span></span>  
  
     <span data-ttu-id="95858-149">BTSTask 将指定的策略及其所有关联的词汇都导出到应用程序 .msi 文件中。</span><span class="sxs-lookup"><span data-stu-id="95858-149">BTSTask exports the specified policies and all of their associated vocabularies into an application .msi file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95858-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="95858-150">See Also</span></span>  
 <span data-ttu-id="95858-151">[导出 BizTalk 应用程序、 绑定和策略](../core/exporting-biztalk-applications-bindings-and-policies.md) </span><span class="sxs-lookup"><span data-stu-id="95858-151">[Exporting BizTalk Applications, Bindings, and Policies](../core/exporting-biztalk-applications-bindings-and-policies.md) </span></span>  
 [<span data-ttu-id="95858-152">管理策略</span><span class="sxs-lookup"><span data-stu-id="95858-152">Managing Policies</span></span>](../core/managing-policies.md)