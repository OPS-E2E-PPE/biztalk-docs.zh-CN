---
title: 如何将帐户添加到视图 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], security
- Add-Account command [BAM]
- managing [BAM], adding accounts to views
ms.assetid: 0875796c-82a4-4165-9bed-88e8ba466548
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 808d5395452733d43337e0883b306b7757a7da08
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968667"
---
# <a name="how-to-add-accounts-to-a-view"></a><span data-ttu-id="bdd94-102">如何将帐户添加到视图</span><span class="sxs-lookup"><span data-stu-id="bdd94-102">How to Add Accounts to a View</span></span>
<span data-ttu-id="bdd94-103">管理员使用**添加帐户**命令以将用户与 BAM 视图关联，以防止未经授权的访问的 BAM Excel 电子表格视图。</span><span class="sxs-lookup"><span data-stu-id="bdd94-103">Administrators use the **add-account** command to associate users with BAM views and protect BAM Excel Spreadsheet views from unauthorized access.</span></span> <span data-ttu-id="bdd94-104">当用户保存 BAM 视图时，视图将引用隐藏工作簿中的 SQL 连接字符串。</span><span class="sxs-lookup"><span data-stu-id="bdd94-104">When users save BAM views, the views reference a SQL connection string that is hidden within the workbook.</span></span> <span data-ttu-id="bdd94-105">工作簿受到保护，但你必须确保已保护文档。</span><span class="sxs-lookup"><span data-stu-id="bdd94-105">The workbook is protected, but you must ensure that the document is protected.</span></span>  
  
 <span data-ttu-id="bdd94-106">将用户与 BAM 视图关联，限制访问权限向用户或向其授予访问权限的组视图。</span><span class="sxs-lookup"><span data-stu-id="bdd94-106">When you associate users with BAM views, you restrict access to the views to only the users or groups to whom you grant access.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bdd94-107">如果你使用的实时聚合 (Rta)，与添加用户**添加帐户**不会自动授予登录权限运行 SQL Server 的计算机。</span><span class="sxs-lookup"><span data-stu-id="bdd94-107">If you are using real-time aggregations (RTAs), users added with **add-account** are not automatically granted logon rights to the computer running SQL Server.</span></span> <span data-ttu-id="bdd94-108">如果你使用的 Rta，考虑建立包含所有需要查看的 Rta 视图的用户的 Windows 用户组。</span><span class="sxs-lookup"><span data-stu-id="bdd94-108">If you are using RTAs, consider establishing a Windows user group that contains all of the users that need to see views of the RTAs.</span></span> <span data-ttu-id="bdd94-109">组托管 BAM 主导入数据库的 SQL 服务器上的显式 SQL Server 登录权限的 Grant。</span><span class="sxs-lookup"><span data-stu-id="bdd94-109">Grant that group explicit SQL Server logon rights on the SQL server hosting the BAM Primary Import database.</span></span>  
  
 <span data-ttu-id="bdd94-110">有关查看 BAM 视图的信息，请参阅[如何列表 BAM 视图](../core/how-to-list-bam-views.md)。</span><span class="sxs-lookup"><span data-stu-id="bdd94-110">For information about viewing BAM views, see [How to List BAM Views](../core/how-to-list-bam-views.md).</span></span>  
  
### <a name="to-add-an-account-to-a-view"></a><span data-ttu-id="bdd94-111">若要将帐户添加到视图</span><span class="sxs-lookup"><span data-stu-id="bdd94-111">To add an account to a view</span></span>  
  
1.  <span data-ttu-id="bdd94-112">如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="bdd94-112">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="bdd94-113">通过在命令提示符处键入 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking，导航到跟踪文件夹。</span><span class="sxs-lookup"><span data-stu-id="bdd94-113">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="bdd94-114">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="bdd94-114">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="bdd94-115">类型**bm 添加帐户 AccountName:\<帐户名称\>的视图：\<视图名称\>**。</span><span class="sxs-lookup"><span data-stu-id="bdd94-115">Type **bm add-account -AccountName:\<account name\> -View:\<view name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bdd94-116">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="bdd94-116">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="bdd94-117">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="bdd94-117">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdd94-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bdd94-118">See Also</span></span>  
 <span data-ttu-id="bdd94-119">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="bdd94-119">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="bdd94-120">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="bdd94-120">BAM Management Utility</span></span>](../core/bam-management-utility.md)