---
title: "迁移和升级故障排除 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- upgrading, troubleshooting
- troubleshooting, upgrading
- troubleshooting, migrating
- migrating, troubleshooting
ms.assetid: 6e6c0ff9-7897-4de6-9e9b-b502b3a1785b
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c0e2a18b1cdba47c999150b5bc52c0b016aec61
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="migration-and-upgrade-troubleshooting"></a><span data-ttu-id="f4125-102">迁移和升级故障排除</span><span class="sxs-lookup"><span data-stu-id="f4125-102">Migration and Upgrade Troubleshooting</span></span>
## <a name="assemblies-need-to-be-undeployed-before-an-upgrade"></a><span data-ttu-id="f4125-103">程序集需要升级之前未部署</span><span class="sxs-lookup"><span data-stu-id="f4125-103">Assemblies need to be undeployed before an upgrade</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="f4125-104">故障现象</span><span class="sxs-lookup"><span data-stu-id="f4125-104">Symptom</span></span>  
 <span data-ttu-id="f4125-105">当你尝试升级 A4SWIFT 时，则升级过程失败。</span><span class="sxs-lookup"><span data-stu-id="f4125-105">When you attempt to upgrade A4SWIFT, the upgrade process fails.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="f4125-106">可能的原因</span><span class="sxs-lookup"><span data-stu-id="f4125-106">Possible Cause</span></span>  
 <span data-ttu-id="f4125-107">在升级完成时，仍将部署以下 A4SWIFT 程序集： Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration、 Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas，Microsoft.Solutions.FinancialServices.SWIFT.MrsrService。</span><span class="sxs-lookup"><span data-stu-id="f4125-107">The following A4SWIFT assemblies are still deployed when the upgrade is done:  Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration, Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas, Microsoft.Solutions.FinancialServices.SWIFT.MrsrService.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4125-108">无需重新部署 Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas。</span><span class="sxs-lookup"><span data-stu-id="f4125-108">You do not have to redeploy Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.</span></span> <span data-ttu-id="f4125-109">安装程序将重新部署该程序集。</span><span class="sxs-lookup"><span data-stu-id="f4125-109">The installation program redeploys that assembly.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="f4125-110">解决方案</span><span class="sxs-lookup"><span data-stu-id="f4125-110">Solution</span></span>  
 <span data-ttu-id="f4125-111">手动取消部署按以下顺序的四个 A4SWIFT 程序集：</span><span class="sxs-lookup"><span data-stu-id="f4125-111">Manually undeploy the four A4SWIFT assemblies in the following order:</span></span>  
  
-   <span data-ttu-id="f4125-112">Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration</span><span class="sxs-lookup"><span data-stu-id="f4125-112">Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration</span></span>  
  
-   <span data-ttu-id="f4125-113">Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas</span><span class="sxs-lookup"><span data-stu-id="f4125-113">Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas</span></span>  
  
-   <span data-ttu-id="f4125-114">Microsoft.Solutions.FinancialServices.SWIFT.MrsrService。</span><span class="sxs-lookup"><span data-stu-id="f4125-114">Microsoft.Solutions.FinancialServices.SWIFT.MrsrService.</span></span>  
  
 <span data-ttu-id="f4125-115">在升级之后，重新部署这些程序集 (使用**BTSTask.exe**) 按相反的顺序。</span><span class="sxs-lookup"><span data-stu-id="f4125-115">After you have upgraded, redeploy these assemblies (using **BTSTask.exe**) in the reverse order.</span></span>  
  
## <a name="an-upgrade-removes-access-permissions-for-the-service-folder"></a><span data-ttu-id="f4125-116">升级会删除服务文件夹的访问权限</span><span class="sxs-lookup"><span data-stu-id="f4125-116">An upgrade removes access permissions for the Service folder</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="f4125-117">故障现象</span><span class="sxs-lookup"><span data-stu-id="f4125-117">Symptom</span></span>  
 <span data-ttu-id="f4125-118">升级到之后[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]，%programfiles%\Microsoft BizTalk Accelerator for SWIFT\Service 文件夹的访问权限不正确。</span><span class="sxs-lookup"><span data-stu-id="f4125-118">After an upgrade to [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)], the access permission for the %programfiles%\Microsoft BizTalk Accelerator for SWIFT\Service folder is incorrect.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="f4125-119">可能的原因</span><span class="sxs-lookup"><span data-stu-id="f4125-119">Possible Cause</span></span>  
 <span data-ttu-id="f4125-120">当你升级到[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]，升级过程从 %programfiles%\Microsoft BizTalk Accelerator for SWIFT\Service 文件夹中移除 A4SWIFT 管理员和 A4SWIFT 用户组的访问权限。</span><span class="sxs-lookup"><span data-stu-id="f4125-120">When you upgrade to [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)], the upgrade process removes access permissions for the A4SWIFT Administrators and A4SWIFT Users groups from the %programfiles%\Microsoft BizTalk Accelerator for SWIFT\Service folder.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="f4125-121">解决方案</span><span class="sxs-lookup"><span data-stu-id="f4125-121">Solution</span></span>  
 <span data-ttu-id="f4125-122">如果你遇到此问题，手动设置的服务文件夹的以下访问权限：</span><span class="sxs-lookup"><span data-stu-id="f4125-122">If you encounter this problem, manually set the following access permissions for the Service folder:</span></span>  
  
