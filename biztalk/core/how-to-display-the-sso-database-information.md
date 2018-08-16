---
title: 如何显示 SSO 数据库信息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO], viewing SSO database
- SSO database, viewing
- viewing, SSO database
ms.assetid: 0ebadd2e-6ea5-460c-b0a8-f48589e6bf1c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8371ccae36fe66051178da5baa55360e9fcf8406
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010014"
---
# <a name="how-to-display-the-sso-database-information"></a><span data-ttu-id="8bb3c-102">如何显示 SSO 数据库信息</span><span class="sxs-lookup"><span data-stu-id="8bb3c-102">How to Display the SSO Database Information</span></span>
<span data-ttu-id="8bb3c-103">可以使用 MMC 管理单元或命令行 (ssomanage) 实用工具来查看 SSO 数据库信息。</span><span class="sxs-lookup"><span data-stu-id="8bb3c-103">You can view SSO database information by using the MMC Snap-In or the command line (ssomanage) utility.</span></span>  
  
### <a name="to-display-the-sso-database-information-using-the-mmc-snap-in"></a><span data-ttu-id="8bb3c-104">使用 MMC 管理单元显示 SSO 数据库信息</span><span class="sxs-lookup"><span data-stu-id="8bb3c-104">To display the SSO database information using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="8bb3c-105">在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。</span><span class="sxs-lookup"><span data-stu-id="8bb3c-105">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="8bb3c-106">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="8bb3c-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="8bb3c-107">右键单击“系统” ，然后单击“属性” 。</span><span class="sxs-lookup"><span data-stu-id="8bb3c-107">Right-click **System**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="8bb3c-108">单击选项卡**系统属性**对话框可以查看 SSO 数据库信息。</span><span class="sxs-lookup"><span data-stu-id="8bb3c-108">Click the tabs on the  **System Properties** dialog box to view SSO database information.</span></span>  
  
### <a name="to-display-the-sso-database-information-using-the-command-line"></a><span data-ttu-id="8bb3c-109">使用命令行显示 SSO 数据库信息</span><span class="sxs-lookup"><span data-stu-id="8bb3c-109">To display the SSO database information using the command line</span></span>  
  
1.  <span data-ttu-id="8bb3c-110">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="8bb3c-110">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="8bb3c-111">在命令行提示符下，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="8bb3c-111">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="8bb3c-112">默认安装目录**\<驱动器\>**: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="8bb3c-112">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="8bb3c-113">类型**ssomanage – displaydb**。</span><span class="sxs-lookup"><span data-stu-id="8bb3c-113">Type **ssomanage –displaydb**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8bb3c-114">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="8bb3c-114">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-display-the-sso-database-the-sso-server-is-connected-to-using-the-command-line"></a><span data-ttu-id="8bb3c-115">使用命令行显示 SSO 服务器连接到的 SSO 数据库</span><span class="sxs-lookup"><span data-stu-id="8bb3c-115">To display the SSO database the SSO Server is connected to using the command line</span></span>  
  
1. <span data-ttu-id="8bb3c-116">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="8bb3c-116">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="8bb3c-117">在命令行提示符下，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="8bb3c-117">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="8bb3c-118">默认安装目录**\<驱动器\>**: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="8bb3c-118">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="8bb3c-119">类型**ssomanage – showdb**。</span><span class="sxs-lookup"><span data-stu-id="8bb3c-119">Type **ssomanage –showdb**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="8bb3c-120">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="8bb3c-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
   <span data-ttu-id="8bb3c-121">下表对这些过程中显示的值进行了说明：</span><span class="sxs-lookup"><span data-stu-id="8bb3c-121">The following table describes the values displayed by these procedures.</span></span>  
  
