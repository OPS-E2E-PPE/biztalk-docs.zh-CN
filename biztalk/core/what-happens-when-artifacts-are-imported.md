---
title: 导入项目时，会发生什么情况 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing, artifacts
- artifacts, importing
ms.assetid: a83957df-6e16-419a-b693-87985b498cc4
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52098eaa69fd2cefc25e6c7ba27908ec6a5a9bd9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395176"
---
# <a name="what-happens-when-artifacts-are-imported"></a><span data-ttu-id="ebe66-102">导入项目时，会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="ebe66-102">What Happens When Artifacts Are Imported</span></span>
<span data-ttu-id="ebe66-103">本主题介绍导入时，项目会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="ebe66-103">This topic describes what happens to artifacts when they are imported.</span></span> <span data-ttu-id="ebe66-104">有三种方式导入项目，本主题中介绍：</span><span class="sxs-lookup"><span data-stu-id="ebe66-104">There are three ways to import artifacts, which are covered in this topic:</span></span>  
  
-   <span data-ttu-id="ebe66-105">将 BizTalk.msi 文件中的项目导入到 BizTalk 组或应用程序</span><span class="sxs-lookup"><span data-stu-id="ebe66-105">Importing artifacts in a BizTalk .msi file into a BizTalk group or application</span></span>  
  
-   <span data-ttu-id="ebe66-106">将.xml 策略文件导入到 BizTalk 组</span><span class="sxs-lookup"><span data-stu-id="ebe66-106">Importing an .xml policy file into a BizTalk group</span></span>  
  
-   <span data-ttu-id="ebe66-107">绑定文件导入到 BizTalk 组或应用程序</span><span class="sxs-lookup"><span data-stu-id="ebe66-107">Importing a binding file into a BizTalk group or application</span></span>  
  
## <a name="importing-a-biztalk-msi-file"></a><span data-ttu-id="ebe66-108">导入 BizTalk.msi 文件</span><span class="sxs-lookup"><span data-stu-id="ebe66-108">Importing a BizTalk .msi file</span></span>  
 <span data-ttu-id="ebe66-109">您将 BizTalk.msi 文件导入到 BizTalk 组或应用程序时，BizTalk Server 处理的项目，它包含按如下所示：</span><span class="sxs-lookup"><span data-stu-id="ebe66-109">When you import a BizTalk .msi file into a BizTalk group or application, BizTalk Server handles the artifacts that it contains as follows:</span></span>  
  
-   <span data-ttu-id="ebe66-110">如果导入过程中添加的任何引用从此组中其他应用程序到应用程序，该引用添加到 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="ebe66-110">If during import you added any references from this application to other applications in the group, the reference is added to the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="ebe66-111">如果指定此选项，应用程序中的现有项目将被覆盖的.msi 文件中的项目具有相同全名和版本号 （如果适用）。</span><span class="sxs-lookup"><span data-stu-id="ebe66-111">If you specified this option, existing artifacts in the application are overwritten by artifacts in the .msi file that have the same full name and version number (if applicable).</span></span>  
  
-   <span data-ttu-id="ebe66-112">如果绑定文件已添加到应用程序，并导入过程中选择其目标环境，则应用绑定。</span><span class="sxs-lookup"><span data-stu-id="ebe66-112">If binding files have been added to the application, and you select their target environment during import, the bindings are applied.</span></span>  
  
-   <span data-ttu-id="ebe66-113">配置为在导入时运行的预处理或后处理脚本将运行。</span><span class="sxs-lookup"><span data-stu-id="ebe66-113">Pre- or post-processing scripts that are configured to run on import will run.</span></span>  
  