|<span data-ttu-id="f4125-123">组或用户名</span><span class="sxs-lookup"><span data-stu-id="f4125-123">Group or User Name</span></span>|<span data-ttu-id="f4125-124">权限</span><span class="sxs-lookup"><span data-stu-id="f4125-124">Permission</span></span>|  
|------------------------|----------------|  
|<span data-ttu-id="f4125-125">A4SWIFT 管理员</span><span class="sxs-lookup"><span data-stu-id="f4125-125">A4SWIFT Administrators</span></span>|<span data-ttu-id="f4125-126">完全控制</span><span class="sxs-lookup"><span data-stu-id="f4125-126">Full Control</span></span>|  
|<span data-ttu-id="f4125-127">A4SWIFT 用户</span><span class="sxs-lookup"><span data-stu-id="f4125-127">A4SWIFT Users</span></span>|<span data-ttu-id="f4125-128">读取及执行</span><span class="sxs-lookup"><span data-stu-id="f4125-128">Read & Execute</span></span>|  
  
 <span data-ttu-id="f4125-129">若要设置这些权限，请继续执行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f4125-129">To set these permissions, proceed as follows:</span></span>  
  
 <span data-ttu-id="f4125-130">在[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器中，移动到*%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\Service。</span><span class="sxs-lookup"><span data-stu-id="f4125-130">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to *%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\Service.</span></span>  
  
1.  <span data-ttu-id="f4125-131">右键单击服务文件夹，单击**属性**，然后单击**安全**选项卡。</span><span class="sxs-lookup"><span data-stu-id="f4125-131">Right-click the Service folder, click **Properties**, and then click the **Security** tab.</span></span>  
  
2.  <span data-ttu-id="f4125-132">在组或用户名称窗格中的服务属性对话框中，单击**添加**，输入 ***\<服务器名称\>*\A4SWIFT 管理员**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f4125-132">In the Group or user names pane of the Service Properties dialog box, click **Add**, enter ***\<server name\>*\A4SWIFT Administrators**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f4125-133">如果 A4SWIFT Administrators 组的域组，请输入 ***\<域名\>*\A4SWIFT 管理员**。</span><span class="sxs-lookup"><span data-stu-id="f4125-133">If the A4SWIFT Administrators group is a domain group, enter ***\<domain name\>*\A4SWIFT Administrators**.</span></span>  
  
3.  <span data-ttu-id="f4125-134">重复步骤 2  ***\<服务器名称\>*\A4SWIFT 用户**，或  **\<*域名*\>\A4SWIFT 用户 * * 如果 A4SWIFT 用户组是域组。</span><span class="sxs-lookup"><span data-stu-id="f4125-134">Repeat step 2 for ***\<server name\>*\A4SWIFT Users**, or **\<*domain name*\>\A4SWIFT Users** if the A4SWIFT Users group is a domain group.</span></span>  
  
4.  <span data-ttu-id="f4125-135">在组或用户名称窗格中，选择**A4SWIFT 管理员**。</span><span class="sxs-lookup"><span data-stu-id="f4125-135">In the Group or user names pane, select **A4SWIFT Administrators**.</span></span> <span data-ttu-id="f4125-136">在权限窗格中，选择**允许**为**完全控制**。</span><span class="sxs-lookup"><span data-stu-id="f4125-136">In the Permissions pane, select **Allow** for **Full Control**.</span></span>  
  
5.  <span data-ttu-id="f4125-137">在组或用户名称窗格中，选择**A4SWIFT 用户**。</span><span class="sxs-lookup"><span data-stu-id="f4125-137">In the Group or user names pane, select **A4SWIFT Users**.</span></span> <span data-ttu-id="f4125-138">在权限窗格中，单击**允许**为**读取和执行**，**列出文件夹内容**，和**读取**。</span><span class="sxs-lookup"><span data-stu-id="f4125-138">In the Permissions pane, click **Allow** for **Read & Execute**, **List Folder Contents**, and **Read**.</span></span>  
  
6.  <span data-ttu-id="f4125-139">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="f4125-139">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4125-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f4125-140">See Also</span></span>  
 [<span data-ttu-id="f4125-141">疑难解答：问题和解决方法</span><span class="sxs-lookup"><span data-stu-id="f4125-141">Troubleshooting: Issues and Resolutions</span></span>](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)