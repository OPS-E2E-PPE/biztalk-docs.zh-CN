---
title: 如何将一个 BAM 项目添加到应用程序 |Microsoft 文档
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
ms.openlocfilehash: 44b4a55141b2e5cfbc527dd386c9f1cbdd464dc9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247421"
---
# <a name="how-to-add-a-bam-artifact-to-an-application"></a><span data-ttu-id="113d2-102">如何将一个 BAM 项目添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="113d2-102">How to Add a BAM Artifact to an Application</span></span>
<span data-ttu-id="113d2-103">本主题介绍如何使用 BizTalk Server 管理控制台或命令行向 BizTalk 应用程序添加 BAM 项目。</span><span class="sxs-lookup"><span data-stu-id="113d2-103">This topic describes how to use the BizTalk Server Administration console or the command line to add a BAM artifact to a BizTalk application.</span></span> <span data-ttu-id="113d2-104">添加 BAM 定义文件不会部署 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="113d2-104">Adding a BAM definition file does not deploy the BAM definition.</span></span> <span data-ttu-id="113d2-105">导入应用程序 .msi 文件时会部署 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="113d2-105">The BAM definition is deployed when the application .msi file is imported.</span></span>  
  
 <span data-ttu-id="113d2-106">如果要覆盖应用程序中已有的 BAM 项目，请指定覆盖选项。</span><span class="sxs-lookup"><span data-stu-id="113d2-106">If you want to overwrite a BAM artifact that already exists in the application, specify the overwrite option.</span></span> <span data-ttu-id="113d2-107">仅当现有 BAM 项目具有与你想要添加的一个同名文件时，则需要使用覆盖选项。</span><span class="sxs-lookup"><span data-stu-id="113d2-107">The overwrite option is required only when the existing BAM artifact has the same file name as the one you want to add.</span></span> <span data-ttu-id="113d2-108">如果未指定，并且 BAM 项目已存在相同的文件名与所添加的应用程序中，添加操作将失败。</span><span class="sxs-lookup"><span data-stu-id="113d2-108">If not specified, and BAM artifact already exists in the application with the same file name as the one being added, the add operation will fail.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="113d2-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="113d2-109">Prerequisites</span></span>  
 <span data-ttu-id="113d2-110">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="113d2-110">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="113d2-111">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="113d2-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-add-a-bam-artifact-to-an-application"></a><span data-ttu-id="113d2-112">向应用程序添加 BAM 项目</span><span class="sxs-lookup"><span data-stu-id="113d2-112">To add a BAM artifact to an application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="113d2-113">使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="113d2-113">Using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="113d2-114">单击**启动**，单击**Al 程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="113d2-114">Click **Start**, click **Al Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="113d2-115">在控制台树中，依次展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”、“BizTalk 组”、“应用程序”和要向其中添加 BAM 项目文件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="113d2-115">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk Group, expand Applications, and then expand the application to which you want to add a BAM artifact file.</span></span>  
  
3.  <span data-ttu-id="113d2-116">右键单击**资源**文件夹，指向**添加**，然后单击**资源**。</span><span class="sxs-lookup"><span data-stu-id="113d2-116">Right-click the **Resources** folder, point to **Add**, and then click **Resources**.</span></span>  
  
4.  <span data-ttu-id="113d2-117">单击**添加**，选择 BAM 项目的文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="113d2-117">Click **Add**, select the file of the BAM artifact, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="113d2-118">在**文件类型**下拉列表中，选择**System.BizTalk:BAM**。</span><span class="sxs-lookup"><span data-stu-id="113d2-118">In the **File type** drop-down list, select **System.BizTalk:BAM**.</span></span>  
  
