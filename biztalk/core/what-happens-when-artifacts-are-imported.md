---
title: "导入项目时，会发生什么情况 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing, artifacts
- artifacts, importing
ms.assetid: a83957df-6e16-419a-b693-87985b498cc4
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d87e814fd43545d18db0d6e4fd0c585279eb5261
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-happens-when-artifacts-are-imported"></a><span data-ttu-id="c8441-102">导入项目时发生的情况</span><span class="sxs-lookup"><span data-stu-id="c8441-102">What Happens When Artifacts Are Imported</span></span>
<span data-ttu-id="c8441-103">本主题介绍导入项目时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="c8441-103">This topic describes what happens to artifacts when they are imported.</span></span> <span data-ttu-id="c8441-104">可以通过本主题介绍的三种方式导入项目：</span><span class="sxs-lookup"><span data-stu-id="c8441-104">There are three ways to import artifacts, which are covered in this topic:</span></span>  
  
-   <span data-ttu-id="c8441-105">将 BizTalk .msi 文件中的项目导入到 BizTalk 组或应用程序</span><span class="sxs-lookup"><span data-stu-id="c8441-105">Importing artifacts in a BizTalk .msi file into a BizTalk group or application</span></span>  
  
-   <span data-ttu-id="c8441-106">将 .xml 策略文件导入到 BizTalk 组</span><span class="sxs-lookup"><span data-stu-id="c8441-106">Importing an .xml policy file into a BizTalk group</span></span>  
  
-   <span data-ttu-id="c8441-107">将绑定文件导入到 BizTalk 组或应用程序</span><span class="sxs-lookup"><span data-stu-id="c8441-107">Importing a binding file into a BizTalk group or application</span></span>  
  
## <a name="importing-a-biztalk-msi-file"></a><span data-ttu-id="c8441-108">导入 BizTalk .msi 文件</span><span class="sxs-lookup"><span data-stu-id="c8441-108">Importing a BizTalk .msi file</span></span>  
 <span data-ttu-id="c8441-109">将 BizTalk .msi 文件导入到 BizTalk 组或应用程序时，BizTalk Server 按如下所示处理它包含的项目：</span><span class="sxs-lookup"><span data-stu-id="c8441-109">When you import a BizTalk .msi file into a BizTalk group or application, BizTalk Server handles the artifacts that it contains as follows:</span></span>  
  
-   <span data-ttu-id="c8441-110">如果在导入期间您将任何引用从此应用程序添加到组中的其他应用程序，则该引用被添加到 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="c8441-110">If during import you added any references from this application to other applications in the group, the reference is added to the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="c8441-111">如果指定此选项，则应用程序中的现有项目被 .msi 文件中具有相同全名和版本号（如果适用）的项目覆盖。</span><span class="sxs-lookup"><span data-stu-id="c8441-111">If you specified this option, existing artifacts in the application are overwritten by artifacts in the .msi file that have the same full name and version number (if applicable).</span></span>  
  
-   <span data-ttu-id="c8441-112">如果绑定文件已添加到应用程序，并且您在导入期间选择其目标环境，则应用绑定。</span><span class="sxs-lookup"><span data-stu-id="c8441-112">If binding files have been added to the application, and you select their target environment during import, the bindings are applied.</span></span>  
  
-   <span data-ttu-id="c8441-113">配置为在导入时运行的预处理或后处理脚本将运行。</span><span class="sxs-lookup"><span data-stu-id="c8441-113">Pre- or post-processing scripts that are configured to run on import will run.</span></span>  
  
