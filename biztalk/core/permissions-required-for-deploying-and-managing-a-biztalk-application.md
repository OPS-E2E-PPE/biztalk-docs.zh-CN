---
title: 用于部署和管理 BizTalk 应用程序所需的权限 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c4dcf35fb7975e878e6603712d5a56d2bd89a89
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019648"
---
# <a name="permissions-required-for-deploying-and-managing-a-biztalk-application"></a><span data-ttu-id="5d672-102">用于部署和管理 BizTalk 应用程序所需的权限</span><span class="sxs-lookup"><span data-stu-id="5d672-102">Permissions Required for Deploying and Managing a BizTalk Application</span></span>
<span data-ttu-id="5d672-103">应用程序部署包括部署 BizTalk 程序集从 Visual Studio，以及导入、 导出和安装 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5d672-103">Application deployment includes deploying BizTalk assemblies from Visual Studio as well as importing, exporting, and installing BizTalk applications.</span></span> <span data-ttu-id="5d672-104">若要执行这些任务所需的基本权限如下所示：</span><span class="sxs-lookup"><span data-stu-id="5d672-104">The basic permissions you need to perform these tasks are as follows:</span></span>  
  
- <span data-ttu-id="5d672-105">作为 BizTalk Server Administrators 组的成员，将授予部署 BizTalk 程序集从 Visual Studio 所需的权限。</span><span class="sxs-lookup"><span data-stu-id="5d672-105">As a member of the BizTalk Server Administrators group, you are granted the permissions required to deploy BizTalk assemblies from Visual Studio.</span></span>  
  
- <span data-ttu-id="5d672-106">作为 BizTalk Server Administrators 组的成员，授予所需将 BizTalk 应用程序导入 BizTalk 组的权限。</span><span class="sxs-lookup"><span data-stu-id="5d672-106">As a member of the BizTalk Server Administrators group, you are granted the permissions required to import BizTalk applications into a BizTalk group.</span></span> <span data-ttu-id="5d672-107">如果已指定该选项可以添加到全局程序集缓存 (GAC) 上导入应用程序中包括程序集，您还必须写入权限的程序集文件夹。</span><span class="sxs-lookup"><span data-stu-id="5d672-107">If the option to add an assembly included in the application to the global assembly cache (GAC) on import has been specified, you must also have Write permissions on the assembly folder.</span></span> <span data-ttu-id="5d672-108">作为本地 Administrators 组的成员，您将拥有此权限。</span><span class="sxs-lookup"><span data-stu-id="5d672-108">As a member of the local Administrators group, you have this permission.</span></span>  
  
- <span data-ttu-id="5d672-109">作为 BizTalk Server Administrators 或 BizTalk Server Operators 组的成员，被授予所需的权限：</span><span class="sxs-lookup"><span data-stu-id="5d672-109">As a member of the BizTalk Server Administrators or BizTalk Server Operators group, you are granted the permissions required to:</span></span>  
  
  -   <span data-ttu-id="5d672-110">导出 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="5d672-110">Export BizTalk applications</span></span>  
  
  -   <span data-ttu-id="5d672-111">启动和停止发送端口、 发送端口组和业务流程</span><span class="sxs-lookup"><span data-stu-id="5d672-111">Start and stop send ports, send port groups, and orchestrations</span></span>  
  
  -   <span data-ttu-id="5d672-112">启用和禁用接收位置</span><span class="sxs-lookup"><span data-stu-id="5d672-112">Enable and disable receive locations</span></span>  
  
  -   <span data-ttu-id="5d672-113">挂起、 继续和终止实例</span><span class="sxs-lookup"><span data-stu-id="5d672-113">Suspend, resume, and terminate instances</span></span>  
  
  -   <span data-ttu-id="5d672-114">启动和停止应用程序</span><span class="sxs-lookup"><span data-stu-id="5d672-114">Start and stop applications</span></span>  
  
- <span data-ttu-id="5d672-115">作为本地 Administrators 组的成员授予权限以在本地计算机上安装 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5d672-115">As a member of the local Administrators group you are granted permissions to install BizTalk applications on the local computer.</span></span>  
  
  <span data-ttu-id="5d672-116">您可能想要提供限制性最强的权限，用户才能执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="5d672-116">You may want to provide the most restrictive permissions for users to perform these tasks.</span></span> <span data-ttu-id="5d672-117">此主题的其余部分，如下所示提供所需权限的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="5d672-117">The remainder of this topic provides more details on the required permissions, as follows.</span></span>  
  