6.  <span data-ttu-id="113d2-119">在**目标**，键入项目文件从包括文件名称的.msi 文件安装应用程序时要复制的位置的完整路径。</span><span class="sxs-lookup"><span data-stu-id="113d2-119">In **Destination**, type the full path of the location where the artifact file is to be copied when the application is installed from the .msi file, including the file name.</span></span> <span data-ttu-id="113d2-120">如果不提供此路径，则在安装过程中，该文件将不会被复制到本地文件系统，但在导入应用程序 .msi 文件时，会部署该文件。</span><span class="sxs-lookup"><span data-stu-id="113d2-120">If this path is not provided, the file is not copied to the local file system during installation, but it will be deployed when the application .msi file is imported.</span></span>  
  
     <span data-ttu-id="113d2-121">示例： **C:\My Applications\MyBAMfile.xml**</span><span class="sxs-lookup"><span data-stu-id="113d2-121">Example: **C:\My Applications\MyBAMfile.xml**</span></span>  
  
7.  <span data-ttu-id="113d2-122">完成后，单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="113d2-122">When finished, click **OK**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="113d2-123">使用命令行</span><span class="sxs-lookup"><span data-stu-id="113d2-123">Using the command line</span></span>  
  
1.  <span data-ttu-id="113d2-124">如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="113d2-124">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="113d2-125">键入以下命令，替换为适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="113d2-125">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
     <span data-ttu-id="113d2-126">**BTSTask AddResource** [**/ApplicationName:***值*] **/Type:System.BizTalk:Bam** [**/覆盖**] **/Source:***值*[**/Destination:***值*] [**/Server:** *值*] [**/数据库：***值*]</span><span class="sxs-lookup"><span data-stu-id="113d2-126">**BTSTask AddResource** [**/ApplicationName:***value*] **/Type:System.BizTalk:Bam** [**/Overwrite**] **/Source:***value* [**/Destination:***value*] [**/Server:***value*] [**/Database:***value*]</span></span>  
  
     <span data-ttu-id="113d2-127">例如：</span><span class="sxs-lookup"><span data-stu-id="113d2-127">Example:</span></span>  
  
     <span data-ttu-id="113d2-128">**BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Bam / 覆盖 /Source:"C:\Source BAMfiles\MyBAMfile.xml"/Destination:"%BTADInstallDir%\BAMfiles\MyBAMfile.xml"/Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span><span class="sxs-lookup"><span data-stu-id="113d2-128">**BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Bam /Overwrite /Source:"C:\Source BAMfiles\MyBAMfile.xml" /Destination:"%BTADInstallDir%\ BAMfiles\MyBAMfile.xml" /Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span></span>  
  
    |<span data-ttu-id="113d2-129">参数</span><span class="sxs-lookup"><span data-stu-id="113d2-129">Parameter</span></span>|<span data-ttu-id="113d2-130">值</span><span class="sxs-lookup"><span data-stu-id="113d2-130">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="113d2-131">**/ 应用程序名称**</span><span class="sxs-lookup"><span data-stu-id="113d2-131">**/ApplicationName**</span></span>|<span data-ttu-id="113d2-132">向其添加 BAM 项目的 BizTalk 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="113d2-132">Name of the BizTalk application to which to add the BAM artifact.</span></span> <span data-ttu-id="113d2-133">如果未指定应用程序名称，则使用组的默认 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="113d2-133">If the application name is not specified, the default BizTalk application for the group is used.</span></span> <span data-ttu-id="113d2-134">如果名称包含空格，必须将它括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="113d2-134">If the name includes spaces, you must enclose it in double quotation marks (").</span></span>|  
    |<span data-ttu-id="113d2-135">**/ 类型**</span><span class="sxs-lookup"><span data-stu-id="113d2-135">**/Type**</span></span>|<span data-ttu-id="113d2-136">**System.BizTalk:Bam** （此值不区分大小写。）</span><span class="sxs-lookup"><span data-stu-id="113d2-136">**System.BizTalk:Bam** (This value is not case-sensitive.)</span></span>|  
    |<span data-ttu-id="113d2-137">**/ 覆盖**</span><span class="sxs-lookup"><span data-stu-id="113d2-137">**/Overwrite**</span></span>|<span data-ttu-id="113d2-138">覆盖现有 BAM 项目的选项。</span><span class="sxs-lookup"><span data-stu-id="113d2-138">Option to overwrite an existing BAM artifact.</span></span> <span data-ttu-id="113d2-139">如果不指定，且应用程序中已存在与要添加的 BAM 项目同名的 BAM 项目，则 AddResource 操作将失败。</span><span class="sxs-lookup"><span data-stu-id="113d2-139">If not specified, and a BAM artifact already exists in the application that has the same file name as the BAM artifact being added, the AddResource operation fails.</span></span>|  
    |<span data-ttu-id="113d2-140">**/ 源**</span><span class="sxs-lookup"><span data-stu-id="113d2-140">**/Source**</span></span>|<span data-ttu-id="113d2-141">BAM 项目文件的完整路径，包含文件名。</span><span class="sxs-lookup"><span data-stu-id="113d2-141">Full path of the BAM artifact file, including the file name.</span></span> <span data-ttu-id="113d2-142">如果路径包含空格，必须将它括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="113d2-142">If the path includes spaces, you must enclose it in double quotation marks (").</span></span>|  
    |<span data-ttu-id="113d2-143">**/ 目标**</span><span class="sxs-lookup"><span data-stu-id="113d2-143">**/Destination**</span></span>|<span data-ttu-id="113d2-144">从 .msi 文件安装应用程序时，BAM 项目文件要复制到的位置的完整路径。</span><span class="sxs-lookup"><span data-stu-id="113d2-144">Full path of the location where the BAM artifact file is to be copied when the application is installed from the .msi file.</span></span> <span data-ttu-id="113d2-145">如果未提供，不复制文件到本地文件系统在安装过程。</span><span class="sxs-lookup"><span data-stu-id="113d2-145">If not provided, the file is not copied to the local file system during installation.</span></span> <span data-ttu-id="113d2-146">如果路径包含空格，必须将它括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="113d2-146">If the path includes spaces, you must enclose it in double quotation marks (").</span></span> <span data-ttu-id="113d2-147">您可以在路径中使用环境变量 %BTADInstallDir% 来指定应用程序安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="113d2-147">You can use the environment variable %BTADInstallDir% in the path to specify the application installation folder.</span></span>|  
    |<span data-ttu-id="113d2-148">**/ 服务器**</span><span class="sxs-lookup"><span data-stu-id="113d2-148">**/Server**</span></span>|<span data-ttu-id="113d2-149">BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。</span><span class="sxs-lookup"><span data-stu-id="113d2-149">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="113d2-150">只在实例名称与服务器名称不相同时才需要指定实例名称。</span><span class="sxs-lookup"><span data-stu-id="113d2-150">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="113d2-151">只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。</span><span class="sxs-lookup"><span data-stu-id="113d2-151">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="113d2-152">示例：</span><span class="sxs-lookup"><span data-stu-id="113d2-152">Examples:</span></span><br /><br /> <span data-ttu-id="113d2-153">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="113d2-153">Server=MyServer</span></span><br /><br /> <span data-ttu-id="113d2-154">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="113d2-154">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="113d2-155">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="113d2-155">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
    |<span data-ttu-id="113d2-156">**/ 数据库**</span><span class="sxs-lookup"><span data-stu-id="113d2-156">**/Database**</span></span>|<span data-ttu-id="113d2-157">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="113d2-157">Name of the BizTalk Management database.</span></span> <span data-ttu-id="113d2-158">如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="113d2-158">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="113d2-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="113d2-159">See Also</span></span>  
 <span data-ttu-id="113d2-160">[管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md) </span><span class="sxs-lookup"><span data-stu-id="113d2-160">[Managing .NET Assemblies, Certificates, and Other Resources](../core/managing-net-assemblies-certificates-and-other-resources.md) </span></span>  
 <span data-ttu-id="113d2-161">[AddResource 命令： BAM 项目](../core/addresource-command-bam-artifact.md) </span><span class="sxs-lookup"><span data-stu-id="113d2-161">[AddResource Command: BAM Artifact](../core/addresource-command-bam-artifact.md) </span></span>  
 <span data-ttu-id="113d2-162">[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="113d2-162">[Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="113d2-163">如何导入 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="113d2-163">How to Import a BizTalk Application</span></span>](../core/how-to-import-a-biztalk-application.md)