-   <span data-ttu-id="c8441-114">基于文件的项目数据被序列化，存储在 BizTalk 管理数据库中。</span><span class="sxs-lookup"><span data-stu-id="c8441-114">File-based artifact data is serialized and stored in the BizTalk Management database.</span></span> <span data-ttu-id="c8441-115">其中包括程序集、虚拟目录、文件、脚本、证书和 BAM 项目。</span><span class="sxs-lookup"><span data-stu-id="c8441-115">This includes data for assemblies, virtual directories, files, scripts, certificates, and BAM artifacts.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c8441-116">出于安全考虑，私钥在导出时从每个证书中删除。</span><span class="sxs-lookup"><span data-stu-id="c8441-116">For security reasons, the private key is removed from each certificate when it is exported.</span></span> <span data-ttu-id="c8441-117">因此，在 BizTalk 管理数据库中不存储私钥。</span><span class="sxs-lookup"><span data-stu-id="c8441-117">Therefore, no private keys are stored in the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="c8441-118">策略数据存储在规则引擎数据库中。</span><span class="sxs-lookup"><span data-stu-id="c8441-118">Policy data is stored in the Rule Engine database.</span></span>  
  
-   <span data-ttu-id="c8441-119">BAM 项目存储在 BAM 主导入数据库中。</span><span class="sxs-lookup"><span data-stu-id="c8441-119">BAM artifacts are stored in the BAM Primary Import database.</span></span> <span data-ttu-id="c8441-120">BAM 定义部署。</span><span class="sxs-lookup"><span data-stu-id="c8441-120">BAM definitions are deployed.</span></span>  
  
