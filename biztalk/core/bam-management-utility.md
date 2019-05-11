---
title: BAM 管理实用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c55aabe2-f38b-4917-863c-b408a4eef98e
caps.latest.revision: 50
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd7569bb1f257c3b8686902ea5776e5bf8e1b467
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530584"
---
# <a name="bam-management-utility"></a><span data-ttu-id="96109-102">BAM 管理实用程序</span><span class="sxs-lookup"><span data-stu-id="96109-102">BAM Management Utility</span></span>
<span data-ttu-id="96109-103">业务活动监视 (BAM) 定义的管理员使用 BAM 管理实用程序来管理和维护 BAM 基础结构的所有方面。</span><span class="sxs-lookup"><span data-stu-id="96109-103">Administrators of Business Activity Monitoring (BAM) definitions use the BAM Management utility to manage and maintain all aspects of the BAM infrastructure.</span></span>  
  
 <span data-ttu-id="96109-104">可以使用 BAM 实用程序来执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="96109-104">You can use the BAM utility to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="96109-105">使用 BAM 定义和 BAM 配置 XML 作为输入。</span><span class="sxs-lookup"><span data-stu-id="96109-105">Consume BAM definition and BAM configuration XML as input.</span></span> <span data-ttu-id="96109-106">BAM 定义 XML 或 XLS 文件到跟踪和聚合，以及所跟踪数据的业务最终用户的视图定义的数据。</span><span class="sxs-lookup"><span data-stu-id="96109-106">The BAM definition XML or XLS files define the data to track and aggregate, as well as the business end user's view on the tracking data.</span></span> <span data-ttu-id="96109-107">BAM 配置 XML 规定的基础结构，如服务器名称、 数据库名称和其他数据库设置的部署位置。</span><span class="sxs-lookup"><span data-stu-id="96109-107">The BAM configuration XML mandates where to deploy the infrastructure, such as the server name, database name, and other database settings.</span></span>  
  
-   <span data-ttu-id="96109-108">部署在服务器上，其中包括 BAM 主导入数据库、 BAM 星型架构数据库、 BAM 分析数据库，运行时基础结构和相应的 Data Transformation Services (DTS) 包。</span><span class="sxs-lookup"><span data-stu-id="96109-108">Deploy the run-time infrastructure on the server, which includes the BAM Primary Import database, BAM Star Schema database, BAM Analysis database, and corresponding Data Transformation Services (DTS) packages.</span></span> <span data-ttu-id="96109-109">在此步骤中创建以下项：</span><span class="sxs-lookup"><span data-stu-id="96109-109">The following items are created during this step:</span></span>  
  
    -   <span data-ttu-id="96109-110">BAM 主导入数据库</span><span class="sxs-lookup"><span data-stu-id="96109-110">BAM Primary Import database</span></span>  
  
    -   <span data-ttu-id="96109-111">BAM 星型架构数据库</span><span class="sxs-lookup"><span data-stu-id="96109-111">BAM Star Schema database</span></span>  
  
    -   <span data-ttu-id="96109-112">BAM 存档数据库</span><span class="sxs-lookup"><span data-stu-id="96109-112">BAM Archive database</span></span>  
  
    -   <span data-ttu-id="96109-113">BAM 分析数据库</span><span class="sxs-lookup"><span data-stu-id="96109-113">BAM Analysis database</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96109-114">运行 BAM 管理实用程序的计算机的区域设置必须与用于创建 BAM 定义部署中对 BAM 命令才能正常工作的区域设置相同。</span><span class="sxs-lookup"><span data-stu-id="96109-114">The locale setting of the computer running the BAM Management utility must be the same as the locale used to create the BAM definition being deployed in order for the BAM commands to work properly.</span></span> <span data-ttu-id="96109-115">例如，如果您执行**get 视图**命令配置的计算机上为英语区域设置，而数据库使用法语区域设置的计算机上你将不能使用返回的视图名称，除非您重置你计算机为法语的区域设置。</span><span class="sxs-lookup"><span data-stu-id="96109-115">For example, if you execute the **get-views** command on a computer configured with an English locale setting against a database on a computer with a French locale you will not be able to use the returned view name unless you reset your computer locale to French.</span></span>  
  
 <span data-ttu-id="96109-116">可以使用 BAM 管理实用程序生成并部署跟踪配置的服务器上。</span><span class="sxs-lookup"><span data-stu-id="96109-116">You can use the BAM Management utility to generate and deploy your tracking configuration on a server.</span></span> <span data-ttu-id="96109-117">BAM 管理实用程序是一个命令行工具位于\<*安装路径*\>\Program Files\Microsoft BizTalk Server\<版本\>\Tracking\BM.exe。</span><span class="sxs-lookup"><span data-stu-id="96109-117">The BAM Management utility is a command-line tool located at \<*installation path*\>\Program Files\Microsoft BizTalk Server \<version\>\Tracking\BM.exe.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="96109-118">若要运行 BAM 管理实用程序，您必须隶属**db_owner** BAM 主导入、 BAM 星型架构和 BAM 存档数据库中的 SQL Server 数据库角色。</span><span class="sxs-lookup"><span data-stu-id="96109-118">To run the BAM management utility, you must be member of the **db_owner** SQL Server Database role in the BAM Primary Import, BAM Star Schema, and BAM Archive databases.</span></span> <span data-ttu-id="96109-119">与 BAM 警报相关的任何更新时，还必须对 BAM 警报数据库具有 sysadmin 权限。</span><span class="sxs-lookup"><span data-stu-id="96109-119">You must also have sysadmin permissions on the BAM Alerts databases if making any updates related to BAM Alerts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96109-120">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="96109-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="96109-121">要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="96109-121">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
