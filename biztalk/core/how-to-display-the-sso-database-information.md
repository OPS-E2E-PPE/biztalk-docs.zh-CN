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
ms.openlocfilehash: d90da02edcde220f2f36e0329ba001300ff5443b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385190"
---
# <a name="how-to-display-the-sso-database-information"></a><span data-ttu-id="d6052-102">如何显示 SSO 数据库信息</span><span class="sxs-lookup"><span data-stu-id="d6052-102">How to Display the SSO Database Information</span></span>
<span data-ttu-id="d6052-103">可以使用 MMC 管理单元或命令行 (ssomanage) 实用工具来查看 SSO 数据库信息。</span><span class="sxs-lookup"><span data-stu-id="d6052-103">You can view SSO database information by using the MMC Snap-In or the command line (ssomanage) utility.</span></span>  
  
### <a name="to-display-the-sso-database-information-using-the-mmc-snap-in"></a><span data-ttu-id="d6052-104">若要显示使用 MMC 管理单元中的 SSO 数据库信息</span><span class="sxs-lookup"><span data-stu-id="d6052-104">To display the SSO database information using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="d6052-105">在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。</span><span class="sxs-lookup"><span data-stu-id="d6052-105">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="d6052-106">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="d6052-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="d6052-107">右键单击“系统” ，然后单击“属性” 。</span><span class="sxs-lookup"><span data-stu-id="d6052-107">Right-click **System**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="d6052-108">单击选项卡**系统属性**对话框可以查看 SSO 数据库信息。</span><span class="sxs-lookup"><span data-stu-id="d6052-108">Click the tabs on the  **System Properties** dialog box to view SSO database information.</span></span>  
  
### <a name="to-display-the-sso-database-information-using-the-command-line"></a><span data-ttu-id="d6052-109">若要显示 SSO 数据库信息使用命令行</span><span class="sxs-lookup"><span data-stu-id="d6052-109">To display the SSO database information using the command line</span></span>  
  
1.  <span data-ttu-id="d6052-110">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="d6052-110">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="d6052-111">在命令行提示符下，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="d6052-111">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="d6052-112">默认安装目录**\<驱动器\>**: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="d6052-112">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="d6052-113">类型**ssomanage – displaydb**。</span><span class="sxs-lookup"><span data-stu-id="d6052-113">Type **ssomanage –displaydb**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6052-114">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="d6052-114">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-display-the-sso-database-the-sso-server-is-connected-to-using-the-command-line"></a><span data-ttu-id="d6052-115">若要显示 SSO 数据库 SSO 服务器被连接到使用命令行</span><span class="sxs-lookup"><span data-stu-id="d6052-115">To display the SSO database the SSO Server is connected to using the command line</span></span>  
  
1. <span data-ttu-id="d6052-116">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="d6052-116">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="d6052-117">在命令行提示符下，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="d6052-117">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="d6052-118">默认安装目录**\<驱动器\>**: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="d6052-118">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="d6052-119">类型**ssomanage – showdb**。</span><span class="sxs-lookup"><span data-stu-id="d6052-119">Type **ssomanage –showdb**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d6052-120">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="d6052-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
   <span data-ttu-id="d6052-121">下表介绍了这些过程所显示的值。</span><span class="sxs-lookup"><span data-stu-id="d6052-121">The following table describes the values displayed by these procedures.</span></span>  
  
