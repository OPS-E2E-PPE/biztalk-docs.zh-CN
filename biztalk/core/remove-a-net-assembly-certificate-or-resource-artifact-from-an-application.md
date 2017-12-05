---
title: "如何删除从应用程序的.NET 程序集、 证书或其他资源项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12196886285a84b391eb3037064f36f08aa5b1fe
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-remove-a-net-assembly-certificate-or-other-resource-artifact-from-an-application"></a><span data-ttu-id="41bb3-102">如何从应用程序中删除 .NET 程序集、证书或其他资源项目</span><span class="sxs-lookup"><span data-stu-id="41bb3-102">How to Remove a .NET Assembly, Certificate, or Other Resource Artifact from an Application</span></span>
<span data-ttu-id="41bb3-103">本主题描述如何使用 BizTalk Server 管理控制台或命令行从 BizTalk 应用程序删除以下资源项目。</span><span class="sxs-lookup"><span data-stu-id="41bb3-103">This topic describes how to use the BizTalk Server Administration console or the command line to remove the following resource artifacts from a BizTalk application.</span></span> <span data-ttu-id="41bb3-104">使用本主题中的过程可以从 BizTalk 管理数据库中删除项目。</span><span class="sxs-lookup"><span data-stu-id="41bb3-104">Using the procedures in this topic removes the artifact from the BizTalk Management database.</span></span> <span data-ttu-id="41bb3-105">这一删除不会从文件系统、证书存储、Internet 信息服务 (IIS) 或 Windows 注册表中删除项目（如果项目存在于这些位置中）。</span><span class="sxs-lookup"><span data-stu-id="41bb3-105">It does not remove the artifact from the file system, certificate store, Internet Information Services (IIS), or the Windows registry, if it exists in any of these locations.</span></span> <span data-ttu-id="41bb3-106">此外，如果您删除某一绑定文件，则绑定保持不变，仅删除该绑定文件。</span><span class="sxs-lookup"><span data-stu-id="41bb3-106">In addition, if you remove a binding file, the bindings remain unchanged – only the binding file is removed.</span></span>  
  
-   <span data-ttu-id="41bb3-107">.NET 程序集</span><span class="sxs-lookup"><span data-stu-id="41bb3-107">.NET assemblies</span></span>  
  
-   <span data-ttu-id="41bb3-108">COM 组件</span><span class="sxs-lookup"><span data-stu-id="41bb3-108">COM components</span></span>  
  
-   <span data-ttu-id="41bb3-109">证书</span><span class="sxs-lookup"><span data-stu-id="41bb3-109">Certificates</span></span>  
  
-   <span data-ttu-id="41bb3-110">特别文件</span><span class="sxs-lookup"><span data-stu-id="41bb3-110">Ad hoc files</span></span>  
  
-   <span data-ttu-id="41bb3-111">BAM 定义</span><span class="sxs-lookup"><span data-stu-id="41bb3-111">BAM definitions</span></span>  
  
-   <span data-ttu-id="41bb3-112">绑定文件</span><span class="sxs-lookup"><span data-stu-id="41bb3-112">Binding files</span></span>  
  
-   <span data-ttu-id="41bb3-113">虚拟目录</span><span class="sxs-lookup"><span data-stu-id="41bb3-113">Virtual directories</span></span>  
  
 <span data-ttu-id="41bb3-114">如果通过导入或添加将某一虚拟目录显式添加到某一应用程序，则可以通过使用本主题中的过程删除该虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="41bb3-114">If a virtual directory is explicitly added to an application, either by being imported from or added, it can be removed by using the procedures in this topic.</span></span> <span data-ttu-id="41bb3-115">如果虚拟目录不是显式添加的，而是在配置接收位置时由引用添加的，则不能通过使用本主题中的过程删除该虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="41bb3-115">If it was not explicitly added, but rather was added by reference when a receive location was configured, you cannot remove it by using the procedures in this topic.</span></span> <span data-ttu-id="41bb3-116">这是因为，虚拟目录不存储于 BizTalk 管理数据库中。</span><span class="sxs-lookup"><span data-stu-id="41bb3-116">This is because the virtual directory is not stored in the BizTalk Management database.</span></span> <span data-ttu-id="41bb3-117">在导出应用程序的 .msi 文件时，将从 IIS 获取虚拟目录并将虚拟目录添加到 .msi 文件中。</span><span class="sxs-lookup"><span data-stu-id="41bb3-117">When you export the application .msi file the virtual directory will be obtained from IIS and added to the .msi file.</span></span> <span data-ttu-id="41bb3-118">在导入 .msi 文件时，虚拟目录将添加到该组的 BizTalk 管理数据库中。</span><span class="sxs-lookup"><span data-stu-id="41bb3-118">When you import the .msi file, the virtual directory will be added to the BizTalk Management database for that group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="41bb3-119">先决条件</span><span class="sxs-lookup"><span data-stu-id="41bb3-119">Prerequisites</span></span>  
 <span data-ttu-id="41bb3-120">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="41bb3-120">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="41bb3-121">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="41bb3-121">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-remove-a-resource-artifact-from-an-application"></a><span data-ttu-id="41bb3-122">从应用程序中删除资源项目</span><span class="sxs-lookup"><span data-stu-id="41bb3-122">To remove a resource artifact from an application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="41bb3-123">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="41bb3-123">Using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="41bb3-124">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="41bb3-124">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="41bb3-125">在控制台树中，依次展开 BizTalk Server 管理、 BizTalk 包含资源项目要删除的组，和包含项目的应用程序。</span><span class="sxs-lookup"><span data-stu-id="41bb3-125">In the console tree, expand BizTalk Server Administration, expand the BizTalk group containing the resource artifact to remove, and then expand the application containing the artifact.</span></span>  
  
