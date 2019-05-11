---
title: 如何从应用程序中删除.NET 程序集、 证书或其他资源项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- virtual directories, deleting
- managing [.NET assemblies], deleting
- managing [applications], COM components
- managing [applications], deleting artifcats
- managing [certificates], deleting
- deleting, binding files
- binding files, deleting
- managing, COM components
- COM components, deleting
- managing [artifacts], deleting
- .NET assemblies, deleting
- deleting, virtual directories
- deleting, definitions [BAM]
- applications, .NET assemblies
- certificates, deleting
- deleting, .NET assemblies
- deleting, artifacts
- deleting, certificates
ms.assetid: b84eebac-261d-495f-80cd-ddda5bb08bef
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0af1ab10400b51515b3041e12935e571eb76be69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397961"
---
# <a name="how-to-remove-a-net-assembly-certificate-or-other-resource-artifact-from-an-application"></a><span data-ttu-id="e5c4d-102">如何从应用程序中删除.NET 程序集、 证书或其他资源项目</span><span class="sxs-lookup"><span data-stu-id="e5c4d-102">How to Remove a .NET Assembly, Certificate, or Other Resource Artifact from an Application</span></span>
<span data-ttu-id="e5c4d-103">本主题介绍如何使用 BizTalk Server 管理控制台或命令行从 BizTalk 应用程序中删除以下资源项目。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-103">This topic describes how to use the BizTalk Server Administration console or the command line to remove the following resource artifacts from a BizTalk application.</span></span> <span data-ttu-id="e5c4d-104">使用本主题中的过程从 BizTalk 管理数据库中删除该项目。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-104">Using the procedures in this topic removes the artifact from the BizTalk Management database.</span></span> <span data-ttu-id="e5c4d-105">如果它存在于这些位置中，它不会从文件系统、 证书存储区、 Internet 信息服务 (IIS) 或 Windows 注册表中，删除该项目。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-105">It does not remove the artifact from the file system, certificate store, Internet Information Services (IIS), or the Windows registry, if it exists in any of these locations.</span></span> <span data-ttu-id="e5c4d-106">此外，如果删除绑定文件，则绑定保持不变，删除只绑定文件。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-106">In addition, if you remove a binding file, the bindings remain unchanged – only the binding file is removed.</span></span>  
  
- <span data-ttu-id="e5c4d-107">.NET 程序集</span><span class="sxs-lookup"><span data-stu-id="e5c4d-107">.NET assemblies</span></span>  
  
- <span data-ttu-id="e5c4d-108">COM 组件</span><span class="sxs-lookup"><span data-stu-id="e5c4d-108">COM components</span></span>  
  
- <span data-ttu-id="e5c4d-109">证书</span><span class="sxs-lookup"><span data-stu-id="e5c4d-109">Certificates</span></span>  
  
- <span data-ttu-id="e5c4d-110">特别文件</span><span class="sxs-lookup"><span data-stu-id="e5c4d-110">Ad hoc files</span></span>  
  
- <span data-ttu-id="e5c4d-111">BAM 定义</span><span class="sxs-lookup"><span data-stu-id="e5c4d-111">BAM definitions</span></span>  
  
- <span data-ttu-id="e5c4d-112">绑定文件</span><span class="sxs-lookup"><span data-stu-id="e5c4d-112">Binding files</span></span>  
  
- <span data-ttu-id="e5c4d-113">虚拟目录</span><span class="sxs-lookup"><span data-stu-id="e5c4d-113">Virtual directories</span></span>  
  
  <span data-ttu-id="e5c4d-114">如果虚拟目录显式添加到应用程序，同时从导入或添加，通过它可以通过使用本主题中的过程中删除。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-114">If a virtual directory is explicitly added to an application, either by being imported from or added, it can be removed by using the procedures in this topic.</span></span> <span data-ttu-id="e5c4d-115">如果它未显式添加，但而不是已通过引用来添加配置接收位置时，无法通过使用本主题中的过程中将其删除。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-115">If it was not explicitly added, but rather was added by reference when a receive location was configured, you cannot remove it by using the procedures in this topic.</span></span> <span data-ttu-id="e5c4d-116">这是因为 BizTalk 管理数据库中不存储的虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-116">This is because the virtual directory is not stored in the BizTalk Management database.</span></span> <span data-ttu-id="e5c4d-117">导出应用程序.msi 文件时将从 IIS 获取虚拟目录，并将其添加到.msi 文件中。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-117">When you export the application .msi file the virtual directory will be obtained from IIS and added to the .msi file.</span></span> <span data-ttu-id="e5c4d-118">导入.msi 文件时，虚拟目录将添加到该组的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-118">When you import the .msi file, the virtual directory will be added to the BizTalk Management database for that group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e5c4d-119">先决条件</span><span class="sxs-lookup"><span data-stu-id="e5c4d-119">Prerequisites</span></span>  
 <span data-ttu-id="e5c4d-120">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-120">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="e5c4d-121">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-121">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-remove-a-resource-artifact-from-an-application"></a><span data-ttu-id="e5c4d-122">若要从应用程序中删除资源项目</span><span class="sxs-lookup"><span data-stu-id="e5c4d-122">To remove a resource artifact from an application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="e5c4d-123">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="e5c4d-123">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="e5c4d-124">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-124">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="e5c4d-125">在控制台树中，依次展开 BizTalk Server 管理、 包含的资源项目的 BizTalk 组删除，和包含该项目的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-125">In the console tree, expand BizTalk Server Administration, expand the BizTalk group containing the resource artifact to remove, and then expand the application containing the artifact.</span></span>  
  
