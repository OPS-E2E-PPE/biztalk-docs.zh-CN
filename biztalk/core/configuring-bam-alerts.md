---
title: 配置 BAM 警报 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, alerts
- alerts, timeout values
- Notification Services, configuration tips
- alerts, configuring
- managing [BAM definitions], configuring alerts
ms.assetid: 29327466-c8e9-41e8-bc12-f3ac6b5d3096
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8d9a1d00735d867aa73493a7eff257947749fee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391324"
---
# <a name="configuring-bam-alerts"></a><span data-ttu-id="b3e6d-102">配置 BAM 警报</span><span class="sxs-lookup"><span data-stu-id="b3e6d-102">Configuring BAM Alerts</span></span>
<span data-ttu-id="b3e6d-103">管理员可以修改 BAM 警报框架的某些元素。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-103">Administrators can modify certain elements of the BAM alert framework.</span></span> <span data-ttu-id="b3e6d-104">本主题介绍适用于管理员的配置选项。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-104">This topic describes the configuration options available to administrators.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3e6d-105">创建警报时应注意该数据存储在 OLAP、 星型架构和 Notification Services 数据库上的本地时间格式的时间。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-105">When creating alerts you should be aware that time data is stored in a Local Time format on the OLAP, Star Schema, and Notification Services databases.</span></span> <span data-ttu-id="b3e6d-106">此外，还假设所有三个数据库位于相同的时区。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-106">It is also assumed that all three databases are in the same time zone.</span></span> <span data-ttu-id="b3e6d-107">在主导入数据库中，信息存储在 UTC 时间格式，并且可以采用相同或不同的时区。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-107">On the Primary Import database, information is stored in the UTC time format and can be in the same or different time zone.</span></span>  
  
## <a name="changing-the-adf-configuration"></a><span data-ttu-id="b3e6d-108">更改 ADF 配置</span><span class="sxs-lookup"><span data-stu-id="b3e6d-108">Changing the ADF configuration</span></span>  
 <span data-ttu-id="b3e6d-109">在部署视图时，BAM 管理实用程序使用 bm.exe.config 文件中指定的 CommandTimeout 值来填充 Notification Services 应用程序定义文件\<EventRule\>\\< ActionTimeout\>元素。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-109">When deploying a view the BAM Management utility uses the CommandTimeout value specified in the bm.exe.config file to populate Notification Services application definition file \<EventRule\>\\<ActionTimeout\> element.</span></span>  
  
 <span data-ttu-id="b3e6d-110">更改 bm.exe.config 中的 CommandTimeout 值不会更改在更改之前所部署的视图的 CommandTimeout 值。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-110">Changing the value of CommandTimeout in bm.exe.config does not change the CommandTimeout value for views deployed prior to the change.</span></span>  
  
 <span data-ttu-id="b3e6d-111">下面的过程使用 ProcessBamNSFiles.vbs 来获得配置和 Notification Services 应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-111">The procedure below uses the ProcessBamNSFiles.vbs to obtain the configuration and the Notification Services application definition file.</span></span> <span data-ttu-id="b3e6d-112">该脚本的详细信息，请参阅[BAM 通知服务配置文件的命令行脚本](../core/bam-command-line-script-for-notification-services-configuration-files.md)。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-112">For more information on the script, see [BAM Command-Line Script for Notification Services Configuration Files](../core/bam-command-line-script-for-notification-services-configuration-files.md).</span></span>  
  
 <span data-ttu-id="b3e6d-113">如何更改用于已部署的视图的 NS 的 ActionTimeout:</span><span class="sxs-lookup"><span data-stu-id="b3e6d-113">How to change the ActionTimeout for NS for already deployed views:</span></span>  
  
#### <a name="to-change-the-command-timeout-value"></a><span data-ttu-id="b3e6d-114">若要更改命令超时值</span><span class="sxs-lookup"><span data-stu-id="b3e6d-114">To change the command timeout value</span></span>  
  
