---
title: 如何向应用程序添加 BAM 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, definition files [BAM]
- BAM, applications
- managing [applications], definition files [BAM]
- definition files [BAM], managing
ms.assetid: 86f19030-e510-4527-ba74-10498c361c00
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7bcd96105455f0940b4882b1019b777922d86755
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981806"
---
# <a name="how-to-add-a-bam-artifact-to-an-application"></a><span data-ttu-id="efd00-102">如何向应用程序添加 BAM 项目</span><span class="sxs-lookup"><span data-stu-id="efd00-102">How to Add a BAM Artifact to an Application</span></span>
<span data-ttu-id="efd00-103">本主题介绍如何使用 BizTalk Server 管理控制台或命令行向 BizTalk 应用程序添加 BAM 项目。</span><span class="sxs-lookup"><span data-stu-id="efd00-103">This topic describes how to use the BizTalk Server Administration console or the command line to add a BAM artifact to a BizTalk application.</span></span> <span data-ttu-id="efd00-104">添加 BAM 定义文件不会部署 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="efd00-104">Adding a BAM definition file does not deploy the BAM definition.</span></span> <span data-ttu-id="efd00-105">导入应用程序 .msi 文件时会部署 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="efd00-105">The BAM definition is deployed when the application .msi file is imported.</span></span>  
  
 <span data-ttu-id="efd00-106">如果要覆盖应用程序中已有的 BAM 项目，请指定覆盖选项。</span><span class="sxs-lookup"><span data-stu-id="efd00-106">If you want to overwrite a BAM artifact that already exists in the application, specify the overwrite option.</span></span> <span data-ttu-id="efd00-107">仅当现有 BAM 项目具有与你想要添加的一个文件同名时，则需要使用覆盖选项。</span><span class="sxs-lookup"><span data-stu-id="efd00-107">The overwrite option is required only when the existing BAM artifact has the same file name as the one you want to add.</span></span> <span data-ttu-id="efd00-108">如果未指定，并且具有与要添加文件同名的应用程序中已存在 BAM 项目，则添加操作将失败。</span><span class="sxs-lookup"><span data-stu-id="efd00-108">If not specified, and BAM artifact already exists in the application with the same file name as the one being added, the add operation will fail.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="efd00-109">必要條件</span><span class="sxs-lookup"><span data-stu-id="efd00-109">Prerequisites</span></span>  
 <span data-ttu-id="efd00-110">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="efd00-110">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="efd00-111">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="efd00-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-add-a-bam-artifact-to-an-application"></a><span data-ttu-id="efd00-112">向应用程序添加 BAM 项目</span><span class="sxs-lookup"><span data-stu-id="efd00-112">To add a BAM artifact to an application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="efd00-113">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="efd00-113">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="efd00-114">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="efd00-114">Click **Start**, click **Al Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="efd00-115">在控制台树中，依次展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”、“BizTalk 组”、“应用程序”和要向其中添加 BAM 项目文件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="efd00-115">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk Group, expand Applications, and then expand the application to which you want to add a BAM artifact file.</span></span>  
  
3. <span data-ttu-id="efd00-116">右键单击**资源**文件夹，指向**添加**，然后单击**资源**。</span><span class="sxs-lookup"><span data-stu-id="efd00-116">Right-click the **Resources** folder, point to **Add**, and then click **Resources**.</span></span>  
  
4. <span data-ttu-id="efd00-117">单击**外**，选择 BAM 项目文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="efd00-117">Click **Add**, select the file of the BAM artifact, and then click **Open**.</span></span>  
  
5. <span data-ttu-id="efd00-118">在中**文件类型**下拉列表中，选择**system.biztalk: bam**。</span><span class="sxs-lookup"><span data-stu-id="efd00-118">In the **File type** drop-down list, select **System.BizTalk:BAM**.</span></span>  
  