3. <span data-ttu-id="e5c4d-126">单击**资源**文件夹，右键单击该项目，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-126">Click the **Resources** folder, right-click the artifact, and then click **Remove**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="e5c4d-127">使用命令行</span><span class="sxs-lookup"><span data-stu-id="e5c4d-127">Using the command line</span></span>  
  
1. <span data-ttu-id="e5c4d-128">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-128">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="e5c4d-129">键入以下命令，替换适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="e5c4d-129">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="e5c4d-130">**BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span><span class="sxs-lookup"><span data-stu-id="e5c4d-130">**BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="e5c4d-131">例如：</span><span class="sxs-lookup"><span data-stu-id="e5c4d-131">Example:</span></span>  
  
    <span data-ttu-id="e5c4d-132">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyAssembly, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**</span><span class="sxs-lookup"><span data-stu-id="e5c4d-132">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyAssembly, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**</span></span>  
  
   |<span data-ttu-id="e5c4d-133">参数</span><span class="sxs-lookup"><span data-stu-id="e5c4d-133">Parameter</span></span>|<span data-ttu-id="e5c4d-134">Description</span><span class="sxs-lookup"><span data-stu-id="e5c4d-134">Description</span></span>|  
   |---------------|-----------------|  
   |<span data-ttu-id="e5c4d-135">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="e5c4d-135">**/ApplicationName**</span></span>|<span data-ttu-id="e5c4d-136">包含项目的 BizTalk 应用程序若要删除的名称。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-136">Name of the BizTalk application containing the artifact to delete.</span></span> <span data-ttu-id="e5c4d-137">如果未指定，则使用默认应用程序。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-137">If not specified, the default application is used.</span></span> <span data-ttu-id="e5c4d-138">如果名称包含空格，则必须将其括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-138">If the name includes spaces, you must enclose it in double quotation marks (").</span></span>|  
   |<span data-ttu-id="e5c4d-139">**/Luid**</span><span class="sxs-lookup"><span data-stu-id="e5c4d-139">**/Luid**</span></span>|<span data-ttu-id="e5c4d-140">项目的本地唯一标识符 (LUID)。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-140">Locally unique identifier (LUID) of the artifact.</span></span> <span data-ttu-id="e5c4d-141">可通过获得 LUID **ListApp**命令，如中所述[ListApp 命令](../core/listapp-command.md)。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-141">You can obtain the LUID by using the **ListApp** command, as described in [ListApp Command](../core/listapp-command.md).</span></span>|  
   |<span data-ttu-id="e5c4d-142">**/Server**</span><span class="sxs-lookup"><span data-stu-id="e5c4d-142">**/Server**</span></span>|<span data-ttu-id="e5c4d-143">承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-143">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="e5c4d-144">实例名称仅是所需的实例名称不同于服务器名称时。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-144">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="e5c4d-145">端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-145">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="e5c4d-146">示例：</span><span class="sxs-lookup"><span data-stu-id="e5c4d-146">Examples:</span></span><br /><br /> <span data-ttu-id="e5c4d-147">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="e5c4d-147">Server=MyServer</span></span><br /><br /> <span data-ttu-id="e5c4d-148">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="e5c4d-148">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="e5c4d-149">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-149">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="e5c4d-150">**/Database**</span><span class="sxs-lookup"><span data-stu-id="e5c4d-150">**/Database**</span></span>|<span data-ttu-id="e5c4d-151">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-151">Name of the BizTalk Management database.</span></span> <span data-ttu-id="e5c4d-152">如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="e5c4d-152">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5c4d-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5c4d-153">See Also</span></span>  
 <span data-ttu-id="e5c4d-154">[管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md) </span><span class="sxs-lookup"><span data-stu-id="e5c4d-154">[Managing .NET Assemblies, Certificates, and Other Resources](../core/managing-net-assemblies-certificates-and-other-resources.md) </span></span>  
 [<span data-ttu-id="e5c4d-155">RemoveResource 命令</span><span class="sxs-lookup"><span data-stu-id="e5c4d-155">RemoveResource Command</span></span>](../core/removeresource-command.md)