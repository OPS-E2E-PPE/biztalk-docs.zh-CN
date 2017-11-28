---
title: "BAM 安全建议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, BAM
- managing [BAM], security
- BAM, security
ms.assetid: 73613123-c1ed-477a-9f5c-342b2573c975
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f26cd3051dd296cc2849cb9c8ba7f8aa1d7ac6a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="bam-security-recommendations"></a><span data-ttu-id="978b6-102">BAM 安全建议</span><span class="sxs-lookup"><span data-stu-id="978b6-102">BAM Security Recommendations</span></span>
<span data-ttu-id="978b6-103">我们建议您遵守以下准则，以便在您的环境中保护和部署 BAM。</span><span class="sxs-lookup"><span data-stu-id="978b6-103">We recommend that you follow these guidelines for securing and deploying BAM in your environment:</span></span>  
  
-   <span data-ttu-id="978b6-104">如果您使用的是 [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]，则管理计算机必须安装下列软件以部署 BAM：</span><span class="sxs-lookup"><span data-stu-id="978b6-104">If you are using [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)], the administration computer must have the following software installed to deploy BAM:</span></span>  
  
    -   [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]  
  
    -   [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]<span data-ttu-id="978b6-105">客户端工具</span><span class="sxs-lookup"><span data-stu-id="978b6-105"> client tools</span></span>  
  
    -   [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]<span data-ttu-id="978b6-106">Integration Services</span><span class="sxs-lookup"><span data-stu-id="978b6-106"> Integration Services</span></span>  
  
    -   [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]<span data-ttu-id="978b6-107"> Analysis Services</span><span class="sxs-lookup"><span data-stu-id="978b6-107"> Analysis Services</span></span>  
  
    -   [!INCLUDE[SQLServer2005_SP3_long](../includes/sqlserver2005-sp3-long-md.md)]<span data-ttu-id="978b6-108">（如果您将使用 BAM 警报）</span><span class="sxs-lookup"><span data-stu-id="978b6-108">, if you will be using BAM alerts</span></span>  
  
        > [!NOTE]
        >  [!INCLUDE[SQLServer2005_SP3_short](../includes/sqlserver2005-sp3-short-md.md)]<span data-ttu-id="978b6-109"> 包含 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 的 [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)] 通知服务。</span><span class="sxs-lookup"><span data-stu-id="978b6-109"> contains [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Notification Services for [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="978b6-110">用于运行分析 DTS 包的用户上下文必须是 BAM 主导入数据库和 BAM 星型架构数据库的 db_owner [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="978b6-110">The user context under which the analysis DTS package runs must be a member of the db_owner [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] role of the BAM Primary Import and BAM Star Schema databases.</span></span> <span data-ttu-id="978b6-111">此外，分析服务在其下运行的服务帐户必须为 OLAP 管理员并且必须为 BAM 星型架构数据库的 db_owner。</span><span class="sxs-lookup"><span data-stu-id="978b6-111">In addition, the service account under which Analysis Services runs must be an OLAP administrator and must be a db_owner of the BAM Star Schema database.</span></span> <span data-ttu-id="978b6-112">有关详细信息，请参阅以下 Microsoft 帮助和支持 Web 站点[http://go.microsoft.com/fwlink/?LinkId=22781](http://go.microsoft.com/fwlink/?LinkId=22781)。</span><span class="sxs-lookup"><span data-stu-id="978b6-112">For more information, see the Microsoft Help and Support Web site at [http://go.microsoft.com/fwlink/?LinkId=22781](http://go.microsoft.com/fwlink/?LinkId=22781).</span></span>  
  
-   <span data-ttu-id="978b6-113">多个用户需要访问的实时和存档数据： 销售人员、 业务经理和其他人。</span><span class="sxs-lookup"><span data-stu-id="978b6-113">Multiple users need access to the live and archived data: salespeople, business managers, and others.</span></span> <span data-ttu-id="978b6-114">这些用户必须在 BAM 主导入数据库和 BAM 分析数据库所在的域（企业域）中具有域帐户，但他们的帐户不需要具有访问 BizTalk 资源的权限。</span><span class="sxs-lookup"><span data-stu-id="978b6-114">These users must have domain accounts in the domain where the BAM Primary Import and BAM Analysis databases are (corporate domain), but their accounts do not need to have access to BizTalk resources.</span></span>  
  
-   <span data-ttu-id="978b6-115">为了让用户可以访问 BAM 数据的视图，必须使用 BAM 管理实用程序 (BM.exe) 授予用户对视图的访问权限，此外，用户必须具有 SQL 登录名。</span><span class="sxs-lookup"><span data-stu-id="978b6-115">For users to access views of the BAM data, you must use the BAM management utility (BM.exe) to grant the users permissions to the views, and the users must have SQL logins.</span></span> <span data-ttu-id="978b6-116">有关 BAM 管理实用工具的详细信息，请参阅[BAM 管理实用工具](../core/bam-management-utility.md)。</span><span class="sxs-lookup"><span data-stu-id="978b6-116">For more information about the BAM management utility, see [BAM Management Utility](../core/bam-management-utility.md).</span></span>  
  
-   <span data-ttu-id="978b6-117">若要向可以访问 BAM 分析数据库中的多维数据集的角色添加用户，您必须在 BAM 数据库所在的域中有一台管理计算机。</span><span class="sxs-lookup"><span data-stu-id="978b6-117">To add users to roles that have access to the cubes in the BAM Analysis database, you must have an administration computer in the same domain as the BAM databases.</span></span>  
  
-   <span data-ttu-id="978b6-118">管理 BAM 的人员必须是 BAM 主导入数据库、星型架构数据库和 BAM 存档数据库的 db_owner。</span><span class="sxs-lookup"><span data-stu-id="978b6-118">The person administering BAM must be db_owner for the BAM Primary Import, Star Schema, and BAM Archive databases.</span></span> <span data-ttu-id="978b6-119">该人还必须是 BAM 分析数据库的 OLAP 管理员。</span><span class="sxs-lookup"><span data-stu-id="978b6-119">That person must also be an OLAP administrator for the BAM Analysis database.</span></span>  
  
-   <span data-ttu-id="978b6-120">如果要部署 Microsoft Office Excel 工作簿（.xls 文件），则必须在管理计算机上安装 Excel。</span><span class="sxs-lookup"><span data-stu-id="978b6-120">If you are deploying Microsoft Office Excel workbooks (.xls files), Excel must be installed on the administration computer.</span></span> <span data-ttu-id="978b6-121">部署某个工作簿之前，请打开它，并确保宏安全性设置为高，且没有任何警告。</span><span class="sxs-lookup"><span data-stu-id="978b6-121">Before you deploy a workbook, open it and ensure that the macro security is set to high, and that there are no warnings.</span></span>  
  
-   <span data-ttu-id="978b6-122">如果不需要将任何业务分发到与实际数据相连的用户 BAM Excel 工作簿中，我们建议您使用 XML 文件部署工作簿。</span><span class="sxs-lookup"><span data-stu-id="978b6-122">If there is no business need to distribute to the users BAM Excel workbooks that connect to the real data, we recommend that you deploy the workbooks by using XML files.</span></span> <span data-ttu-id="978b6-123">这样就不再需要在管理计算机上安装 Excel，也不再需要验证宏的安全性。</span><span class="sxs-lookup"><span data-stu-id="978b6-123">This eliminates the need to install Excel on the administration computer, and the need to verify the macro security level.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="978b6-124">当你删除对视图的用户的权限时，必须记住同时消除对用户设置的警报的任何订阅。</span><span class="sxs-lookup"><span data-stu-id="978b6-124">When you remove a user's permissions on a view, you must also remember to eliminate any subscriptions to alerts that the user has set.</span></span> <span data-ttu-id="978b6-125">有关从警报中删除订阅服务器的详细信息，请参阅[如何删除订阅服务器从警报](../core/how-to-remove-subscribers-from-an-alert.md)。</span><span class="sxs-lookup"><span data-stu-id="978b6-125">For more information about removing subscribers from an alert, see [How to Remove Subscribers from an Alert](../core/how-to-remove-subscribers-from-an-alert.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="978b6-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="978b6-126">See Also</span></span>  
 <span data-ttu-id="978b6-127">[最低安全用户权限](../core/minimum-security-user-rights.md) </span><span class="sxs-lookup"><span data-stu-id="978b6-127">[Minimum Security User Rights](../core/minimum-security-user-rights.md) </span></span>  
 [<span data-ttu-id="978b6-128">BizTalk Server 部署的安全建议</span><span class="sxs-lookup"><span data-stu-id="978b6-128">Security Recommendations for a BizTalk Server Deployment</span></span>](../core/security-recommendations-for-a-biztalk-server-deployment.md)