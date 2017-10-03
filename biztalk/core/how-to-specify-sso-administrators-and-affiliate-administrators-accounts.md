---
title: "如何指定 SSO Administrators 和 Affiliate Administrators 帐户 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- administrator accounts, SSO
- enabling, SSO
- SSO, enabling
- disabling, SSO
- SSO, disabling
- managing [SSO], configuring administrator accounts
- managing [SSO], enabling
- managing [SSO], disabling
- SSO, administrator accounts
ms.assetid: 6c300e09-b781-45de-b2da-b1083164a1c0
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c588f476cca366f139a359bfccd28413a6057fe4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-specify-sso-administrators-and-affiliate-administrators-accounts"></a><span data-ttu-id="d7bb6-102">如何指定 SSO Administrators 和 Affiliate Administrators 帐户</span><span class="sxs-lookup"><span data-stu-id="d7bb6-102">How to Specify SSO Administrators and Affiliate Administrators Accounts</span></span>
<span data-ttu-id="d7bb6-103">企业单一登录 (SSO) 管理员和关联管理员帐户可以为主机组也可以为个人帐户。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-103">The Enterprise Single Sign-On (SSO) Administrators and Affiliate Administrators accounts can be host group or individual accounts.</span></span> <span data-ttu-id="d7bb6-104">必须首先创建这些帐户，然后才能配置 SSO 系统。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-104">You must create these accounts before you configure the SSO system.</span></span>  
  
 <span data-ttu-id="d7bb6-105">在使用域帐户时，必须将 SSO 管理员和 SSO 关联管理员帐户作为域控制器中的域全局安全组创建。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-105">When using domain accounts, you must create the SSO Administrators and SSO Affiliate Administrators accounts as a domain global security groups in the domain controller.</span></span> <span data-ttu-id="d7bb6-106">域管理员必须创建这些帐户。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-106">The domain administrator must create these accounts.</span></span>  
  
 <span data-ttu-id="d7bb6-107">必须在 SSO 数据库中指定单一登录管理员和关联管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-107">You must specify the Single Sign-On Administrators and Affiliate Administrators accounts in the SSO database.</span></span> <span data-ttu-id="d7bb6-108">必须首先禁用单一登录系统，然后才能用 SSO Administrators 组更新 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-108">You must disable the Single Sign-On system before you update the SSO database with the SSO Administrators group.</span></span>  
  
 <span data-ttu-id="d7bb6-109">以下 XML 代码显示了用于更新 SSO 数据库的 XML 示例：</span><span class="sxs-lookup"><span data-stu-id="d7bb6-109">The following XML code shows a sample XML for updating the SSO database:</span></span>  
  
```  
<sso>  
<globalInfo>  
<ssoAdminAccount>Domain\Accountname</ssoAdminAccount>  
<ssoAffiliateAdminAccount>Domain\Accountname</ssoAffiliateAdminAccount>  
</globalInfo>  
</sso>  
```  
  
> [!NOTE]
>  <span data-ttu-id="d7bb6-110">配置向导自动在 SSO 数据库中指定 SSO Administrators 和 SSO Affiliate Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-110">The Configuration Wizard automatically specifies the SSO administrator and SSO affiliate administrator groups in the SSO database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7bb6-111">如果未配置 SSO，用户应检查是否在混合模式域使用域本地帐户。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-111">If SSO does not configure, users should check whether Domain Local Accounts are being used in a mixed-mode domain.</span></span>  
  
### <a name="to-disable-the-enterprise-single-sign-on-system-using-the-mmc-snap-in"></a><span data-ttu-id="d7bb6-112">使用 MMC 管理单元禁用企业单一登录系统</span><span class="sxs-lookup"><span data-stu-id="d7bb6-112">To disable the Enterprise Single Sign-On system using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="d7bb6-113">在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-113">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="d7bb6-114">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-114">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="d7bb6-115">右键单击**系统**，然后单击**禁用**。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-115">Right-click **System**, and then click **Disable**.</span></span>  
  
### <a name="to-disable-the-enterprise-single-sign-on-system-using-the-command-line"></a><span data-ttu-id="d7bb6-116">使用命令行禁用企业单一登录系统</span><span class="sxs-lookup"><span data-stu-id="d7bb6-116">To disable the Enterprise Single Sign-On system using the command line</span></span>  
  
1.  <span data-ttu-id="d7bb6-117">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-117">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="d7bb6-118">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-118">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="d7bb6-119">默认安装目录是\<*驱动器*>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-119">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="d7bb6-120">类型**ssomanage** –**disablesso**。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-120">Type **ssomanage** –**disablesso**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d7bb6-121">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-121">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-update-the-sso-database-using-the-mmc-snap-in"></a><span data-ttu-id="d7bb6-122">使用 MMC 管理单元更新 SSO 数据库</span><span class="sxs-lookup"><span data-stu-id="d7bb6-122">To update the SSO database using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="d7bb6-123">上**启动**菜单上，单击**所有程序**， **Microsoft Enterprise 上单一登录**，，然后**SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-123">On the **Start** menu, click **All Programs**, **Microsoft Enterprise Single Sign-On**, and then **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="d7bb6-124">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-124">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="d7bb6-125">右键单击**系统**，然后单击**更新**。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-125">Right-click **System**, and then click **Update**.</span></span>  
  
### <a name="to-update-the-sso-database-using-the-command-line"></a><span data-ttu-id="d7bb6-126">使用命令行更新 SSO 数据库</span><span class="sxs-lookup"><span data-stu-id="d7bb6-126">To update the SSO database using the command line</span></span>  
  
1.  <span data-ttu-id="d7bb6-127">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-127">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="d7bb6-128">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-128">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="d7bb6-129">默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-129">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="d7bb6-130">类型**ssomanage-updatedb *\<更新文件 >***，其中*\<更新文件 >*是路径和 XML 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-130">Type **ssomanage –updatedb *\<update file>***, where *\<update file>* is the path and name of the XML file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d7bb6-131">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-131">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-enable-the-enterprise-single-sign-on-system-using-the-mmc-snap-in"></a><span data-ttu-id="d7bb6-132">使用 MMC 管理单元启用企业单一登录系统</span><span class="sxs-lookup"><span data-stu-id="d7bb6-132">To enable the Enterprise Single Sign-On system using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="d7bb6-133">上**启动**菜单上，单击**所有程序**， **Microsoft Enterprise 上单一登录**，，然后**SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-133">On the **Start** menu, click **All Programs**, **Microsoft Enterprise Single Sign-On**, and then **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="d7bb6-134">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-134">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="d7bb6-135">右键单击**系统**，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-135">Right-click **System**, and then click **Enable**.</span></span>  
  
### <a name="to-enable-the-enterprise-single-sign-on-system-using-the-command-line"></a><span data-ttu-id="d7bb6-136">使用命令行启用企业单一登录系统</span><span class="sxs-lookup"><span data-stu-id="d7bb6-136">To enable the Enterprise Single Sign-On system using the command line</span></span>  
  
1.  <span data-ttu-id="d7bb6-137">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-137">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="d7bb6-138">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-138">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="d7bb6-139">默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-139">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="d7bb6-140">类型**ssomanage-enablesso**。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-140">Type **ssomanage –enablesso**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d7bb6-141">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="d7bb6-141">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7bb6-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7bb6-142">See Also</span></span>  
 [<span data-ttu-id="d7bb6-143">SSO 用户组</span><span class="sxs-lookup"><span data-stu-id="d7bb6-143">SSO User Groups</span></span>](../core/sso-user-groups.md)