6. <span data-ttu-id="efd00-119">在中**目标**，键入从.msi 文件，包括文件名称安装该应用程序时复制项目文件所在的位置的完整路径。</span><span class="sxs-lookup"><span data-stu-id="efd00-119">In **Destination**, type the full path of the location where the artifact file is to be copied when the application is installed from the .msi file, including the file name.</span></span> <span data-ttu-id="efd00-120">如果不提供此路径，则在安装过程中，该文件将不会被复制到本地文件系统，但在导入应用程序 .msi 文件时，会部署该文件。</span><span class="sxs-lookup"><span data-stu-id="efd00-120">If this path is not provided, the file is not copied to the local file system during installation, but it will be deployed when the application .msi file is imported.</span></span>  
  
    <span data-ttu-id="efd00-121">示例： **C:\My Applications\MyBAMfile.xml**</span><span class="sxs-lookup"><span data-stu-id="efd00-121">Example: **C:\My Applications\MyBAMfile.xml**</span></span>  
  
7. <span data-ttu-id="efd00-122">完成后，单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="efd00-122">When finished, click **OK**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="efd00-123">使用命令行</span><span class="sxs-lookup"><span data-stu-id="efd00-123">Using the command line</span></span>  
  
1. <span data-ttu-id="efd00-124">按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="efd00-124">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="efd00-125">键入以下命令，替换适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="efd00-125">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="efd00-126">**BTSTask AddResource** [**/ApplicationName:**<em>值</em>] **/Type:System.BizTalk:Bam** [**/overwrite**] **/Source:**<em>值</em>[**/Destination:**<em>值</em>] [**/Server:** <em>值</em>] [**/database:**<em>值</em>]</span><span class="sxs-lookup"><span data-stu-id="efd00-126">**BTSTask AddResource** [**/ApplicationName:**<em>value</em>] **/Type:System.BizTalk:Bam** [**/Overwrite**] **/Source:**<em>value</em> [**/Destination:**<em>value</em>] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="efd00-127">例如：</span><span class="sxs-lookup"><span data-stu-id="efd00-127">Example:</span></span>  
  
    <span data-ttu-id="efd00-128">**BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Bam / 覆盖 /Source:"C:\Source BAMfiles\MyBAMfile.xml"/Destination:"%BTADInstallDir%\BAMfiles\MyBAMfile.xml"/Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span><span class="sxs-lookup"><span data-stu-id="efd00-128">**BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Bam /Overwrite /Source:"C:\Source BAMfiles\MyBAMfile.xml" /Destination:"%BTADInstallDir%\ BAMfiles\MyBAMfile.xml" /Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span></span>  
  
   |<span data-ttu-id="efd00-129">参数</span><span class="sxs-lookup"><span data-stu-id="efd00-129">Parameter</span></span>|<span data-ttu-id="efd00-130">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="efd00-130">Value</span></span>|  
   |---------------|-----------|  
   |<span data-ttu-id="efd00-131">**/ 应用程序名称**</span><span class="sxs-lookup"><span data-stu-id="efd00-131">**/ApplicationName**</span></span>|<span data-ttu-id="efd00-132">向其添加 BAM 项目的 BizTalk 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="efd00-132">Name of the BizTalk application to which to add the BAM artifact.</span></span> <span data-ttu-id="efd00-133">如果未指定应用程序名称，则使用组的默认 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="efd00-133">If the application name is not specified, the default BizTalk application for the group is used.</span></span> <span data-ttu-id="efd00-134">如果名称包含空格，则必须将其括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="efd00-134">If the name includes spaces, you must enclose it in double quotation marks (").</span></span>|  
   |<span data-ttu-id="efd00-135">**/ 类型**</span><span class="sxs-lookup"><span data-stu-id="efd00-135">**/Type**</span></span>|<span data-ttu-id="efd00-136">**System.biztalk: bam** （此值不区分大小写。）</span><span class="sxs-lookup"><span data-stu-id="efd00-136">**System.BizTalk:Bam** (This value is not case-sensitive.)</span></span>|  
   |<span data-ttu-id="efd00-137">**/ 覆盖**</span><span class="sxs-lookup"><span data-stu-id="efd00-137">**/Overwrite**</span></span>|<span data-ttu-id="efd00-138">覆盖现有 BAM 项目的选项。</span><span class="sxs-lookup"><span data-stu-id="efd00-138">Option to overwrite an existing BAM artifact.</span></span> <span data-ttu-id="efd00-139">如果不指定，且应用程序中已存在与要添加的 BAM 项目同名的 BAM 项目，则 AddResource 操作将失败。</span><span class="sxs-lookup"><span data-stu-id="efd00-139">If not specified, and a BAM artifact already exists in the application that has the same file name as the BAM artifact being added, the AddResource operation fails.</span></span>|  
   |<span data-ttu-id="efd00-140">**/ 源**</span><span class="sxs-lookup"><span data-stu-id="efd00-140">**/Source**</span></span>|<span data-ttu-id="efd00-141">BAM 项目文件的完整路径，包含文件名。</span><span class="sxs-lookup"><span data-stu-id="efd00-141">Full path of the BAM artifact file, including the file name.</span></span> <span data-ttu-id="efd00-142">如果路径包含空格，则必须将其括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="efd00-142">If the path includes spaces, you must enclose it in double quotation marks (").</span></span>|  
   |<span data-ttu-id="efd00-143">**/ 目标**</span><span class="sxs-lookup"><span data-stu-id="efd00-143">**/Destination**</span></span>|<span data-ttu-id="efd00-144">从 .msi 文件安装应用程序时，BAM 项目文件要复制到的位置的完整路径。</span><span class="sxs-lookup"><span data-stu-id="efd00-144">Full path of the location where the BAM artifact file is to be copied when the application is installed from the .msi file.</span></span> <span data-ttu-id="efd00-145">如果未提供，该文件是期间不会复制到本地文件系统安装。</span><span class="sxs-lookup"><span data-stu-id="efd00-145">If not provided, the file is not copied to the local file system during installation.</span></span> <span data-ttu-id="efd00-146">如果路径包含空格，则必须将其括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="efd00-146">If the path includes spaces, you must enclose it in double quotation marks (").</span></span> <span data-ttu-id="efd00-147">您可以在路径中使用环境变量 %BTADInstallDir% 来指定应用程序安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="efd00-147">You can use the environment variable %BTADInstallDir% in the path to specify the application installation folder.</span></span>|  
   |<span data-ttu-id="efd00-148">**/ 服务器**</span><span class="sxs-lookup"><span data-stu-id="efd00-148">**/Server**</span></span>|<span data-ttu-id="efd00-149">BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。</span><span class="sxs-lookup"><span data-stu-id="efd00-149">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="efd00-150">只在实例名称与服务器名称不相同时才需要指定实例名称。</span><span class="sxs-lookup"><span data-stu-id="efd00-150">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="efd00-151">只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。</span><span class="sxs-lookup"><span data-stu-id="efd00-151">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="efd00-152">示例：</span><span class="sxs-lookup"><span data-stu-id="efd00-152">Examples:</span></span><br /><br /> <span data-ttu-id="efd00-153">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="efd00-153">Server=MyServer</span></span><br /><br /> <span data-ttu-id="efd00-154">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="efd00-154">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="efd00-155">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="efd00-155">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="efd00-156">**/ 数据库**</span><span class="sxs-lookup"><span data-stu-id="efd00-156">**/Database**</span></span>|<span data-ttu-id="efd00-157">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="efd00-157">Name of the BizTalk Management database.</span></span> <span data-ttu-id="efd00-158">如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="efd00-158">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="efd00-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="efd00-159">See Also</span></span>  
 <span data-ttu-id="efd00-160">[管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md) </span><span class="sxs-lookup"><span data-stu-id="efd00-160">[Managing .NET Assemblies, Certificates, and Other Resources](../core/managing-net-assemblies-certificates-and-other-resources.md) </span></span>  
 <span data-ttu-id="efd00-161">[AddResource 命令： BAM 项目](../core/addresource-command-bam-artifact.md) </span><span class="sxs-lookup"><span data-stu-id="efd00-161">[AddResource Command: BAM Artifact](../core/addresource-command-bam-artifact.md) </span></span>  
 <span data-ttu-id="efd00-162">[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="efd00-162">[Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="efd00-163">如何导入 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="efd00-163">How to Import a BizTalk Application</span></span>](../core/how-to-import-a-biztalk-application.md)