1.  <span data-ttu-id="b3e6d-115">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-115">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="b3e6d-116">通过在命令提示符下键入，导航到跟踪文件夹**cd"C:\Program Files\Microsoft BizTalk Server\<版本\>\Tracking"** 或**cd"C:\Program Files (x86) \Microsoft BizTalk服务器\<版本\>\Tracking"** 64 位计算机上。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-116">Navigate to the tracking folder by typing at the command prompt **cd “C:\Program Files\Microsoft BizTalk Server \<version\>\Tracking”** or **cd “C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\Tracking”** on a 64 bit computer.</span></span> <span data-ttu-id="b3e6d-117">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-117">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="b3e6d-118">检索 ADF 文件。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-118">Retrieve the ADF file.</span></span> <span data-ttu-id="b3e6d-119">类型**cscript ProcessBamNSFiles.vbs-Get \<ConfigFilePath\> \<文件路径\> \< PID Server\> \< PID 数据库\>** .</span><span class="sxs-lookup"><span data-stu-id="b3e6d-119">Type **cscript ProcessBamNSFiles.vbs -Get \<ConfigFilePath\> \<ADFFilePath\> \< PID Server\> \< PID database \>**.</span></span> <span data-ttu-id="b3e6d-120">ConfigFilePath、 文件路径、 PID 服务器和 PID 数据库替换为你安装的相应值。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-120">Replacing the ConfigFilePath, ADFFilePath, PID Server, and PID database with the appropriate values for your installation.</span></span>  
  
4.  <span data-ttu-id="b3e6d-121">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-121">Press **ENTER**.</span></span>  
  
5.  <span data-ttu-id="b3e6d-122">在编辑器中打开 ADF 文件并搜索\<ActionTimeout\>、 使用所需的值更新和请注意，此值是 XML 持续时间。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-122">Open the ADF file in an editor and search for \<ActionTimeout\>, update with desired value & please note that this value is an XML duration.</span></span>  
  
6.  <span data-ttu-id="b3e6d-123">保存该 ADF 文件。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-123">Save the ADF file.</span></span> <span data-ttu-id="b3e6d-124">类型**cscript ProcessBamNSFiles.vbs-Update \<ConfigFilePath\> \<文件路径\> \< PID Server\> \< PID 数据库\>**.</span><span class="sxs-lookup"><span data-stu-id="b3e6d-124">Type **cscript ProcessBamNSFiles.vbs -Update \<ConfigFilePath\> \<ADFFilePath\> \< PID Server\> \< PID database \>**.</span></span>  
  
7.  <span data-ttu-id="b3e6d-125">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-125">Press **ENTER**.</span></span>  
  
