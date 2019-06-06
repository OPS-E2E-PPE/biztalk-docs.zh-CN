---
title: 如何指定 SSO 管理员和关联管理员帐户 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faff8a6a8b8b9a639c4e03c4c48c287835667238
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383851"
---
# <a name="how-to-specify-sso-administrators-and-affiliate-administrators-accounts"></a><span data-ttu-id="51989-102">如何指定 SSO 管理员和关联管理员帐户</span><span class="sxs-lookup"><span data-stu-id="51989-102">How to Specify SSO Administrators and Affiliate Administrators Accounts</span></span>
<span data-ttu-id="51989-103">企业单一登录 (SSO) 管理员和关联管理员帐户可以是主机组或个人帐户。</span><span class="sxs-lookup"><span data-stu-id="51989-103">The Enterprise Single Sign-On (SSO) Administrators and Affiliate Administrators accounts can be host group or individual accounts.</span></span> <span data-ttu-id="51989-104">在配置 SSO 系统之前，必须创建这些帐户。</span><span class="sxs-lookup"><span data-stu-id="51989-104">You must create these accounts before you configure the SSO system.</span></span>  
  
 <span data-ttu-id="51989-105">时使用域帐户，你必须创建的 SSO Administrators 和 SSO Affiliate Administrators 帐户为域全局安全组的域控制器中。</span><span class="sxs-lookup"><span data-stu-id="51989-105">When using domain accounts, you must create the SSO Administrators and SSO Affiliate Administrators accounts as a domain global security groups in the domain controller.</span></span> <span data-ttu-id="51989-106">域管理员必须创建这些帐户。</span><span class="sxs-lookup"><span data-stu-id="51989-106">The domain administrator must create these accounts.</span></span>  
  
 <span data-ttu-id="51989-107">必须在 SSO 数据库中指定的 Single Sign-on Administrators 和 Affiliate Administrators 帐户。</span><span class="sxs-lookup"><span data-stu-id="51989-107">You must specify the Single Sign-On Administrators and Affiliate Administrators accounts in the SSO database.</span></span> <span data-ttu-id="51989-108">使用 SSO Administrators 组更新 SSO 数据库之前，必须禁用单一登录系统。</span><span class="sxs-lookup"><span data-stu-id="51989-108">You must disable the Single Sign-On system before you update the SSO database with the SSO Administrators group.</span></span>  
  
 <span data-ttu-id="51989-109">下面的 XML 代码显示更新 SSO 数据库的示例 XML:</span><span class="sxs-lookup"><span data-stu-id="51989-109">The following XML code shows a sample XML for updating the SSO database:</span></span>  
  
```  
<sso>  
<globalInfo>  
<ssoAdminAccount>Domain\Accountname</ssoAdminAccount>  
<ssoAffiliateAdminAccount>Domain\Accountname</ssoAffiliateAdminAccount>  
</globalInfo>  
</sso>  
```  
  
> [!NOTE]
>  <span data-ttu-id="51989-110">配置向导自动指定 SSO 管理员和 SSO 关联管理员组在 SSO 数据库中。</span><span class="sxs-lookup"><span data-stu-id="51989-110">The Configuration Wizard automatically specifies the SSO administrator and SSO affiliate administrator groups in the SSO database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51989-111">如果 SSO 不进行配置，用户应检查是否正在混合模式域中使用域本地帐户。</span><span class="sxs-lookup"><span data-stu-id="51989-111">If SSO does not configure, users should check whether Domain Local Accounts are being used in a mixed-mode domain.</span></span>  
  
### <a name="to-disable-the-enterprise-single-sign-on-system-using-the-mmc-snap-in"></a><span data-ttu-id="51989-112">若要禁用企业单一登录系统使用 Mmc 管理单元</span><span class="sxs-lookup"><span data-stu-id="51989-112">To disable the Enterprise Single Sign-On system using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="51989-113">在“开始”  菜单上，依次单击“所有程序”  、“Microsoft Enterprise Single Sign-On”  和“SSO 管理”  。</span><span class="sxs-lookup"><span data-stu-id="51989-113">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="51989-114">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="51989-114">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="51989-115">右键单击**系统**，然后单击**禁用**。</span><span class="sxs-lookup"><span data-stu-id="51989-115">Right-click **System**, and then click **Disable**.</span></span>  
  