3.  <span data-ttu-id="41bb3-126">单击**资源**文件夹，右键单击该项目，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="41bb3-126">Click the **Resources** folder, right-click the artifact, and then click **Remove**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="41bb3-127">使用命令行</span><span class="sxs-lookup"><span data-stu-id="41bb3-127">Using the command line</span></span>  
  
1.  <span data-ttu-id="41bb3-128">如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="41bb3-128">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="41bb3-129">键入以下命令，替换为适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="41bb3-129">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
     <span data-ttu-id="41bb3-130">**BTSTask RemoveResource** [**/ApplicationName:***值*] **/Luid:***值*[**/Server:***值*] [**/数据库：***值*]</span><span class="sxs-lookup"><span data-stu-id="41bb3-130">**BTSTask RemoveResource** [**/ApplicationName:***value*] **/Luid:***value* [**/Server:***value*] [**/Database:***value*]</span></span>  
  
     <span data-ttu-id="41bb3-131">例如：</span><span class="sxs-lookup"><span data-stu-id="41bb3-131">Example:</span></span>  
  
     <span data-ttu-id="41bb3-132">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyAssembly，Version = 1.0.0.0，Culture = neutral，PublicKeyToken = 0123456789ABCDEF"**</span><span class="sxs-lookup"><span data-stu-id="41bb3-132">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyAssembly, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**</span></span>  
  
    |<span data-ttu-id="41bb3-133">参数</span><span class="sxs-lookup"><span data-stu-id="41bb3-133">Parameter</span></span>|<span data-ttu-id="41bb3-134">Description</span><span class="sxs-lookup"><span data-stu-id="41bb3-134">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="41bb3-135">**/ 应用程序名称**</span><span class="sxs-lookup"><span data-stu-id="41bb3-135">**/ApplicationName**</span></span>|<span data-ttu-id="41bb3-136">包含要删除的项目的 BizTalk 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="41bb3-136">Name of the BizTalk application containing the artifact to delete.</span></span> <span data-ttu-id="41bb3-137">如果未指定，则使用默认应用程序。</span><span class="sxs-lookup"><span data-stu-id="41bb3-137">If not specified, the default application is used.</span></span> <span data-ttu-id="41bb3-138">如果名称包含空格，必须将它括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="41bb3-138">If the name includes spaces, you must enclose it in double quotation marks (").</span></span>|  
    |<span data-ttu-id="41bb3-139">**/ Luid**</span><span class="sxs-lookup"><span data-stu-id="41bb3-139">**/Luid**</span></span>|<span data-ttu-id="41bb3-140">项目的本地唯一标识符 (LUID)。</span><span class="sxs-lookup"><span data-stu-id="41bb3-140">Locally unique identifier (LUID) of the artifact.</span></span> <span data-ttu-id="41bb3-141">你可以通过使用获取而定**ListApp**命令时中, 所述[ListApp 命令](../core/listapp-command.md)。</span><span class="sxs-lookup"><span data-stu-id="41bb3-141">You can obtain the LUID by using the **ListApp** command, as described in [ListApp Command](../core/listapp-command.md).</span></span>|  
    |<span data-ttu-id="41bb3-142">**/ 服务器**</span><span class="sxs-lookup"><span data-stu-id="41bb3-142">**/Server**</span></span>|<span data-ttu-id="41bb3-143">BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。</span><span class="sxs-lookup"><span data-stu-id="41bb3-143">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="41bb3-144">只在实例名称与服务器名称不相同时才需要指定实例名称。</span><span class="sxs-lookup"><span data-stu-id="41bb3-144">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="41bb3-145">只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。</span><span class="sxs-lookup"><span data-stu-id="41bb3-145">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="41bb3-146">示例：</span><span class="sxs-lookup"><span data-stu-id="41bb3-146">Examples:</span></span><br /><br /> <span data-ttu-id="41bb3-147">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="41bb3-147">Server=MyServer</span></span><br /><br /> <span data-ttu-id="41bb3-148">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="41bb3-148">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="41bb3-149">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="41bb3-149">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
    |<span data-ttu-id="41bb3-150">**/ 数据库**</span><span class="sxs-lookup"><span data-stu-id="41bb3-150">**/Database**</span></span>|<span data-ttu-id="41bb3-151">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="41bb3-151">Name of the BizTalk Management database.</span></span> <span data-ttu-id="41bb3-152">如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="41bb3-152">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="41bb3-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41bb3-153">See Also</span></span>  
 <span data-ttu-id="41bb3-154">[管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md) </span><span class="sxs-lookup"><span data-stu-id="41bb3-154">[Managing .NET Assemblies, Certificates, and Other Resources](../core/managing-net-assemblies-certificates-and-other-resources.md) </span></span>  
 [<span data-ttu-id="41bb3-155">RemoveResource 命令</span><span class="sxs-lookup"><span data-stu-id="41bb3-155">RemoveResource Command</span></span>](../core/removeresource-command.md)