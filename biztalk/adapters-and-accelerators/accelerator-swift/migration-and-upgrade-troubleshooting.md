---
title: 迁移和升级进行故障排除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- upgrading, troubleshooting
- troubleshooting, upgrading
- troubleshooting, migrating
- migrating, troubleshooting
ms.assetid: 6e6c0ff9-7897-4de6-9e9b-b502b3a1785b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad7f575038257bc876e3fc822e624e91c93451ff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994638"
---
# <a name="migration-and-upgrade-troubleshooting"></a><span data-ttu-id="c6a0f-102">迁移和升级进行故障排除</span><span class="sxs-lookup"><span data-stu-id="c6a0f-102">Migration and Upgrade Troubleshooting</span></span>
## <a name="assemblies-need-to-be-undeployed-before-an-upgrade"></a><span data-ttu-id="c6a0f-103">需要先升级之前取消部署程序集</span><span class="sxs-lookup"><span data-stu-id="c6a0f-103">Assemblies need to be undeployed before an upgrade</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="c6a0f-104">故障现象</span><span class="sxs-lookup"><span data-stu-id="c6a0f-104">Symptom</span></span>  
 <span data-ttu-id="c6a0f-105">当您尝试升级 A4SWIFT 时，升级过程将失败。</span><span class="sxs-lookup"><span data-stu-id="c6a0f-105">When you attempt to upgrade A4SWIFT, the upgrade process fails.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="c6a0f-106">可能的原因</span><span class="sxs-lookup"><span data-stu-id="c6a0f-106">Possible Cause</span></span>  
 <span data-ttu-id="c6a0f-107">完成升级后仍将部署以下 A4SWIFT 程序集： Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration、 Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas，Microsoft.Solutions.FinancialServices.SWIFT.MrsrService。</span><span class="sxs-lookup"><span data-stu-id="c6a0f-107">The following A4SWIFT assemblies are still deployed when the upgrade is done:  Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration, Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas, Microsoft.Solutions.FinancialServices.SWIFT.MrsrService.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6a0f-108">无需重新部署 Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas。</span><span class="sxs-lookup"><span data-stu-id="c6a0f-108">You do not have to redeploy Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.</span></span> <span data-ttu-id="c6a0f-109">安装程序重新部署该程序集。</span><span class="sxs-lookup"><span data-stu-id="c6a0f-109">The installation program redeploys that assembly.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="c6a0f-110">解决方案</span><span class="sxs-lookup"><span data-stu-id="c6a0f-110">Solution</span></span>  
 <span data-ttu-id="c6a0f-111">手动取消部署按以下顺序的四个 A4SWIFT 程序集：</span><span class="sxs-lookup"><span data-stu-id="c6a0f-111">Manually undeploy the four A4SWIFT assemblies in the following order:</span></span>  
  
- <span data-ttu-id="c6a0f-112">Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration</span><span class="sxs-lookup"><span data-stu-id="c6a0f-112">Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration</span></span>  
  
- <span data-ttu-id="c6a0f-113">Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas</span><span class="sxs-lookup"><span data-stu-id="c6a0f-113">Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas</span></span>  
  
- <span data-ttu-id="c6a0f-114">Microsoft.Solutions.FinancialServices.SWIFT.MrsrService.</span><span class="sxs-lookup"><span data-stu-id="c6a0f-114">Microsoft.Solutions.FinancialServices.SWIFT.MrsrService.</span></span>  
  
  <span data-ttu-id="c6a0f-115">升级后，重新部署这些程序集 (使用**BTSTask.exe**) 按相反的顺序。</span><span class="sxs-lookup"><span data-stu-id="c6a0f-115">After you have upgraded, redeploy these assemblies (using **BTSTask.exe**) in the reverse order.</span></span>  
  
## <a name="an-upgrade-removes-access-permissions-for-the-service-folder"></a><span data-ttu-id="c6a0f-116">升级会删除服务文件夹的访问权限</span><span class="sxs-lookup"><span data-stu-id="c6a0f-116">An upgrade removes access permissions for the Service folder</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="c6a0f-117">故障现象</span><span class="sxs-lookup"><span data-stu-id="c6a0f-117">Symptom</span></span>  
 <span data-ttu-id="c6a0f-118">升级到后[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]，%programfiles%\Microsoft BizTalk Accelerator for SWIFT\Service 文件夹的访问权限不正确。</span><span class="sxs-lookup"><span data-stu-id="c6a0f-118">After an upgrade to [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)], the access permission for the %programfiles%\Microsoft BizTalk Accelerator for SWIFT\Service folder is incorrect.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="c6a0f-119">可能的原因</span><span class="sxs-lookup"><span data-stu-id="c6a0f-119">Possible Cause</span></span>  
 <span data-ttu-id="c6a0f-120">当你升级到[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]，升级过程中删除 %programfiles%\Microsoft BizTalk Accelerator for SWIFT\Service 文件夹从 A4SWIFT 管理员和 A4SWIFT 用户组的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c6a0f-120">When you upgrade to [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)], the upgrade process removes access permissions for the A4SWIFT Administrators and A4SWIFT Users groups from the %programfiles%\Microsoft BizTalk Accelerator for SWIFT\Service folder.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="c6a0f-121">解决方案</span><span class="sxs-lookup"><span data-stu-id="c6a0f-121">Solution</span></span>  
 <span data-ttu-id="c6a0f-122">如果遇到此问题，手动设置的服务文件夹的以下访问权限：</span><span class="sxs-lookup"><span data-stu-id="c6a0f-122">If you encounter this problem, manually set the following access permissions for the Service folder:</span></span>  
  