-   <span data-ttu-id="ebe66-114">序列化和 BizTalk 管理数据库中存储基于文件的项目数据。</span><span class="sxs-lookup"><span data-stu-id="ebe66-114">File-based artifact data is serialized and stored in the BizTalk Management database.</span></span> <span data-ttu-id="ebe66-115">其中包括针对程序集、 虚拟目录、 文件、 脚本、 证书和 BAM 项目的数据。</span><span class="sxs-lookup"><span data-stu-id="ebe66-115">This includes data for assemblies, virtual directories, files, scripts, certificates, and BAM artifacts.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ebe66-116">出于安全考虑，私钥导出时将删除从每个证书中。</span><span class="sxs-lookup"><span data-stu-id="ebe66-116">For security reasons, the private key is removed from each certificate when it is exported.</span></span> <span data-ttu-id="ebe66-117">因此，没有专用密钥存储在 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="ebe66-117">Therefore, no private keys are stored in the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="ebe66-118">策略数据存储在规则引擎数据库。</span><span class="sxs-lookup"><span data-stu-id="ebe66-118">Policy data is stored in the Rule Engine database.</span></span>  
  
-   <span data-ttu-id="ebe66-119">BAM 项目存储在 BAM 主导入数据库中。</span><span class="sxs-lookup"><span data-stu-id="ebe66-119">BAM artifacts are stored in the BAM Primary Import database.</span></span> <span data-ttu-id="ebe66-120">部署 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="ebe66-120">BAM definitions are deployed.</span></span>  
  
