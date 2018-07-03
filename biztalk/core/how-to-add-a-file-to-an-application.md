---
title: 如何将文件添加到应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], adding files
- files, adding to applications
- managing [resources], adding files
ms.assetid: 6665b946-113a-4026-a0a3-6b67ede4b689
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7f07991c8ecb85f21eed4cf6fb59d11d3f6f15e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007670"
---
# <a name="how-to-add-a-file-to-an-application"></a><span data-ttu-id="af9c6-102">如何将文件添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="af9c6-102">How to Add a File to an Application</span></span>
<span data-ttu-id="af9c6-103">本主题介绍如何使用 BizTalk Server 管理控制台或命令行向 BizTalk 应用程序添加文件。</span><span class="sxs-lookup"><span data-stu-id="af9c6-103">This topic describes how to use the BizTalk Server Administration console or the command line to add a file to a BizTalk application.</span></span> <span data-ttu-id="af9c6-104">在安装应用程序时，添加到该应用程序中的文件将复制到安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="af9c6-104">Files that you add to your application are copied to the installation folder when the application is installed.</span></span> <span data-ttu-id="af9c6-105">还可以将文件导出到应用程序的 .msi 文件，以及随应用程序移到不同部署环境中。</span><span class="sxs-lookup"><span data-stu-id="af9c6-105">Files can also can be exported into the application's .msi file and moved to different deployment environments with the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af9c6-106">添加自述文件的说明，请参阅[自述文件链接如何](../core/how-to-link-to-a-readme-file.md)。</span><span class="sxs-lookup"><span data-stu-id="af9c6-106">For instructions on adding a Readme file, see [How to Link to a Readme File](../core/how-to-link-to-a-readme-file.md).</span></span>  
  
 <span data-ttu-id="af9c6-107">如果要覆盖应用程序中已有的文件，请指定“Overwrite”选项。</span><span class="sxs-lookup"><span data-stu-id="af9c6-107">If you want to overwrite a file that already exists in the application, specify the Overwrite option.</span></span> <span data-ttu-id="af9c6-108">只有两个文件同名时，“Overwrite”选项才生效。</span><span class="sxs-lookup"><span data-stu-id="af9c6-108">The overwrite option only works when both files have the same file name.</span></span> <span data-ttu-id="af9c6-109">如果未指定“Overwrite”选项，且应用程序中已经存在与要添加的文件名称相同的文件，则添加操作将失败。</span><span class="sxs-lookup"><span data-stu-id="af9c6-109">If not specified, and a file already exists in the application with the same file name as the one being added, the add operation will fail.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af9c6-110">与某些其他类型的项目不同，BizTalk 组中的多个文件可具有相同的文件名。</span><span class="sxs-lookup"><span data-stu-id="af9c6-110">Unlike some other types of artifacts, you can have more than one file having the same file name in a BizTalk group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="af9c6-111">必要條件</span><span class="sxs-lookup"><span data-stu-id="af9c6-111">Prerequisites</span></span>  
 <span data-ttu-id="af9c6-112">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="af9c6-112">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="af9c6-113">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="af9c6-113">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-add-a-file-to-an-application"></a><span data-ttu-id="af9c6-114">若要将文件添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="af9c6-114">To add a file to an application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="af9c6-115">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="af9c6-115">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="af9c6-116">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="af9c6-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="af9c6-117">在控制台树中，展开 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开要向其添加文件的应用程序所在的 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="af9c6-117">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] and the BizTalk Group containing the application to which you want to add the file.</span></span>  
  
3. <span data-ttu-id="af9c6-118">展开“应用程序”，然后展开要向其添加文件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="af9c6-118">Expand Applications and the application to which you want to add a file.</span></span>  
  
4. <span data-ttu-id="af9c6-119">右键单击**资源**文件夹，指向**添加**，然后单击**资源**。</span><span class="sxs-lookup"><span data-stu-id="af9c6-119">Right-click the **Resources** folder, point to **Add**, and then click **Resources**.</span></span>  
  
5. <span data-ttu-id="af9c6-120">单击**外**，选择的文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="af9c6-120">Click **Add**, select the file, and then click **Open**.</span></span>  
  