- [<span data-ttu-id="5d672-118">用于部署 BizTalk 程序集从 Visual Studio 的权限</span><span class="sxs-lookup"><span data-stu-id="5d672-118">Permissions for deploying BizTalk assemblies from Visual Studio</span></span>](#BKMK_Permissions_for_deploying)  
  
- [<span data-ttu-id="5d672-119">导入应用程序的权限</span><span class="sxs-lookup"><span data-stu-id="5d672-119">Permissions for importing an application</span></span>](#BKMK_Permissions_for_importing)  
  
- [<span data-ttu-id="5d672-120">导出应用程序的权限</span><span class="sxs-lookup"><span data-stu-id="5d672-120">Permissions for exporting an application</span></span>](#BKMK_Permissions_for_exporting)  
  
- [<span data-ttu-id="5d672-121">安装应用程序的权限</span><span class="sxs-lookup"><span data-stu-id="5d672-121">Permissions for installing an application</span></span>](#BKMK_Permissions_for_installing_an_application)  
  
##  <a name="BKMK_Permissions_for_deploying"></a> <span data-ttu-id="5d672-122">用于部署 BizTalk 程序集从 Visual Studio 的权限</span><span class="sxs-lookup"><span data-stu-id="5d672-122">Permissions for deploying BizTalk assemblies from Visual Studio</span></span>  
 <span data-ttu-id="5d672-123">若要部署 BizTalk 程序集从 Visual Studio 中的，必须在 BizTalk 管理数据库中，至少具有写入权限。</span><span class="sxs-lookup"><span data-stu-id="5d672-123">To deploy BizTalk assemblies from within Visual Studio, you must have Write permission on the BizTalk Management database, at a minimum.</span></span> <span data-ttu-id="5d672-124">授予此权限作为 BizTalk Server Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="5d672-124">You are granted this permission as a member of the BizTalk Server Administrators group.</span></span>  
  
##  <a name="BKMK_Permissions_for_importing"></a> <span data-ttu-id="5d672-125">导入应用程序的权限</span><span class="sxs-lookup"><span data-stu-id="5d672-125">Permissions for importing an application</span></span>  
 <span data-ttu-id="5d672-126">要导入 BizTalk 应用程序，必须至少具有以下权限。</span><span class="sxs-lookup"><span data-stu-id="5d672-126">To import a BizTalk application, you must have the following permissions, at a minimum.</span></span> <span data-ttu-id="5d672-127">您已被授予所有所需的权限作为 BizTalk Server Administrators 组的成员，但如果你想要安装到 GAC 中的任何程序集，还必须对程序集文件夹具有写权限。</span><span class="sxs-lookup"><span data-stu-id="5d672-127">You are granted all of the required permissions as a member of the BizTalk Server Administrators group, except that if you want to install any assemblies to the GAC, you must also have Write permissions on the assembly folder.</span></span>  
  
|<span data-ttu-id="5d672-128">项</span><span class="sxs-lookup"><span data-stu-id="5d672-128">Item</span></span>|<span data-ttu-id="5d672-129">权限</span><span class="sxs-lookup"><span data-stu-id="5d672-129">Permissions</span></span>|<span data-ttu-id="5d672-130">在需要时</span><span class="sxs-lookup"><span data-stu-id="5d672-130">When Required</span></span>|  
|----------|-----------------|-------------------|  
|<span data-ttu-id="5d672-131">BizTalk 管理数据库</span><span class="sxs-lookup"><span data-stu-id="5d672-131">BizTalk Management database</span></span>|<span data-ttu-id="5d672-132">读/写</span><span class="sxs-lookup"><span data-stu-id="5d672-132">Read/Write</span></span>|<span data-ttu-id="5d672-133">始终要求。</span><span class="sxs-lookup"><span data-stu-id="5d672-133">Always required.</span></span>|  
|<span data-ttu-id="5d672-134">BizTalk 规则引擎数据库</span><span class="sxs-lookup"><span data-stu-id="5d672-134">BizTalk Rule Engine database</span></span>|<span data-ttu-id="5d672-135">读/写</span><span class="sxs-lookup"><span data-stu-id="5d672-135">Read/Write</span></span>|<span data-ttu-id="5d672-136">才被必需的应用程序如果包括规则资源。</span><span class="sxs-lookup"><span data-stu-id="5d672-136">Required only if the application includes rules resources.</span></span>|  
|<span data-ttu-id="5d672-137">BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="5d672-137">BAM database</span></span>|<span data-ttu-id="5d672-138">读/写</span><span class="sxs-lookup"><span data-stu-id="5d672-138">Read/Write</span></span>|<span data-ttu-id="5d672-139">才被必需的应用程序如果包括 BAM 资源</span><span class="sxs-lookup"><span data-stu-id="5d672-139">Required only if the application includes BAM resources</span></span>|  
|<span data-ttu-id="5d672-140">全局程序集缓存 (GAC)</span><span class="sxs-lookup"><span data-stu-id="5d672-140">Global assembly cache (GAC)</span></span>|<span data-ttu-id="5d672-141">读/写</span><span class="sxs-lookup"><span data-stu-id="5d672-141">Read/Write</span></span>|<span data-ttu-id="5d672-142">如果应用程序包括程序集资源，并且你指定的程序集都添加到 GAC 上导入必需的仅。</span><span class="sxs-lookup"><span data-stu-id="5d672-142">Required only if the application includes assembly resources, and you specify that the assemblies are added to the GAC on import.</span></span> <span data-ttu-id="5d672-143">（参见备注。）</span><span class="sxs-lookup"><span data-stu-id="5d672-143">(See Note.)</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="5d672-144">在使用导入向导导入程序集，可以指定将程序集添加到全局程序集缓存 (GAC) 的选项。</span><span class="sxs-lookup"><span data-stu-id="5d672-144">When importing an assembly by using the Import Wizard, you can specify the option to add the assembly to the global assembly cache (GAC).</span></span> <span data-ttu-id="5d672-145">在这种情况下，您必须对程序集文件夹具有写入权限。</span><span class="sxs-lookup"><span data-stu-id="5d672-145">In this case, you must have write permission on the assembly folder.</span></span> <span data-ttu-id="5d672-146">有关程序集文件夹的详细信息，请参阅[安装应用程序的权限](#BKMK_Permissions_for_installing_an_application)。</span><span class="sxs-lookup"><span data-stu-id="5d672-146">For more information about the assembly folder, see [Permissions for installing an application](#BKMK_Permissions_for_installing_an_application).</span></span>  
>   
>  <span data-ttu-id="5d672-147">如果你的应用程序包括用于部署所列内容之外的任何项的脚本，必须具有适当的权限来部署的其他项。</span><span class="sxs-lookup"><span data-stu-id="5d672-147">If your application includes a script that deploys any items in addition to those listed, you must have appropriate permissions to deploy the additional items.</span></span>  
  
##  <a name="BKMK_Permissions_for_exporting"></a> <span data-ttu-id="5d672-148">导出应用程序的权限</span><span class="sxs-lookup"><span data-stu-id="5d672-148">Permissions for exporting an application</span></span>  
 <span data-ttu-id="5d672-149">若要导出 BizTalk 应用程序，必须至少具有以下权限。</span><span class="sxs-lookup"><span data-stu-id="5d672-149">To export a BizTalk application, you must have the following permissions, at a minimum.</span></span> <span data-ttu-id="5d672-150">为 BizTalk Operators 组的成员具有所需的权限。</span><span class="sxs-lookup"><span data-stu-id="5d672-150">You are granted the required permissions as a member of the BizTalk Operators group.</span></span>  
  
|<span data-ttu-id="5d672-151">项</span><span class="sxs-lookup"><span data-stu-id="5d672-151">Item</span></span>|<span data-ttu-id="5d672-152">权限</span><span class="sxs-lookup"><span data-stu-id="5d672-152">Permissions</span></span>|<span data-ttu-id="5d672-153">在需要时</span><span class="sxs-lookup"><span data-stu-id="5d672-153">When Required</span></span>|  
|----------|-----------------|-------------------|  
|<span data-ttu-id="5d672-154">BizTalk 管理数据库</span><span class="sxs-lookup"><span data-stu-id="5d672-154">BizTalk Management database</span></span>|<span data-ttu-id="5d672-155">读取</span><span class="sxs-lookup"><span data-stu-id="5d672-155">Read</span></span>|<span data-ttu-id="5d672-156">始终要求。</span><span class="sxs-lookup"><span data-stu-id="5d672-156">Always required.</span></span>|  
|<span data-ttu-id="5d672-157">BizTalk 规则引擎数据库</span><span class="sxs-lookup"><span data-stu-id="5d672-157">BizTalk Rule Engine database</span></span>|<span data-ttu-id="5d672-158">读取</span><span class="sxs-lookup"><span data-stu-id="5d672-158">Read</span></span>|<span data-ttu-id="5d672-159">才被必需的应用程序如果包括规则资源。</span><span class="sxs-lookup"><span data-stu-id="5d672-159">Required only if the application includes rules resources.</span></span>|  
|<span data-ttu-id="5d672-160">证书存储区</span><span class="sxs-lookup"><span data-stu-id="5d672-160">Certificate store</span></span>|<span data-ttu-id="5d672-161">读取</span><span class="sxs-lookup"><span data-stu-id="5d672-161">Read</span></span>|<span data-ttu-id="5d672-162">才被必需的应用程序如果包括证书资源。</span><span class="sxs-lookup"><span data-stu-id="5d672-162">Required only if the application includes certificate resources.</span></span>|  
|<span data-ttu-id="5d672-163">Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="5d672-163">Internet Information Services</span></span>|<span data-ttu-id="5d672-164">读取</span><span class="sxs-lookup"><span data-stu-id="5d672-164">Read</span></span>|<span data-ttu-id="5d672-165">才被必需的应用程序如果包括虚拟目录资源。</span><span class="sxs-lookup"><span data-stu-id="5d672-165">Required only if the application includes virtual directory resources.</span></span>|  
  
##  <a name="BKMK_Permissions_for_installing_an_application"></a> <span data-ttu-id="5d672-166">安装应用程序的权限</span><span class="sxs-lookup"><span data-stu-id="5d672-166">Permissions for installing an application</span></span>  
 <span data-ttu-id="5d672-167">默认情况下，本地管理员组的成员具有在本地计算机上安装 BizTalk 应用程序所需的权限。</span><span class="sxs-lookup"><span data-stu-id="5d672-167">By default, members of the local Administrators group have the permissions required to install BizTalk applications on the local computer.</span></span> <span data-ttu-id="5d672-168">如果你想要向需要安装应用程序的用户提供更受限制的权限下, 表提供了您必须配置的最低权限。</span><span class="sxs-lookup"><span data-stu-id="5d672-168">If you want to provide more restricted permissions to users who need to install applications, the following table provides the minimum permissions that you must configure.</span></span> <span data-ttu-id="5d672-169">除了这些权限，如果你的应用程序包含具有其他权限才能安装，例如，创建一个新的数据库或数据库表的资源您必须还具有这些权限。</span><span class="sxs-lookup"><span data-stu-id="5d672-169">In addition to these permissions, if your application has resources that require additional permissions to install, such as to create a new database or database table, you must also have these permissions.</span></span>  
  
|<span data-ttu-id="5d672-170">项</span><span class="sxs-lookup"><span data-stu-id="5d672-170">Item</span></span>|<span data-ttu-id="5d672-171">权限</span><span class="sxs-lookup"><span data-stu-id="5d672-171">Permissions</span></span>|<span data-ttu-id="5d672-172">在需要时</span><span class="sxs-lookup"><span data-stu-id="5d672-172">When Required</span></span>|  
|----------|-----------------|-------------------|  
|<span data-ttu-id="5d672-173">证书存储区</span><span class="sxs-lookup"><span data-stu-id="5d672-173">Certificate store</span></span>|<span data-ttu-id="5d672-174">读/写</span><span class="sxs-lookup"><span data-stu-id="5d672-174">Read/Write</span></span>|<span data-ttu-id="5d672-175">才被必需的应用程序如果包括证书资源。</span><span class="sxs-lookup"><span data-stu-id="5d672-175">Required only if the application includes certificate resources.</span></span>|  
|<span data-ttu-id="5d672-176">Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="5d672-176">Internet Information Services</span></span>|<span data-ttu-id="5d672-177">读/写</span><span class="sxs-lookup"><span data-stu-id="5d672-177">Read/Write</span></span>|<span data-ttu-id="5d672-178">才被必需的应用程序如果包括虚拟目录资源。</span><span class="sxs-lookup"><span data-stu-id="5d672-178">Required only if the application includes virtual directory resources.</span></span>|  
|<span data-ttu-id="5d672-179">GAC</span><span class="sxs-lookup"><span data-stu-id="5d672-179">GAC</span></span>|<span data-ttu-id="5d672-180">读/写</span><span class="sxs-lookup"><span data-stu-id="5d672-180">Read/Write</span></span>|<span data-ttu-id="5d672-181">如果应用程序包括程序集资源，并且你指定的程序集都添加到 GAC 上安装必需的仅。</span><span class="sxs-lookup"><span data-stu-id="5d672-181">Required only if the application includes assembly resources, and you specify that the assemblies are added to the GAC on install.</span></span> <span data-ttu-id="5d672-182">（请注意，参阅下面。）</span><span class="sxs-lookup"><span data-stu-id="5d672-182">(See Note, below.)</span></span>|  
|<span data-ttu-id="5d672-183">文件系统</span><span class="sxs-lookup"><span data-stu-id="5d672-183">File system</span></span>|<span data-ttu-id="5d672-184">读/写</span><span class="sxs-lookup"><span data-stu-id="5d672-184">Read/Write</span></span>|<span data-ttu-id="5d672-185">才被必需的目标属性是否已设置的资源。</span><span class="sxs-lookup"><span data-stu-id="5d672-185">Required only if a destination property has been set for a resource.</span></span>|  
|<span data-ttu-id="5d672-186">注册表</span><span class="sxs-lookup"><span data-stu-id="5d672-186">Registry</span></span>|<span data-ttu-id="5d672-187">读/写</span><span class="sxs-lookup"><span data-stu-id="5d672-187">Read/Write</span></span>|<span data-ttu-id="5d672-188">需要**regsvcs**或**regasm**属性设置为 True，为一个程序集资源，其中包含托管 COM 或 COM + 组件。</span><span class="sxs-lookup"><span data-stu-id="5d672-188">Required if the **regsvcs** or **regasm**property is set to True for an assembly resource containing managed COM or COM+ components.</span></span>|  
|<span data-ttu-id="5d672-189">注册表</span><span class="sxs-lookup"><span data-stu-id="5d672-189">Registry</span></span>|<span data-ttu-id="5d672-190">读/写</span><span class="sxs-lookup"><span data-stu-id="5d672-190">Read/Write</span></span>|<span data-ttu-id="5d672-191">所需的应用程序如果包括非托管的 COM 资源</span><span class="sxs-lookup"><span data-stu-id="5d672-191">Required if the application includes unmanaged COM resources</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="5d672-192">从 BizTalk Server 管理控制台中，可以指定将程序集添加到安装在 GAC （右键单击资源文件夹中的程序集，然后单击修改）。</span><span class="sxs-lookup"><span data-stu-id="5d672-192">From the BizTalk Server Administration console, you can specify that an assembly be added to the GAC on installation (right-click the assembly in the resources folder and then click Modify).</span></span> <span data-ttu-id="5d672-193">如果指定此选项，然后安装的 BizTalk 应用程序需要编写程序集文件夹，其中包含在 GAC 上的权限。</span><span class="sxs-lookup"><span data-stu-id="5d672-193">If this option is specified, then installing the BizTalk application requires Write permission on the assembly folder, which contains the GAC.</span></span> <span data-ttu-id="5d672-194">程序集文件夹的路径为 %systemroot%\assembly。</span><span class="sxs-lookup"><span data-stu-id="5d672-194">The path of the assembly folder is %SystemRoot%\assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d672-195">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d672-195">See Also</span></span>  
 [<span data-ttu-id="5d672-196">应用程序部署的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="5d672-196">Security Considerations for Application Deployment</span></span>](../core/security-considerations-for-application-deployment.md)