-   <span data-ttu-id="ebe66-121">BizTalk 程序集和已配置的"添加到 GAC 上导入"部署选项的.NET 程序集添加到全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="ebe66-121">BizTalk assemblies and .NET assemblies that have the "Add to GAC on import" deployment option configured are added to the global assembly cache (GAC).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ebe66-122">由于项目数据存储在 BizTalk Server 数据库中，在更高版本导出到.msi 文件的应用程序时，BizTalk Server 可以检索的所有配置信息和数据与应用程序关联的数据库并将其项目并将其包含在.msi 文件中。</span><span class="sxs-lookup"><span data-stu-id="ebe66-122">Because the artifact data is stored in the BizTalk Server databases, when you later export the application into an .msi file, BizTalk Server can retrieve from the databases all of the configuration information and data associated with the application and its artifacts and include it in the .msi file.</span></span> <span data-ttu-id="ebe66-123">.Msi 文件导入到另一个 BizTalk 组中，会将所有项目配置信息和数据重新创建新组中。</span><span class="sxs-lookup"><span data-stu-id="ebe66-123">When you import the .msi file into another BizTalk group, all of the artifact configuration information and data is recreated in the new group.</span></span>  
  
 <span data-ttu-id="ebe66-124">导入应用程序后，可以查看、 管理和部署在一起作为单个实体或通过使用管理控制台或 BTSTask 单独的应用程序中的项目。</span><span class="sxs-lookup"><span data-stu-id="ebe66-124">After you import an application, you can view, manage, and deploy the artifacts in the application either together as a single entity or individually by using the Administration console or BTSTask.</span></span> <span data-ttu-id="ebe66-125">有关详细信息，请参阅[应用程序部署和管理工具](../core/application-deployment-and-management-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="ebe66-125">For more information, see [Application Deployment and Management Tools](../core/application-deployment-and-management-tools.md).</span></span>  
  
## <a name="importing-a-policy"></a><span data-ttu-id="ebe66-126">导入策略</span><span class="sxs-lookup"><span data-stu-id="ebe66-126">Importing a policy</span></span>  
 <span data-ttu-id="ebe66-127">在从.xml 文件中导入策略，该策略添加到规则引擎数据库。</span><span class="sxs-lookup"><span data-stu-id="ebe66-127">When you import a policy from an .xml file, the policy is added to the Rule Engine database.</span></span> <span data-ttu-id="ebe66-128">与导入 BizTalk.msi 文件内的策略时，该策略不是与 BizTalk 管理数据库中的任何应用程序相关联。</span><span class="sxs-lookup"><span data-stu-id="ebe66-128">Unlike when you import a policy within a BizTalk .msi file, the policy is not associated with any application in the BizTalk Management database.</span></span> <span data-ttu-id="ebe66-129">该策略的策略节点中显示\<的所有项目\>BizTalk Server 管理控制台中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="ebe66-129">The policy displays in the Policies node of the \<All Artifacts\> folder in the BizTalk Server Administration console.</span></span> <span data-ttu-id="ebe66-130">导入策略后可以发布它，使其适用于应用程序中使用的组。</span><span class="sxs-lookup"><span data-stu-id="ebe66-130">After importing the policy you can publish it to make it available for applications in the group to use.</span></span> <span data-ttu-id="ebe66-131">有关详细信息，请参阅[管理策略](../core/managing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ebe66-131">For more information, see [Managing Policies](../core/managing-policies.md).</span></span>  
  
## <a name="importing-a-binding-file"></a><span data-ttu-id="ebe66-132">导入绑定文件</span><span class="sxs-lookup"><span data-stu-id="ebe66-132">Importing a binding file</span></span>  
 <span data-ttu-id="ebe66-133">绑定文件导入到 BizTalk 组中导入的文件具有相同的名称绑定的组中当前存在任何绑定的导入的文件中的绑定将覆盖并应用配置。</span><span class="sxs-lookup"><span data-stu-id="ebe66-133">When you import a binding file into a BizTalk group, any bindings that currently exist in the group having the same name as bindings in the imported file are overwritten by the bindings in the imported file, and the configuration is applied.</span></span>  
  
 <span data-ttu-id="ebe66-134">您将绑定文件导入 BizTalk 应用程序可以单独或作为应用程序的一部分，任何绑定当前中存在具有相同的名称，如文件中的绑定覆盖导入的绑定，该应用程序时，应用配置。</span><span class="sxs-lookup"><span data-stu-id="ebe66-134">When you import a binding file into a BizTalk application either individually or as part of an application, any bindings that currently exist in the application having the same name as bindings in the file are overwritten by the imported bindings, and the configuration is applied.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ebe66-135">出于安全原因，在导出绑定文件时 BizTalk Server 将从文件删除绑定密码。</span><span class="sxs-lookup"><span data-stu-id="ebe66-135">For security reasons, when you export a binding file, BizTalk Server removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="ebe66-136">导入绑定之后, 必须重新配置为发送端口的密码，并接收位置，它们才能正常。</span><span class="sxs-lookup"><span data-stu-id="ebe66-136">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="ebe66-137">发送端口在 BizTalk Server 管理控制台的传输属性对话框中配置密码，或接收位置。</span><span class="sxs-lookup"><span data-stu-id="ebe66-137">You configure passwords in the Transport Properties dialog box of the BizTalk Server Administration console for the send port or receive location.</span></span> <span data-ttu-id="ebe66-138">有关说明，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。</span><span class="sxs-lookup"><span data-stu-id="ebe66-138">For instructions, see [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span> <span data-ttu-id="ebe66-139">另请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="ebe66-139">See also [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebe66-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="ebe66-140">See Also</span></span>  
 <span data-ttu-id="ebe66-141">[对项目采取的应用程序部署过程](../core/what-happens-to-artifacts-during-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="ebe66-141">[What Happens to Artifacts During Application Deployment](../core/what-happens-to-artifacts-during-application-deployment.md) </span></span>  
 <span data-ttu-id="ebe66-142">[导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md) </span><span class="sxs-lookup"><span data-stu-id="ebe66-142">[Importing BizTalk Applications, Bindings, and Policies](../core/importing-biztalk-applications-bindings-and-policies.md) </span></span>  
 [<span data-ttu-id="ebe66-143">依赖关系和应用程序部署</span><span class="sxs-lookup"><span data-stu-id="ebe66-143">Dependencies and Application Deployment</span></span>](../core/dependencies-and-application-deployment.md)