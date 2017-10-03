---
title: "用于部署和管理 BizTalk 应用程序所需权限 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying [applications], security
- permissions, EDI adapters
- deploying, security
- security, applications
- security, EDI adapters
- assemblies, permissions
- permissions, deploying
- EDI adapters, security
- permissions, assemblies
- security, assemblies
- permissions, applications
- deploying, permissions
- applications, importing
- applications, exporting
- permissions, exporting
- installing, permissions
- applications, security
- security, permissions
- applications, installing
- assemblies, security
- managing, security
ms.assetid: 4a459ff1-661d-403a-99e0-d54b82e008d0
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 608da93cd1960d26304f4dcebe239367de2404e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="permissions-required-for-deploying-and-managing-a-biztalk-application"></a><span data-ttu-id="448e2-102">用于部署和管理 BizTalk 应用程序所需权限</span><span class="sxs-lookup"><span data-stu-id="448e2-102">Permissions Required for Deploying and Managing a BizTalk Application</span></span>
<span data-ttu-id="448e2-103">应用程序部署包括部署 BizTalk 从 Visual Studio 的程序集，以及导入、 导出和安装 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="448e2-103">Application deployment includes deploying BizTalk assemblies from Visual Studio as well as importing, exporting, and installing BizTalk applications.</span></span> <span data-ttu-id="448e2-104">你需要执行这些任务的基本权限如下所示：</span><span class="sxs-lookup"><span data-stu-id="448e2-104">The basic permissions you need to perform these tasks are as follows:</span></span>  
  
-   <span data-ttu-id="448e2-105">作为 BizTalk Server Administrators 组的成员，你授予所需部署 BizTalk 从 Visual Studio 的程序集的权限。</span><span class="sxs-lookup"><span data-stu-id="448e2-105">As a member of the BizTalk Server Administrators group, you are granted the permissions required to deploy BizTalk assemblies from Visual Studio.</span></span>  
  
-   <span data-ttu-id="448e2-106">作为 BizTalk Server Administrators 组的成员，你授予所需 BizTalk 应用程序导入到 BizTalk 组的权限。</span><span class="sxs-lookup"><span data-stu-id="448e2-106">As a member of the BizTalk Server Administrators group, you are granted the permissions required to import BizTalk applications into a BizTalk group.</span></span> <span data-ttu-id="448e2-107">如果已指定选项以添加到上导入的全局程序集缓存 (GAC) 应用程序中包含的程序集，你还必须程序集文件夹具有写入权限。</span><span class="sxs-lookup"><span data-stu-id="448e2-107">If the option to add an assembly included in the application to the global assembly cache (GAC) on import has been specified, you must also have Write permissions on the assembly folder.</span></span> <span data-ttu-id="448e2-108">作为本地 Administrators 组的成员，您将拥有此权限。</span><span class="sxs-lookup"><span data-stu-id="448e2-108">As a member of the local Administrators group, you have this permission.</span></span>  
  
-   <span data-ttu-id="448e2-109">作为 BizTalk Server Administrators 或 BizTalk Server Operators 组的成员，您被授予所需的权限：</span><span class="sxs-lookup"><span data-stu-id="448e2-109">As a member of the BizTalk Server Administrators or BizTalk Server Operators group, you are granted the permissions required to:</span></span>  
  
    -   <span data-ttu-id="448e2-110">在导出 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="448e2-110">Export BizTalk applications</span></span>  
  
    -   <span data-ttu-id="448e2-111">启动和停止发送端口、 发送端口组和业务流程</span><span class="sxs-lookup"><span data-stu-id="448e2-111">Start and stop send ports, send port groups, and orchestrations</span></span>  
  
    -   <span data-ttu-id="448e2-112">启用和禁用接收位置</span><span class="sxs-lookup"><span data-stu-id="448e2-112">Enable and disable receive locations</span></span>  
  
    -   <span data-ttu-id="448e2-113">挂起、 继续和终止实例</span><span class="sxs-lookup"><span data-stu-id="448e2-113">Suspend, resume, and terminate instances</span></span>  
  
    -   <span data-ttu-id="448e2-114">启动和停止应用程序</span><span class="sxs-lookup"><span data-stu-id="448e2-114">Start and stop applications</span></span>  
  