-   <span data-ttu-id="c8441-121">配置了“导入时添加到 GAC”部署选项的 BizTalk 程序集和 .NET 程序集添加到全局程序集引擎 (GAC)。</span><span class="sxs-lookup"><span data-stu-id="c8441-121">BizTalk assemblies and .NET assemblies that have the "Add to GAC on import" deployment option configured are added to the global assembly cache (GAC).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8441-122">项目数据存储在 BizTalk Server 数据库中，因此，当您稍后将应用程序导出到 .msi 文件中时，BizTalk Server 可以从数据库中检索所有配置信息以及与应用程序及其项目关联的数据，并将这些信息和数据包括在 .msi 文件中。</span><span class="sxs-lookup"><span data-stu-id="c8441-122">Because the artifact data is stored in the BizTalk Server databases, when you later export the application into an .msi file, BizTalk Server can retrieve from the databases all of the configuration information and data associated with the application and its artifacts and include it in the .msi file.</span></span> <span data-ttu-id="c8441-123">当您将 .msi 文件导入另一个 BizTalk 组时，所有项目配置信息和数据在新组中重新创建。</span><span class="sxs-lookup"><span data-stu-id="c8441-123">When you import the .msi file into another BizTalk group, all of the artifact configuration information and data is recreated in the new group.</span></span>  
  
 <span data-ttu-id="c8441-124">导入应用程序后，您可以使用管理控制台或 BTSTask 在应用程序中将多个项目作为单个实体一起进行查看、管理和部署，也可以对项目分别进行查看、管理和部署。</span><span class="sxs-lookup"><span data-stu-id="c8441-124">After you import an application, you can view, manage, and deploy the artifacts in the application either together as a single entity or individually by using the Administration console or BTSTask.</span></span> <span data-ttu-id="c8441-125">有关详细信息，请参阅[应用程序部署和管理工具](../core/application-deployment-and-management-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c8441-125">For more information, see [Application Deployment and Management Tools](../core/application-deployment-and-management-tools.md).</span></span>  
  
## <a name="importing-a-policy"></a><span data-ttu-id="c8441-126">导入策略</span><span class="sxs-lookup"><span data-stu-id="c8441-126">Importing a policy</span></span>  
 <span data-ttu-id="c8441-127">从 .xml 文件导入策略时，该策略被添加到规则引擎数据库。</span><span class="sxs-lookup"><span data-stu-id="c8441-127">When you import a policy from an .xml file, the policy is added to the Rule Engine database.</span></span> <span data-ttu-id="c8441-128">与您导入 BizTalk .msi 文件内的策略不同的是，该策略不与 BizTalk 管理数据库中的任何应用程序相关联。</span><span class="sxs-lookup"><span data-stu-id="c8441-128">Unlike when you import a policy within a BizTalk .msi file, the policy is not associated with any application in the BizTalk Management database.</span></span> <span data-ttu-id="c8441-129">策略中的策略节点显示\<所有项目 > 在 BizTalk Server 管理控制台中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="c8441-129">The policy displays in the Policies node of the \<All Artifacts> folder in the BizTalk Server Administration console.</span></span> <span data-ttu-id="c8441-130">导入策略后，您可以发布它，使其对组中的应用程序可用。</span><span class="sxs-lookup"><span data-stu-id="c8441-130">After importing the policy you can publish it to make it available for applications in the group to use.</span></span> <span data-ttu-id="c8441-131">有关详细信息，请参阅[管理策略](../core/managing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c8441-131">For more information, see [Managing Policies](../core/managing-policies.md).</span></span>  
  
## <a name="importing-a-binding-file"></a><span data-ttu-id="c8441-132">导入绑定文件</span><span class="sxs-lookup"><span data-stu-id="c8441-132">Importing a binding file</span></span>  
 <span data-ttu-id="c8441-133">将绑定文件导入 BizTalk 组时，在该组中当前存在的与所导入文件中的绑定同名的任何绑定被所导入文件中的绑定覆盖，并应用其配置。</span><span class="sxs-lookup"><span data-stu-id="c8441-133">When you import a binding file into a BizTalk group, any bindings that currently exist in the group having the same name as bindings in the imported file are overwritten by the bindings in the imported file, and the configuration is applied.</span></span>  
  
 <span data-ttu-id="c8441-134">将绑定文件分别或作为应用程序的一部分导入 BizTalk 应用程序时，在应用程序中当前存在的与文件中的绑定同名的任何绑定被导入的绑定覆盖，并应用其配置。</span><span class="sxs-lookup"><span data-stu-id="c8441-134">When you import a binding file into a BizTalk application either individually or as part of an application, any bindings that currently exist in the application having the same name as bindings in the file are overwritten by the imported bindings, and the configuration is applied.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c8441-135">出于安全方面的原因，如果导出绑定文件，BizTalk Server 会从该文件中删除绑定的密码。</span><span class="sxs-lookup"><span data-stu-id="c8441-135">For security reasons, when you export a binding file, BizTalk Server removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="c8441-136">在导入绑定后，必须为发送端口和接收位置重新配置密码，它们才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="c8441-136">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="c8441-137">您需要在 BizTalk Server 管理控制台的“传输属性”对话框中为发送端口或接收位置配置密码。</span><span class="sxs-lookup"><span data-stu-id="c8441-137">You configure passwords in the Transport Properties dialog box of the BizTalk Server Administration console for the send port or receive location.</span></span> <span data-ttu-id="c8441-138">有关说明，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。</span><span class="sxs-lookup"><span data-stu-id="c8441-138">For instructions, see [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span> <span data-ttu-id="c8441-139">另请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="c8441-139">See also [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8441-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8441-140">See Also</span></span>  
 <span data-ttu-id="c8441-141">[会发生什么情况项目在应用程序部署过程](../core/what-happens-to-artifacts-during-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="c8441-141">[What Happens to Artifacts During Application Deployment](../core/what-happens-to-artifacts-during-application-deployment.md) </span></span>  
 <span data-ttu-id="c8441-142">[导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md) </span><span class="sxs-lookup"><span data-stu-id="c8441-142">[Importing BizTalk Applications, Bindings, and Policies](../core/importing-biztalk-applications-bindings-and-policies.md) </span></span>  
 [<span data-ttu-id="c8441-143">依赖关系和应用程序部署</span><span class="sxs-lookup"><span data-stu-id="c8441-143">Dependencies and Application Deployment</span></span>](../core/dependencies-and-application-deployment.md)