### <a name="to-disable-the-enterprise-single-sign-on-system-using-the-command-line"></a><span data-ttu-id="51989-116">若要禁用企业单一登录系统使用命令行</span><span class="sxs-lookup"><span data-stu-id="51989-116">To disable the Enterprise Single Sign-On system using the command line</span></span>  
  
1.  <span data-ttu-id="51989-117">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="51989-117">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="51989-118">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="51989-118">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="51989-119">默认安装目录\<*驱动器*\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="51989-119">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="51989-120">类型**ssomanage** –**disablesso**。</span><span class="sxs-lookup"><span data-stu-id="51989-120">Type **ssomanage** –**disablesso**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51989-121">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="51989-121">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-update-the-sso-database-using-the-mmc-snap-in"></a><span data-ttu-id="51989-122">使用 MMC 管理单元更新 SSO 数据库</span><span class="sxs-lookup"><span data-stu-id="51989-122">To update the SSO database using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="51989-123">上**启动**菜单上，单击**所有程序**， **Microsoft 企业单一登录**，然后**SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="51989-123">On the **Start** menu, click **All Programs**, **Microsoft Enterprise Single Sign-On**, and then **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="51989-124">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="51989-124">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="51989-125">右键单击**系统**，然后单击**更新**。</span><span class="sxs-lookup"><span data-stu-id="51989-125">Right-click **System**, and then click **Update**.</span></span>  
  
### <a name="to-update-the-sso-database-using-the-command-line"></a><span data-ttu-id="51989-126">使用命令行更新 SSO 数据库</span><span class="sxs-lookup"><span data-stu-id="51989-126">To update the SSO database using the command line</span></span>  
  
1. <span data-ttu-id="51989-127">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="51989-127">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="51989-128">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="51989-128">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="51989-129">默认安装目录 *\<驱动器\>* : \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="51989-129">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="51989-130">类型 \*\*ssomanage –updatedb \*\<更新文件\>\*\*<em>，其中 \*\<更新文件\></em> 是路径和 XML 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="51989-130">Type \*\*ssomanage –updatedb \*\<update file\>\*\*<em>, where \*\<update file\></em> is the path and name of the XML file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="51989-131">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="51989-131">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-enable-the-enterprise-single-sign-on-system-using-the-mmc-snap-in"></a><span data-ttu-id="51989-132">若要启用企业单一登录系统使用 Mmc 管理单元</span><span class="sxs-lookup"><span data-stu-id="51989-132">To enable the Enterprise Single Sign-On system using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="51989-133">上**启动**菜单上，单击**所有程序**， **Microsoft 企业单一登录**，然后**SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="51989-133">On the **Start** menu, click **All Programs**, **Microsoft Enterprise Single Sign-On**, and then **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="51989-134">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="51989-134">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="51989-135">右键单击**系统**，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="51989-135">Right-click **System**, and then click **Enable**.</span></span>  
  
### <a name="to-enable-the-enterprise-single-sign-on-system-using-the-command-line"></a><span data-ttu-id="51989-136">若要启用企业单一登录系统使用命令行</span><span class="sxs-lookup"><span data-stu-id="51989-136">To enable the Enterprise Single Sign-On system using the command line</span></span>  
  
1.  <span data-ttu-id="51989-137">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="51989-137">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="51989-138">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="51989-138">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="51989-139">默认安装目录 *\<驱动器\>* : \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="51989-139">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="51989-140">类型**ssomanage – enablesso**。</span><span class="sxs-lookup"><span data-stu-id="51989-140">Type **ssomanage –enablesso**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51989-141">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="51989-141">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51989-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="51989-142">See Also</span></span>  
 [<span data-ttu-id="51989-143">SSO 用户组</span><span class="sxs-lookup"><span data-stu-id="51989-143">SSO User Groups</span></span>](../core/sso-user-groups.md)