-   <span data-ttu-id="448e2-115">作为本地 Administrators 组的成员都被授予权限的本地计算机上安装 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="448e2-115">As a member of the local Administrators group you are granted permissions to install BizTalk applications on the local computer.</span></span>  
  
 <span data-ttu-id="448e2-116">你可能想要提供的用户来执行这些任务的限制最严格权限。</span><span class="sxs-lookup"><span data-stu-id="448e2-116">You may want to provide the most restrictive permissions for users to perform these tasks.</span></span> <span data-ttu-id="448e2-117">此主题的其余部分，如下所示提供所需的权限，有关的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="448e2-117">The remainder of this topic provides more details on the required permissions, as follows.</span></span>  
  
-   [<span data-ttu-id="448e2-118">部署 BizTalk 从 Visual Studio 的程序集的权限</span><span class="sxs-lookup"><span data-stu-id="448e2-118">Permissions for deploying BizTalk assemblies from Visual Studio</span></span>](#BKMK_Permissions_for_deploying)  
  
-   [<span data-ttu-id="448e2-119">用于导入应用程序的权限</span><span class="sxs-lookup"><span data-stu-id="448e2-119">Permissions for importing an application</span></span>](#BKMK_Permissions_for_importing)  
  
-   [<span data-ttu-id="448e2-120">导出应用程序的权限</span><span class="sxs-lookup"><span data-stu-id="448e2-120">Permissions for exporting an application</span></span>](#BKMK_Permissions_for_exporting)  
  
-   [<span data-ttu-id="448e2-121">安装应用程序的权限</span><span class="sxs-lookup"><span data-stu-id="448e2-121">Permissions for installing an application</span></span>](#BKMK_Permissions_for_installing_an_application)  
  
##  <span data-ttu-id="448e2-122"><a name="BKMK_Permissions_for_deploying"></a>部署 BizTalk 从 Visual Studio 的程序集的权限</span><span class="sxs-lookup"><span data-stu-id="448e2-122"><a name="BKMK_Permissions_for_deploying"></a> Permissions for deploying BizTalk assemblies from Visual Studio</span></span>  
 <span data-ttu-id="448e2-123">若要部署从 Visual Studio 中的 BizTalk 程序集，必须在 BizTalk 管理数据库中，至少具有写入权限。</span><span class="sxs-lookup"><span data-stu-id="448e2-123">To deploy BizTalk assemblies from within Visual Studio, you must have Write permission on the BizTalk Management database, at a minimum.</span></span> <span data-ttu-id="448e2-124">您被授予此权限与 BizTalk Server Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="448e2-124">You are granted this permission as a member of the BizTalk Server Administrators group.</span></span>  
  
##  <span data-ttu-id="448e2-125"><a name="BKMK_Permissions_for_importing"></a>用于导入应用程序的权限</span><span class="sxs-lookup"><span data-stu-id="448e2-125"><a name="BKMK_Permissions_for_importing"></a> Permissions for importing an application</span></span>  
 <span data-ttu-id="448e2-126">要导入 BizTalk 应用程序，必须至少具有以下权限。</span><span class="sxs-lookup"><span data-stu-id="448e2-126">To import a BizTalk application, you must have the following permissions, at a minimum.</span></span> <span data-ttu-id="448e2-127">您已被授予所有所需的权限作为 BizTalk Server Administrators 组的成员，但如果你想要安装到 gac 中的任何程序集，还必须对程序集文件夹具有写入权限。</span><span class="sxs-lookup"><span data-stu-id="448e2-127">You are granted all of the required permissions as a member of the BizTalk Server Administrators group, except that if you want to install any assemblies to the GAC, you must also have Write permissions on the assembly folder.</span></span>  
  
|<span data-ttu-id="448e2-128">项</span><span class="sxs-lookup"><span data-stu-id="448e2-128">Item</span></span>|<span data-ttu-id="448e2-129">Permissions</span><span class="sxs-lookup"><span data-stu-id="448e2-129">Permissions</span></span>|<span data-ttu-id="448e2-130">在需要时</span><span class="sxs-lookup"><span data-stu-id="448e2-130">When Required</span></span>|  
|----------|-----------------|-------------------|  
|<span data-ttu-id="448e2-131">BizTalk 管理数据库</span><span class="sxs-lookup"><span data-stu-id="448e2-131">BizTalk Management database</span></span>|<span data-ttu-id="448e2-132">读/写</span><span class="sxs-lookup"><span data-stu-id="448e2-132">Read/Write</span></span>|<span data-ttu-id="448e2-133">始终要求。</span><span class="sxs-lookup"><span data-stu-id="448e2-133">Always required.</span></span>|  
|<span data-ttu-id="448e2-134">BizTalk 规则引擎数据库</span><span class="sxs-lookup"><span data-stu-id="448e2-134">BizTalk Rule Engine database</span></span>|<span data-ttu-id="448e2-135">读/写</span><span class="sxs-lookup"><span data-stu-id="448e2-135">Read/Write</span></span>|<span data-ttu-id="448e2-136">才被必需的应用程序如果包括规则资源。</span><span class="sxs-lookup"><span data-stu-id="448e2-136">Required only if the application includes rules resources.</span></span>|  
|<span data-ttu-id="448e2-137">BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="448e2-137">BAM database</span></span>|<span data-ttu-id="448e2-138">读/写</span><span class="sxs-lookup"><span data-stu-id="448e2-138">Read/Write</span></span>|<span data-ttu-id="448e2-139">如果该应用程序包括 BAM 资源仅必填项</span><span class="sxs-lookup"><span data-stu-id="448e2-139">Required only if the application includes BAM resources</span></span>|  
|<span data-ttu-id="448e2-140">全局程序集缓存 (GAC)</span><span class="sxs-lookup"><span data-stu-id="448e2-140">Global assembly cache (GAC)</span></span>|<span data-ttu-id="448e2-141">读/写</span><span class="sxs-lookup"><span data-stu-id="448e2-141">Read/Write</span></span>|<span data-ttu-id="448e2-142">如果应用程序包含程序集资源，并指定程序集将添加到导入 GAC 仅必填项。</span><span class="sxs-lookup"><span data-stu-id="448e2-142">Required only if the application includes assembly resources, and you specify that the assemblies are added to the GAC on import.</span></span> <span data-ttu-id="448e2-143">（参见备注。）</span><span class="sxs-lookup"><span data-stu-id="448e2-143">(See Note.)</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="448e2-144">当使用导入向导导入程序集，可以指定将程序集添加到全局程序集缓存 (GAC) 选项。</span><span class="sxs-lookup"><span data-stu-id="448e2-144">When importing an assembly by using the Import Wizard, you can specify the option to add the assembly to the global assembly cache (GAC).</span></span> <span data-ttu-id="448e2-145">在这种情况下，你必须在程序集文件夹具有写入权限。</span><span class="sxs-lookup"><span data-stu-id="448e2-145">In this case, you must have write permission on the assembly folder.</span></span> <span data-ttu-id="448e2-146">有关程序集文件夹的详细信息，请参阅[安装应用程序的权限](#BKMK_Permissions_for_installing_an_application)。</span><span class="sxs-lookup"><span data-stu-id="448e2-146">For more information about the assembly folder, see [Permissions for installing an application](#BKMK_Permissions_for_installing_an_application).</span></span>  
>   
>  <span data-ttu-id="448e2-147">如果你的应用程序包括部署除列出的任何项的脚本，你必须具有相应权限，无法部署的其他项。</span><span class="sxs-lookup"><span data-stu-id="448e2-147">If your application includes a script that deploys any items in addition to those listed, you must have appropriate permissions to deploy the additional items.</span></span>  
  
##  <span data-ttu-id="448e2-148"><a name="BKMK_Permissions_for_exporting"></a>导出应用程序的权限</span><span class="sxs-lookup"><span data-stu-id="448e2-148"><a name="BKMK_Permissions_for_exporting"></a> Permissions for exporting an application</span></span>  
 <span data-ttu-id="448e2-149">若要导出 BizTalk 应用程序，必须至少具有以下权限。</span><span class="sxs-lookup"><span data-stu-id="448e2-149">To export a BizTalk application, you must have the following permissions, at a minimum.</span></span> <span data-ttu-id="448e2-150">作为 BizTalk Operators 组的成员，您被授予所需的权限。</span><span class="sxs-lookup"><span data-stu-id="448e2-150">You are granted the required permissions as a member of the BizTalk Operators group.</span></span>  
  
|<span data-ttu-id="448e2-151">项</span><span class="sxs-lookup"><span data-stu-id="448e2-151">Item</span></span>|<span data-ttu-id="448e2-152">Permissions</span><span class="sxs-lookup"><span data-stu-id="448e2-152">Permissions</span></span>|<span data-ttu-id="448e2-153">在需要时</span><span class="sxs-lookup"><span data-stu-id="448e2-153">When Required</span></span>|  
|----------|-----------------|-------------------|  
|<span data-ttu-id="448e2-154">BizTalk 管理数据库</span><span class="sxs-lookup"><span data-stu-id="448e2-154">BizTalk Management database</span></span>|<span data-ttu-id="448e2-155">读取</span><span class="sxs-lookup"><span data-stu-id="448e2-155">Read</span></span>|<span data-ttu-id="448e2-156">始终要求。</span><span class="sxs-lookup"><span data-stu-id="448e2-156">Always required.</span></span>|  
|<span data-ttu-id="448e2-157">BizTalk 规则引擎数据库</span><span class="sxs-lookup"><span data-stu-id="448e2-157">BizTalk Rule Engine database</span></span>|<span data-ttu-id="448e2-158">读取</span><span class="sxs-lookup"><span data-stu-id="448e2-158">Read</span></span>|<span data-ttu-id="448e2-159">才被必需的应用程序如果包括规则资源。</span><span class="sxs-lookup"><span data-stu-id="448e2-159">Required only if the application includes rules resources.</span></span>|  
|<span data-ttu-id="448e2-160">证书存储</span><span class="sxs-lookup"><span data-stu-id="448e2-160">Certificate store</span></span>|<span data-ttu-id="448e2-161">读取</span><span class="sxs-lookup"><span data-stu-id="448e2-161">Read</span></span>|<span data-ttu-id="448e2-162">才被必需的应用程序如果包括证书资源。</span><span class="sxs-lookup"><span data-stu-id="448e2-162">Required only if the application includes certificate resources.</span></span>|  
|<span data-ttu-id="448e2-163">Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="448e2-163">Internet Information Services</span></span>|<span data-ttu-id="448e2-164">读取</span><span class="sxs-lookup"><span data-stu-id="448e2-164">Read</span></span>|<span data-ttu-id="448e2-165">才被必需的应用程序如果包括虚拟目录资源。</span><span class="sxs-lookup"><span data-stu-id="448e2-165">Required only if the application includes virtual directory resources.</span></span>|  
  
##  <span data-ttu-id="448e2-166"><a name="BKMK_Permissions_for_installing_an_application"></a>安装应用程序的权限</span><span class="sxs-lookup"><span data-stu-id="448e2-166"><a name="BKMK_Permissions_for_installing_an_application"></a> Permissions for installing an application</span></span>  
 <span data-ttu-id="448e2-167">默认情况下，本地管理员组的成员具有在本地计算机上安装 BizTalk 应用程序所需的权限。</span><span class="sxs-lookup"><span data-stu-id="448e2-167">By default, members of the local Administrators group have the permissions required to install BizTalk applications on the local computer.</span></span> <span data-ttu-id="448e2-168">如果你想要向需要安装应用程序的用户提供更受限制的权限下, 表提供了你必须配置的最低权限。</span><span class="sxs-lookup"><span data-stu-id="448e2-168">If you want to provide more restricted permissions to users who need to install applications, the following table provides the minimum permissions that you must configure.</span></span> <span data-ttu-id="448e2-169">除了这些权限，如果你的应用程序的资源需要额外权限，若要安装，例如创建新数据库或数据库表，你必须还具有这些权限。</span><span class="sxs-lookup"><span data-stu-id="448e2-169">In addition to these permissions, if your application has resources that require additional permissions to install, such as to create a new database or database table, you must also have these permissions.</span></span>  
  
|<span data-ttu-id="448e2-170">项</span><span class="sxs-lookup"><span data-stu-id="448e2-170">Item</span></span>|<span data-ttu-id="448e2-171">Permissions</span><span class="sxs-lookup"><span data-stu-id="448e2-171">Permissions</span></span>|<span data-ttu-id="448e2-172">在需要时</span><span class="sxs-lookup"><span data-stu-id="448e2-172">When Required</span></span>|  
|----------|-----------------|-------------------|  
|<span data-ttu-id="448e2-173">证书存储</span><span class="sxs-lookup"><span data-stu-id="448e2-173">Certificate store</span></span>|<span data-ttu-id="448e2-174">读/写</span><span class="sxs-lookup"><span data-stu-id="448e2-174">Read/Write</span></span>|<span data-ttu-id="448e2-175">才被必需的应用程序如果包括证书资源。</span><span class="sxs-lookup"><span data-stu-id="448e2-175">Required only if the application includes certificate resources.</span></span>|  
|<span data-ttu-id="448e2-176">Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="448e2-176">Internet Information Services</span></span>|<span data-ttu-id="448e2-177">读/写</span><span class="sxs-lookup"><span data-stu-id="448e2-177">Read/Write</span></span>|<span data-ttu-id="448e2-178">才被必需的应用程序如果包括虚拟目录资源。</span><span class="sxs-lookup"><span data-stu-id="448e2-178">Required only if the application includes virtual directory resources.</span></span>|  
|<span data-ttu-id="448e2-179">GAC</span><span class="sxs-lookup"><span data-stu-id="448e2-179">GAC</span></span>|<span data-ttu-id="448e2-180">读/写</span><span class="sxs-lookup"><span data-stu-id="448e2-180">Read/Write</span></span>|<span data-ttu-id="448e2-181">如果应用程序包含程序集资源，并指定程序集将添加到安装在 gac 中仅必填项。</span><span class="sxs-lookup"><span data-stu-id="448e2-181">Required only if the application includes assembly resources, and you specify that the assemblies are added to the GAC on install.</span></span> <span data-ttu-id="448e2-182">（请注意，下面。）</span><span class="sxs-lookup"><span data-stu-id="448e2-182">(See Note, below.)</span></span>|  
|<span data-ttu-id="448e2-183">文件系统</span><span class="sxs-lookup"><span data-stu-id="448e2-183">File system</span></span>|<span data-ttu-id="448e2-184">读/写</span><span class="sxs-lookup"><span data-stu-id="448e2-184">Read/Write</span></span>|<span data-ttu-id="448e2-185">如果已为资源设置目标属性，则需要仅。</span><span class="sxs-lookup"><span data-stu-id="448e2-185">Required only if a destination property has been set for a resource.</span></span>|  
|<span data-ttu-id="448e2-186">注册表</span><span class="sxs-lookup"><span data-stu-id="448e2-186">Registry</span></span>|<span data-ttu-id="448e2-187">读/写</span><span class="sxs-lookup"><span data-stu-id="448e2-187">Read/Write</span></span>|<span data-ttu-id="448e2-188">如果存在**regsvcs**或**regasm**属性设置为 True，针对一个程序集资源，其中包含托管 COM 或 COM + 组件。</span><span class="sxs-lookup"><span data-stu-id="448e2-188">Required if the **regsvcs** or **regasm**property is set to True for an assembly resource containing managed COM or COM+ components.</span></span>|  
|<span data-ttu-id="448e2-189">注册表</span><span class="sxs-lookup"><span data-stu-id="448e2-189">Registry</span></span>|<span data-ttu-id="448e2-190">读/写</span><span class="sxs-lookup"><span data-stu-id="448e2-190">Read/Write</span></span>|<span data-ttu-id="448e2-191">所需应用程序如果包括非托管的 COM 资源</span><span class="sxs-lookup"><span data-stu-id="448e2-191">Required if the application includes unmanaged COM resources</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="448e2-192">从 BizTalk Server 管理控制台中，你可以指定程序集将添加到安装上的 GAC （右键单击资源文件夹中的程序集，然后单击修改）。</span><span class="sxs-lookup"><span data-stu-id="448e2-192">From the BizTalk Server Administration console, you can specify that an assembly be added to the GAC on installation (right-click the assembly in the resources folder and then click Modify).</span></span> <span data-ttu-id="448e2-193">如果指定此选项，然后安装的 BizTalk 应用程序需要编写程序集文件夹，其中包含 gac 中的权限。</span><span class="sxs-lookup"><span data-stu-id="448e2-193">If this option is specified, then installing the BizTalk application requires Write permission on the assembly folder, which contains the GAC.</span></span> <span data-ttu-id="448e2-194">程序集文件夹的路径为 %systemroot%\assembly。</span><span class="sxs-lookup"><span data-stu-id="448e2-194">The path of the assembly folder is %SystemRoot%\assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="448e2-195">另请参阅</span><span class="sxs-lookup"><span data-stu-id="448e2-195">See Also</span></span>  
 [<span data-ttu-id="448e2-196">应用程序部署的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="448e2-196">Security Considerations for Application Deployment</span></span>](../core/security-considerations-for-application-deployment.md)