|<span data-ttu-id="8bb3c-122">“属性”</span><span class="sxs-lookup"><span data-stu-id="8bb3c-122">Property</span></span>|<span data-ttu-id="8bb3c-123">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="8bb3c-123">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="8bb3c-124">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8bb3c-124">SQL Server</span></span>|<span data-ttu-id="8bb3c-125">**\<SQL Server 名称\>**</span><span class="sxs-lookup"><span data-stu-id="8bb3c-125">**\<SQL Server name\>**</span></span>|  
|<span data-ttu-id="8bb3c-126">单一登录数据库</span><span class="sxs-lookup"><span data-stu-id="8bb3c-126">Single Sign-On database</span></span>|<span data-ttu-id="8bb3c-127">**\<SQL Server 数据库名称\>**</span><span class="sxs-lookup"><span data-stu-id="8bb3c-127">**\<SQL Server database name\>**</span></span>|  
|<span data-ttu-id="8bb3c-128">单一登录密钥服务器名称</span><span class="sxs-lookup"><span data-stu-id="8bb3c-128">Single Sign-On Secret Server name</span></span>|<span data-ttu-id="8bb3c-129">**\<单一登录服务器名称\>**</span><span class="sxs-lookup"><span data-stu-id="8bb3c-129">**\<Single Sign-On Server name\>**</span></span>|  
|<span data-ttu-id="8bb3c-130">Single Sign-On Administrators 帐户</span><span class="sxs-lookup"><span data-stu-id="8bb3c-130">Single Sign-On Administrators account</span></span>|<span data-ttu-id="8bb3c-131">域\帐户名称</span><span class="sxs-lookup"><span data-stu-id="8bb3c-131">Domain\account name</span></span>|  
|<span data-ttu-id="8bb3c-132">Single Sign-On Affiliate Administrators 帐户</span><span class="sxs-lookup"><span data-stu-id="8bb3c-132">Single Sign-On Affiliate Administrators account</span></span>|<span data-ttu-id="8bb3c-133">域\帐户名称</span><span class="sxs-lookup"><span data-stu-id="8bb3c-133">Domain\account name</span></span>|  
|<span data-ttu-id="8bb3c-134">已删除的应用程序的审核表大小（审核条目数）</span><span class="sxs-lookup"><span data-stu-id="8bb3c-134">Size of audit table for deleted applications (number of audit entries)</span></span>|<span data-ttu-id="8bb3c-135">1000 （默认值）</span><span class="sxs-lookup"><span data-stu-id="8bb3c-135">1,000 (default)</span></span>|  
|<span data-ttu-id="8bb3c-136">已删除的用户映射的审核表大小（审核条目数）</span><span class="sxs-lookup"><span data-stu-id="8bb3c-136">Size of audit table for deleted user mappings (number of audit entries)</span></span>|<span data-ttu-id="8bb3c-137">1000 （默认值）</span><span class="sxs-lookup"><span data-stu-id="8bb3c-137">1,000 (default)</span></span>|  
|<span data-ttu-id="8bb3c-138">外部凭据查找的审核表大小（审核条目数）</span><span class="sxs-lookup"><span data-stu-id="8bb3c-138">Size of audit table for external credential lookups (number of audit entries)</span></span>|<span data-ttu-id="8bb3c-139">1000 （默认值）</span><span class="sxs-lookup"><span data-stu-id="8bb3c-139">1,000 (default)</span></span>|  
|<span data-ttu-id="8bb3c-140">票证超时（分钟）</span><span class="sxs-lookup"><span data-stu-id="8bb3c-140">Ticket timeout (in minutes)</span></span>|<span data-ttu-id="8bb3c-141">2 （默认值）</span><span class="sxs-lookup"><span data-stu-id="8bb3c-141">2 (default)</span></span><br /><br /> <span data-ttu-id="8bb3c-142">此值可为介于 1 到 525,600 之间的整数</span><span class="sxs-lookup"><span data-stu-id="8bb3c-142">This value can be an integer from1 through 525,600</span></span>|  
|<span data-ttu-id="8bb3c-143">凭据缓存超时（分钟）</span><span class="sxs-lookup"><span data-stu-id="8bb3c-143">Credential cache timeout (in minutes)</span></span>|<span data-ttu-id="8bb3c-144">60 （默认值）</span><span class="sxs-lookup"><span data-stu-id="8bb3c-144">60 (default)</span></span>|  
|<span data-ttu-id="8bb3c-145">单一登录状态</span><span class="sxs-lookup"><span data-stu-id="8bb3c-145">Single Sign-On Status</span></span>|<span data-ttu-id="8bb3c-146">已启用/已禁用</span><span class="sxs-lookup"><span data-stu-id="8bb3c-146">Enabled/disabled</span></span>|  
|<span data-ttu-id="8bb3c-147">允许使用票证</span><span class="sxs-lookup"><span data-stu-id="8bb3c-147">Tickets allowed</span></span>|<span data-ttu-id="8bb3c-148">是/否（默认）</span><span class="sxs-lookup"><span data-stu-id="8bb3c-148">Yes/no (default)</span></span>|  
|<span data-ttu-id="8bb3c-149">验证票证</span><span class="sxs-lookup"><span data-stu-id="8bb3c-149">Validate tickets</span></span>|<span data-ttu-id="8bb3c-150">是（默认）/否</span><span class="sxs-lookup"><span data-stu-id="8bb3c-150">Yes (default)/no</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8bb3c-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="8bb3c-151">See Also</span></span>  
 <span data-ttu-id="8bb3c-152">[如何配置 SSO 票证](../core/how-to-configure-the-sso-tickets.md) </span><span class="sxs-lookup"><span data-stu-id="8bb3c-152">[How to Configure the SSO Tickets](../core/how-to-configure-the-sso-tickets.md) </span></span>  
 [<span data-ttu-id="8bb3c-153">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="8bb3c-153">Using SSO</span></span>](../core/using-sso.md)