|<span data-ttu-id="d6052-122">属性</span><span class="sxs-lookup"><span data-stu-id="d6052-122">Property</span></span>|<span data-ttu-id="d6052-123">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="d6052-123">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="d6052-124">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d6052-124">SQL Server</span></span>|<span data-ttu-id="d6052-125">**\<SQL Server 名称\>**</span><span class="sxs-lookup"><span data-stu-id="d6052-125">**\<SQL Server name\>**</span></span>|  
|<span data-ttu-id="d6052-126">单一登录数据库</span><span class="sxs-lookup"><span data-stu-id="d6052-126">Single Sign-On database</span></span>|<span data-ttu-id="d6052-127">**\<SQL Server 数据库名称\>**</span><span class="sxs-lookup"><span data-stu-id="d6052-127">**\<SQL Server database name\>**</span></span>|  
|<span data-ttu-id="d6052-128">单一登录密钥服务器名称</span><span class="sxs-lookup"><span data-stu-id="d6052-128">Single Sign-On Secret Server name</span></span>|<span data-ttu-id="d6052-129">**\<单一登录服务器名称\>**</span><span class="sxs-lookup"><span data-stu-id="d6052-129">**\<Single Sign-On Server name\>**</span></span>|  
|<span data-ttu-id="d6052-130">单一登录管理员帐户</span><span class="sxs-lookup"><span data-stu-id="d6052-130">Single Sign-On Administrators account</span></span>|<span data-ttu-id="d6052-131">域 \ 帐户名</span><span class="sxs-lookup"><span data-stu-id="d6052-131">Domain\account name</span></span>|  
|<span data-ttu-id="d6052-132">单一登录关联管理员帐户</span><span class="sxs-lookup"><span data-stu-id="d6052-132">Single Sign-On Affiliate Administrators account</span></span>|<span data-ttu-id="d6052-133">域 \ 帐户名</span><span class="sxs-lookup"><span data-stu-id="d6052-133">Domain\account name</span></span>|  
|<span data-ttu-id="d6052-134">已删除应用程序 （审核条目数） 的审核表大小</span><span class="sxs-lookup"><span data-stu-id="d6052-134">Size of audit table for deleted applications (number of audit entries)</span></span>|<span data-ttu-id="d6052-135">1000 （默认值）</span><span class="sxs-lookup"><span data-stu-id="d6052-135">1,000 (default)</span></span>|  
|<span data-ttu-id="d6052-136">已删除的用户映射 （审核条目数） 的审核表大小</span><span class="sxs-lookup"><span data-stu-id="d6052-136">Size of audit table for deleted user mappings (number of audit entries)</span></span>|<span data-ttu-id="d6052-137">1000 （默认值）</span><span class="sxs-lookup"><span data-stu-id="d6052-137">1,000 (default)</span></span>|  
|<span data-ttu-id="d6052-138">外部凭据查找 （审核条目数） 的审核表大小</span><span class="sxs-lookup"><span data-stu-id="d6052-138">Size of audit table for external credential lookups (number of audit entries)</span></span>|<span data-ttu-id="d6052-139">1000 （默认值）</span><span class="sxs-lookup"><span data-stu-id="d6052-139">1,000 (default)</span></span>|  
|<span data-ttu-id="d6052-140">票证超时 （以分钟为单位）</span><span class="sxs-lookup"><span data-stu-id="d6052-140">Ticket timeout (in minutes)</span></span>|<span data-ttu-id="d6052-141">2 （默认值）</span><span class="sxs-lookup"><span data-stu-id="d6052-141">2 (default)</span></span><br /><br /> <span data-ttu-id="d6052-142">此值可以是 1 到 525,600 之间的整数</span><span class="sxs-lookup"><span data-stu-id="d6052-142">This value can be an integer from1 through 525,600</span></span>|  
|<span data-ttu-id="d6052-143">凭据缓存超时 （以分钟为单位）</span><span class="sxs-lookup"><span data-stu-id="d6052-143">Credential cache timeout (in minutes)</span></span>|<span data-ttu-id="d6052-144">60 （默认值）</span><span class="sxs-lookup"><span data-stu-id="d6052-144">60 (default)</span></span>|  
|<span data-ttu-id="d6052-145">单一登录状态</span><span class="sxs-lookup"><span data-stu-id="d6052-145">Single Sign-On Status</span></span>|<span data-ttu-id="d6052-146">已启用/禁用</span><span class="sxs-lookup"><span data-stu-id="d6052-146">Enabled/disabled</span></span>|  
|<span data-ttu-id="d6052-147">允许使用票证</span><span class="sxs-lookup"><span data-stu-id="d6052-147">Tickets allowed</span></span>|<span data-ttu-id="d6052-148">是/否 （默认值）</span><span class="sxs-lookup"><span data-stu-id="d6052-148">Yes/no (default)</span></span>|  
|<span data-ttu-id="d6052-149">验证票证</span><span class="sxs-lookup"><span data-stu-id="d6052-149">Validate tickets</span></span>|<span data-ttu-id="d6052-150">是 （默认值）/否</span><span class="sxs-lookup"><span data-stu-id="d6052-150">Yes (default)/no</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d6052-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6052-151">See Also</span></span>  
 <span data-ttu-id="d6052-152">[如何配置 SSO 票证](../core/how-to-configure-the-sso-tickets.md) </span><span class="sxs-lookup"><span data-stu-id="d6052-152">[How to Configure the SSO Tickets](../core/how-to-configure-the-sso-tickets.md) </span></span>  
 [<span data-ttu-id="d6052-153">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="d6052-153">Using SSO</span></span>](../core/using-sso.md)