|<span data-ttu-id="c6a0f-123">组或用户名</span><span class="sxs-lookup"><span data-stu-id="c6a0f-123">Group or User Name</span></span>|<span data-ttu-id="c6a0f-124">权限</span><span class="sxs-lookup"><span data-stu-id="c6a0f-124">Permission</span></span>|  
|------------------------|----------------|  
|<span data-ttu-id="c6a0f-125">A4SWIFT 管理员</span><span class="sxs-lookup"><span data-stu-id="c6a0f-125">A4SWIFT Administrators</span></span>|<span data-ttu-id="c6a0f-126">完全控制</span><span class="sxs-lookup"><span data-stu-id="c6a0f-126">Full Control</span></span>|  
|<span data-ttu-id="c6a0f-127">A4SWIFT 用户</span><span class="sxs-lookup"><span data-stu-id="c6a0f-127">A4SWIFT Users</span></span>|<span data-ttu-id="c6a0f-128">读取及执行</span><span class="sxs-lookup"><span data-stu-id="c6a0f-128">Read & Execute</span></span>|  
  
 <span data-ttu-id="c6a0f-129">若要设置这些权限，请继续阅读，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c6a0f-129">To set these permissions, proceed as follows:</span></span>  
  
 <span data-ttu-id="c6a0f-130">在中[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，转到 *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Service。</span><span class="sxs-lookup"><span data-stu-id="c6a0f-130">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Service.</span></span>  
  
1.  <span data-ttu-id="c6a0f-131">右键单击服务文件夹，单击**属性**，然后单击**安全**选项卡。</span><span class="sxs-lookup"><span data-stu-id="c6a0f-131">Right-click the Service folder, click **Properties**, and then click the **Security** tab.</span></span>  
  
2.  <span data-ttu-id="c6a0f-132">在组或用户名称窗格的服务属性对话框中，单击**外**，输入 ***\<服务器名称\>* \A4SWIFT 管理员**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="c6a0f-132">In the Group or user names pane of the Service Properties dialog box, click **Add**, enter ***\<server name\>*\A4SWIFT Administrators**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6a0f-133">如果 A4SWIFT Administrators 组的域组，请输入 ***\<域名\>* \A4SWIFT 管理员**。</span><span class="sxs-lookup"><span data-stu-id="c6a0f-133">If the A4SWIFT Administrators group is a domain group, enter ***\<domain name\>*\A4SWIFT Administrators**.</span></span>  
  
3.  <span data-ttu-id="c6a0f-134">重复步骤 2 ***\<服务器名称\>* \A4SWIFT 用户**，或 **\<*域名*\>\A4SWIFT 用户**如果A4SWIFT 用户组是域组。</span><span class="sxs-lookup"><span data-stu-id="c6a0f-134">Repeat step 2 for ***\<server name\>*\A4SWIFT Users**, or **\<*domain name*\>\A4SWIFT Users** if the A4SWIFT Users group is a domain group.</span></span>  
  
4.  <span data-ttu-id="c6a0f-135">在组或用户名称窗格中，选择**A4SWIFT 管理员**。</span><span class="sxs-lookup"><span data-stu-id="c6a0f-135">In the Group or user names pane, select **A4SWIFT Administrators**.</span></span> <span data-ttu-id="c6a0f-136">在权限窗格中，选择**允许**有关**完全控制**。</span><span class="sxs-lookup"><span data-stu-id="c6a0f-136">In the Permissions pane, select **Allow** for **Full Control**.</span></span>  
  
5.  <span data-ttu-id="c6a0f-137">在组或用户名称窗格中，选择**A4SWIFT 用户**。</span><span class="sxs-lookup"><span data-stu-id="c6a0f-137">In the Group or user names pane, select **A4SWIFT Users**.</span></span> <span data-ttu-id="c6a0f-138">在权限窗格中，单击**允许**有关**读取和执行**，**列出文件夹内容**，以及**读取**。</span><span class="sxs-lookup"><span data-stu-id="c6a0f-138">In the Permissions pane, click **Allow** for **Read & Execute**, **List Folder Contents**, and **Read**.</span></span>  
  
6.  <span data-ttu-id="c6a0f-139">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="c6a0f-139">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6a0f-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6a0f-140">See Also</span></span>  
 [<span data-ttu-id="c6a0f-141">疑难解答：问题和解决方法</span><span class="sxs-lookup"><span data-stu-id="c6a0f-141">Troubleshooting: Issues and Resolutions</span></span>](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)