6. <span data-ttu-id="af9c6-121">在中**文件类型**下拉列表中，选择**system.biztalk: file**。</span><span class="sxs-lookup"><span data-stu-id="af9c6-121">In the **File type** drop-down list, select **System.BizTalk:File**.</span></span>  
  
7. <span data-ttu-id="af9c6-122">在中**目标**，键入该文件从.msi 文件，包括文件名称安装该应用程序时要复制的位置的完整路径。</span><span class="sxs-lookup"><span data-stu-id="af9c6-122">In **Destination**, type the full path of the location where the file is to be copied when the application is installed from the .msi file, including the file name.</span></span> <span data-ttu-id="af9c6-123">默认位置为 %BTAD_InstallDir%，即应用程序安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="af9c6-123">The default is %BTAD_InstallDir%, the application installation folder.</span></span> <span data-ttu-id="af9c6-124">如果未提供此路径，则在安装过程中，该文件不会复制到本地文件系统。</span><span class="sxs-lookup"><span data-stu-id="af9c6-124">If this path is not provided, the file is not copied to the local file system during installation.</span></span>  
  
8. <span data-ttu-id="af9c6-125">完成后，单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="af9c6-125">When finished, click **OK**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="af9c6-126">使用命令行</span><span class="sxs-lookup"><span data-stu-id="af9c6-126">Using the command line</span></span>  
  