### <a name="notification-service-configuration-tips"></a><span data-ttu-id="b3e6d-126">通知服务配置提示</span><span class="sxs-lookup"><span data-stu-id="b3e6d-126">Notification Service configuration tips</span></span>  
 <span data-ttu-id="b3e6d-127">如果运行的远程计算机上放置警报数据库的方式配置 BAM 警报[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，则必须在 SQL Server 实例上安装 Notification Services 数据库组件。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-127">If you configure BAM Alerts in such a way as to place the Alerts databases on a remote computer running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], then the Notification Services Database Components must be installed on the SQL Server instance.</span></span> <span data-ttu-id="b3e6d-128">如果这些组件不存在的 SQL 实例上，BAM 警报的配置将因出现错误，指示无法通知服务扩展存储过程授予的权限。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-128">If these components are not present on the SQL instance, then configuration of BAM Alerts will fail with an error indicating that permissions could not be granted to the Notification Services Extended Stored Procedures.</span></span> <span data-ttu-id="b3e6d-129">有关安装 Notification Services 组件的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=61999 ](http://go.microsoft.com/fwlink/?LinkId=61999)。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-129">For more information on installing the Notification Services component, see [http://go.microsoft.com/fwlink/?LinkId=61999](http://go.microsoft.com/fwlink/?LinkId=61999).</span></span>  
  
 <span data-ttu-id="b3e6d-130">BAM 可更改 BAM 用于访问 Notification Services 的帐户。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-130">BAM allows you to change the account that BAM uses to access the Notification Services.</span></span> <span data-ttu-id="b3e6d-131">如果更改此帐户以任何方式用运行 NSControl 之外，您将收到一个错误，通知你使用 NSControl 更改帐户。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-131">If you change this account in any way other than running NSControl, you will receive an error informing you to use the NSControl to change the account.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3e6d-132">不能使用 LocalSystem 或 SYSTEM 帐户安装和配置 Notification Services。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-132">You cannot use the LocalSystem or SYSTEM accounts for installing and configuring Notification Services.</span></span> <span data-ttu-id="b3e6d-133">这些是特殊帐户无法登录到并且不能使用文件和 SQL Server 权限授予 BAM 警报用户。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-133">These are special accounts that you cannot log on to and that you cannot use to grant file and SQL Server permissions to the BAM alerts user.</span></span>  
>   
>  <span data-ttu-id="b3e6d-134">若要安装和配置 Notification Services，在本地计算机上创建新的用户帐户，授予其所有必需的权限，然后使用它来配置 Notification Services。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-134">To install and configure Notification Services, create a new user account on the local computer, grant it all the requisite permissions, and then use it to configure Notification Services.</span></span>  
  
##### <a name="to-change-ns-user-account-for-bam"></a><span data-ttu-id="b3e6d-135">若要为 BAM 更改 NS 用户帐户</span><span class="sxs-lookup"><span data-stu-id="b3e6d-135">To change NS user account for BAM</span></span>  
  
1. <span data-ttu-id="b3e6d-136">使用 NSControl 更新用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-136">Use NSControl to update the user account.</span></span>  
  
2. <span data-ttu-id="b3e6d-137">授予 NS 用户读取、 写入和更改到 BAM 警报文件位置共享的权限。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-137">Grant the NS user read, write, and change permissions to the BAM Alerts File Location share.</span></span>  
  
3. <span data-ttu-id="b3e6d-138">将 NS 用户添加为 BAMAlerts 实例和应用程序数据库中的 NSRunService 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-138">Add the NS user as a member of NSRunService role in both the BAMAlerts instance and application databases.</span></span>  
  
4. <span data-ttu-id="b3e6d-139">授予 NS 用户权限使用在文档在本地计算机上的[ http://go.microsoft.com/fwlink/?LinkId=62005 ](http://go.microsoft.com/fwlink/?LinkId=62005)。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-139">Grant the NS User rights on the local machine using the documentation at [http://go.microsoft.com/fwlink/?LinkId=62005](http://go.microsoft.com/fwlink/?LinkId=62005).</span></span>  
  
5. <span data-ttu-id="b3e6d-140">根据数据库对 NS NS 权限授予[ http://go.microsoft.com/fwlink/?LinkId=62008 ](http://go.microsoft.com/fwlink/?LinkId=62008)。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-140">Grant the NS rights to the NS database according to [http://go.microsoft.com/fwlink/?LinkId=62008](http://go.microsoft.com/fwlink/?LinkId=62008).</span></span>  
  
6. <span data-ttu-id="b3e6d-141">授予 NS 用户登录到主导入数据库的 SQL 服务器和数据库访问权限。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-141">Grant the NS user login rights to SQL server and database access to the Primary Import database.</span></span>  
  
7. <span data-ttu-id="b3e6d-142">将 NS 用户添加为 BAM_ManagmentNSReader SQL 角色。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-142">Add the NS user to the BAM_ManagmentNSReader SQL role.</span></span>  
  
8. <span data-ttu-id="b3e6d-143">将 NS 用户添加到 BamAnalysis 数据库中的"BAM 警报"角色。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-143">Add the NS user to the "BAM Alerts" role in BamAnalysis database.</span></span>  
  
   <span data-ttu-id="b3e6d-144">如果修改了送达的警报的文件的文件存放位置。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-144">If you modify the file drop location for alerts delivered by file.</span></span> <span data-ttu-id="b3e6d-145">必须重新启动 SQL Notification Services。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-145">You must restart the SQL Notifications Services.</span></span>  
  
   <span data-ttu-id="b3e6d-146">如果不重新启动 NS 服务，警报将继续传送到原始文件存放位置。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-146">If the NS service is not restarted, alerts will continue being delivered to the original file drop location.</span></span>  
  
   <span data-ttu-id="b3e6d-147">通过修改 BAM 配置文件的以下行并使用 BAM 管理实用程序 update-config 命令可以更改文件存放位置。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-147">The file drop location is changed by modifying the following line of the BAM configuration file and using the BAM manangement utility update-config command.</span></span>  
  
   <span data-ttu-id="b3e6d-148">\<属性名称 ="FileDropUNC"\>\\\\< 计算机名\>\alerts\</Property\></span><span class="sxs-lookup"><span data-stu-id="b3e6d-148">\<Property Name="FileDropUNC"\>\\\\<computer name\>\alerts\</Property\></span></span>  
  
   <span data-ttu-id="b3e6d-149">有关 BAM 管理实用程序的详细信息，请参阅[BAM 管理实用程序](../core/bam-management-utility.md)。</span><span class="sxs-lookup"><span data-stu-id="b3e6d-149">For more information on the BAM Management utility, see [BAM Management Utility](../core/bam-management-utility.md).</span></span>