## <a name="bam-management-utility-commands"></a><span data-ttu-id="96109-122">BAM 管理实用程序命令</span><span class="sxs-lookup"><span data-stu-id="96109-122">BAM Management Utility Commands</span></span>  
 <span data-ttu-id="96109-123">命令说明使用以下约定：</span><span class="sxs-lookup"><span data-stu-id="96109-123">The command descriptions use these conventions:</span></span>  
  
- <span data-ttu-id="96109-124">方括号 ([]) 表示可选参数。</span><span class="sxs-lookup"><span data-stu-id="96109-124">The square brackets ([]) indicate an optional parameter.</span></span>  
  
- <span data-ttu-id="96109-125">尖括号 （<>） 表示必需的参数。</span><span class="sxs-lookup"><span data-stu-id="96109-125">The angled brackets (<>) indicate a required parameter.</span></span>  
  
- <span data-ttu-id="96109-126">大括号 ({}) 指示应从枚举列表中选择一项。</span><span class="sxs-lookup"><span data-stu-id="96109-126">The braces ({}) indicate that one item should be selected from the enumerated list.</span></span>  
  
- <span data-ttu-id="96109-127">安全帐户可以是 NT 组或单个 NT 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="96109-127">A security account can be either an NT group or an individual NT user account.</span></span>  
  
- <span data-ttu-id="96109-128">BAM 定义文件可以是 XML 文件或 BAM Excel 工作簿文件 (.xls)。</span><span class="sxs-lookup"><span data-stu-id="96109-128">A BAM definition file can be either an XML file or a BAM Excel workbook file (.xls).</span></span>  
  
- <span data-ttu-id="96109-129">如果未提供 BAM 配置文件，则默认为当前文件夹中的 BamConfiguration.xml。</span><span class="sxs-lookup"><span data-stu-id="96109-129">If the BAM configuration file is not supplied, it defaults to BamConfiguration.xml in the current folder.</span></span>  
  
  <span data-ttu-id="96109-130">各个命令说明包含在以下主题：</span><span class="sxs-lookup"><span data-stu-id="96109-130">The Individual command descriptions are contained in the following topics:</span></span>  
  
- [<span data-ttu-id="96109-131">数据库命令</span><span class="sxs-lookup"><span data-stu-id="96109-131">Database Commands</span></span>](../core/database-commands.md)  
  
- [<span data-ttu-id="96109-132">BAM 定义（观察模型）部署命令</span><span class="sxs-lookup"><span data-stu-id="96109-132">Deployment of BAM Definition (Observation Model) Commands</span></span>](../core/deployment-of-bam-definition-observation-model-commands.md)  
  
- [<span data-ttu-id="96109-133">基础结构管理命令</span><span class="sxs-lookup"><span data-stu-id="96109-133">Infrastructure Management Commands</span></span>](../core/infrastructure-management-commands.md)  
  
- [<span data-ttu-id="96109-134">活动管理命令</span><span class="sxs-lookup"><span data-stu-id="96109-134">Activity Management Commands</span></span>](../core/activity-management-commands.md)  
  
- [<span data-ttu-id="96109-135">视图管理命令</span><span class="sxs-lookup"><span data-stu-id="96109-135">View Management Commands</span></span>](../core/view-management-commands.md)  
  
- [<span data-ttu-id="96109-136">警报管理命令</span><span class="sxs-lookup"><span data-stu-id="96109-136">Alert Management Commands</span></span>](../core/alert-management-commands.md)  
  
- [<span data-ttu-id="96109-137">用户管理命令</span><span class="sxs-lookup"><span data-stu-id="96109-137">User Management Commands</span></span>](../core/user-management-commands.md)  
  
- [<span data-ttu-id="96109-138">警报订阅管理命令</span><span class="sxs-lookup"><span data-stu-id="96109-138">Alert Subscription Management Commands</span></span>](../core/alert-subscription-management-commands.md)  
  
- [<span data-ttu-id="96109-139">侦听器管理命令</span><span class="sxs-lookup"><span data-stu-id="96109-139">Interceptor Management Commands</span></span>](../core/interceptor-management-commands.md)  
  
## <a name="displaying-the-bam-management-utility-help"></a><span data-ttu-id="96109-140">显示 BAM 管理实用程序帮助</span><span class="sxs-lookup"><span data-stu-id="96109-140">Displaying the BAM Management Utility Help</span></span>  
 <span data-ttu-id="96109-141">您使用 **/？**</span><span class="sxs-lookup"><span data-stu-id="96109-141">You use the **/?**</span></span> <span data-ttu-id="96109-142">或**帮助 BAM 管理实用程序**命令以显示 BAM 管理实用程序的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="96109-142">or the **help BAM Management utility** command to display the Help file for the BAM Management utility.</span></span>  
  
#### <a name="to-display-the-help-file-for-the-bam-management-utility"></a><span data-ttu-id="96109-143">若要显示 BAM 管理实用程序的帮助文件</span><span class="sxs-lookup"><span data-stu-id="96109-143">To display the Help file for the BAM Management utility</span></span>  
  
1.  <span data-ttu-id="96109-144">从命令提示符处，浏览到以下目录：C:\Program Files\Microsoft BizTalk Server\<版本\>\Tracking\\。</span><span class="sxs-lookup"><span data-stu-id="96109-144">From a command prompt, browse to the following directory: C:\Program Files\Microsoft BizTalk Server \<version\>\Tracking\\.</span></span>  
  
2.  <span data-ttu-id="96109-145">类型**bm**或**bm 帮助**。</span><span class="sxs-lookup"><span data-stu-id="96109-145">Type **bm** or **bm help**.</span></span>  
  
3.  <span data-ttu-id="96109-146">按 Enter。</span><span class="sxs-lookup"><span data-stu-id="96109-146">Press ENTER.</span></span>