1. <span data-ttu-id="af9c6-127">按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="af9c6-127">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="af9c6-128">键入以下命令，替换适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="af9c6-128">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="af9c6-129">**BTSTask AddResource** [**/ApplicationName:**<em>值</em>] **/Type:System.BizTalk:File** [**/overwrite**] **/Source:**<em>值</em>[**/Destination:**<em>值</em>] [**/Server:** <em>值</em>] [**/database:**<em>值</em>]</span><span class="sxs-lookup"><span data-stu-id="af9c6-129">**BTSTask AddResource** [**/ApplicationName:**<em>value</em>] **/Type:System.BizTalk:File** [**/Overwrite**] **/Source:**<em>value</em> [**/Destination:**<em>value</em>] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="af9c6-130">例如：</span><span class="sxs-lookup"><span data-stu-id="af9c6-130">Example:</span></span>  
  
    <span data-ttu-id="af9c6-131">**BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:File / 覆盖 /Source:"C:\Source Files\File.txt"/Destination:"C:\New Files\File.txt"/Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span><span class="sxs-lookup"><span data-stu-id="af9c6-131">**BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:File /Overwrite /Source:"C:\Source Files\File.txt" /Destination:"C:\New Files\File.txt" /Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span></span>  
  
   |<span data-ttu-id="af9c6-132">参数</span><span class="sxs-lookup"><span data-stu-id="af9c6-132">Parameter</span></span>|<span data-ttu-id="af9c6-133">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="af9c6-133">Value</span></span>|  
   |---------------|-----------|  
   |<span data-ttu-id="af9c6-134">**/ 应用程序名称**</span><span class="sxs-lookup"><span data-stu-id="af9c6-134">**/ApplicationName**</span></span>|<span data-ttu-id="af9c6-135">要将文件添加到 BizTalk 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="af9c6-135">Name of the BizTalk application to which to add the file.</span></span> <span data-ttu-id="af9c6-136">如果未指定应用程序名称，则将使用默认 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="af9c6-136">If the application name is not specified, the default BizTalk application is used.</span></span> <span data-ttu-id="af9c6-137">如果名称包含空格，则必须将其括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="af9c6-137">If the name includes spaces, you must enclose it in double quotation marks (").</span></span>|  
   |<span data-ttu-id="af9c6-138">**/ 类型**</span><span class="sxs-lookup"><span data-stu-id="af9c6-138">**/Type**</span></span>|<span data-ttu-id="af9c6-139">**System.biztalk: file** （此值不区分大小写。）</span><span class="sxs-lookup"><span data-stu-id="af9c6-139">**System.BizTalk:File** (This value is not case-sensitive.)</span></span>|  
   |<span data-ttu-id="af9c6-140">**/ 覆盖**</span><span class="sxs-lookup"><span data-stu-id="af9c6-140">**/Overwrite**</span></span>|<span data-ttu-id="af9c6-141">若要更新现有文件的选项。</span><span class="sxs-lookup"><span data-stu-id="af9c6-141">Option to update an existing file.</span></span> <span data-ttu-id="af9c6-142">如果未指定，且文件与要添加的文件具有相同名称的应用程序中已经存在，则 AddResource 操作将失败。</span><span class="sxs-lookup"><span data-stu-id="af9c6-142">If not specified, and a file already exists in the application that has the same name as the file being added, the AddResource operation fails.</span></span>|  
   |<span data-ttu-id="af9c6-143">**/ 源**</span><span class="sxs-lookup"><span data-stu-id="af9c6-143">**/Source**</span></span>|<span data-ttu-id="af9c6-144">该文件，其中包括文件名的完整路径。</span><span class="sxs-lookup"><span data-stu-id="af9c6-144">Full path of the file, including the file name.</span></span> <span data-ttu-id="af9c6-145">如果路径包含空格，则必须将其括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="af9c6-145">If the path includes spaces, you must enclose it in double quotation marks (").</span></span>|  
   |<span data-ttu-id="af9c6-146">**/ 目标**</span><span class="sxs-lookup"><span data-stu-id="af9c6-146">**/Destination**</span></span>|<span data-ttu-id="af9c6-147">将文件从.msi 文件安装应用程序时要复制的位置的完整路径。</span><span class="sxs-lookup"><span data-stu-id="af9c6-147">Full path of the location where the file is to be copied when the application is installed from the .msi file.</span></span> <span data-ttu-id="af9c6-148">如果路径包含空格，则必须将其括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="af9c6-148">If the path includes spaces, you must enclose it in double quotation marks (").</span></span> <span data-ttu-id="af9c6-149">如果未提供，该文件是期间不会复制到本地文件系统安装。</span><span class="sxs-lookup"><span data-stu-id="af9c6-149">If not provided, the file is not copied to the local file system during installation.</span></span>|  
   |<span data-ttu-id="af9c6-150">**/ 服务器**</span><span class="sxs-lookup"><span data-stu-id="af9c6-150">**/Server**</span></span>|<span data-ttu-id="af9c6-151">BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。</span><span class="sxs-lookup"><span data-stu-id="af9c6-151">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="af9c6-152">只在实例名称与服务器名称不相同时才需要指定实例名称。</span><span class="sxs-lookup"><span data-stu-id="af9c6-152">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="af9c6-153">只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。</span><span class="sxs-lookup"><span data-stu-id="af9c6-153">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="af9c6-154">示例：</span><span class="sxs-lookup"><span data-stu-id="af9c6-154">Examples:</span></span><br /><br /> <span data-ttu-id="af9c6-155">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="af9c6-155">Server=MyServer</span></span><br /><br /> <span data-ttu-id="af9c6-156">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="af9c6-156">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="af9c6-157">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="af9c6-157">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="af9c6-158">**/ 数据库**</span><span class="sxs-lookup"><span data-stu-id="af9c6-158">**/Database**</span></span>|<span data-ttu-id="af9c6-159">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="af9c6-159">Name of the BizTalk Management database.</span></span> <span data-ttu-id="af9c6-160">如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="af9c6-160">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="af9c6-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="af9c6-161">See Also</span></span>  
 <span data-ttu-id="af9c6-162">[管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md) </span><span class="sxs-lookup"><span data-stu-id="af9c6-162">[Managing .NET Assemblies, Certificates, and Other Resources](../core/managing-net-assemblies-certificates-and-other-resources.md) </span></span>  
 <span data-ttu-id="af9c6-163">[AddResource 命令： 文件](../core/addresource-command-file.md) </span><span class="sxs-lookup"><span data-stu-id="af9c6-163">[AddResource Command: File](../core/addresource-command-file.md) </span></span>  
 [<span data-ttu-id="af9c6-164">创建和修改 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="af9c6-164">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)