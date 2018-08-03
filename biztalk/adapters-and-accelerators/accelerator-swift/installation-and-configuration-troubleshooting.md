---
title: 安装和配置故障排除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, troubleshooting
- configuring, troubleshooting
- troubleshooting, configuring
- troubleshooting, installing
ms.assetid: 25a2f6c5-c049-4042-8e38-4f7a2556e066
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10c0816508d2efb05dbac14797f80ffef12765fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967174"
---
# <a name="installation-and-configuration-troubleshooting"></a><span data-ttu-id="6d1cb-102">安装和配置故障排除</span><span class="sxs-lookup"><span data-stu-id="6d1cb-102">Installation and Configuration Troubleshooting</span></span>
## <a name="setup-is-unable-to-deploy-the-runtimeschemas-assembly"></a><span data-ttu-id="6d1cb-103">安装程序无法将 RuntimeSchemas 程序集部署</span><span class="sxs-lookup"><span data-stu-id="6d1cb-103">Setup is unable to deploy the RuntimeSchemas assembly</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6d1cb-104">故障现象</span><span class="sxs-lookup"><span data-stu-id="6d1cb-104">Symptom</span></span>  
 <span data-ttu-id="6d1cb-105">A4SWIFT 安装程序无法部署 RuntimeSchemas.dll。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-105">The A4SWIFT Setup program was unable to deploy RuntimeSchemas.dll.</span></span> <span data-ttu-id="6d1cb-106">如果在安装完成后没有手动部署该程序集，A4SWIFT 配置向导将失败。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-106">If the assembly is not deployed manually after setup, the A4SWIFT Configuration Wizard fails.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="6d1cb-107">可能的原因</span><span class="sxs-lookup"><span data-stu-id="6d1cb-107">Possible Cause</span></span>  
 <span data-ttu-id="6d1cb-108">存在以下条件之一：</span><span class="sxs-lookup"><span data-stu-id="6d1cb-108">One of the following conditions exists:</span></span>  
  
- <span data-ttu-id="6d1cb-109">当您尝试执行 A4SWIFT 的初始安装时已部署的运行时架构程序集。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-109">The Runtime Schemas assembly was already deployed when you tried to perform an initial installation of A4SWIFT.</span></span>  
  
- <span data-ttu-id="6d1cb-110">Microsoft[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]尝试 A4SWIFT 安装在计算机上未启动。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-110">Microsoft [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] was not started on the computer on which you tried to install A4SWIFT.</span></span>  
  
- <span data-ttu-id="6d1cb-111">当尝试升级 A4SWIFT，且被另一个程序集的已部署的运行时架构程序集。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-111">The Runtime Schemas assembly was already deployed when you tried to upgrade A4SWIFT, and was referenced by another assembly.</span></span> <span data-ttu-id="6d1cb-112">运行时架构程序集进行 A4SWIFT 此阻止取消部署升级程序。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-112">This prevented undeployment of the Runtime Schemas assembly by the A4SWIFT upgrade program.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="6d1cb-113">解决方案</span><span class="sxs-lookup"><span data-stu-id="6d1cb-113">Solution</span></span>  
 <span data-ttu-id="6d1cb-114">根据问题性质，则继续，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6d1cb-114">Proceed as follows, depending upon the nature of the problem:</span></span>  
  
- <span data-ttu-id="6d1cb-115">如果你尝试运行 A4SWIFT 的初始安装时已部署的运行时架构程序集，在 Microsoft 中打开 BizTalk 浏览器[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]，右键单击 Microsoft 的程序集。Solutions.FinancialServices.SWIFT.RuntimeSchemas，并单击取消部署。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-115">If the Runtime Schemas assembly was already deployed when you attempted to run an initial installation of A4SWIFT, open BizTalk Explorer in Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)], right-click the assembly Microsoft .Solutions.FinancialServices.SWIFT.RuntimeSchemas, and then click Undeploy.</span></span> <span data-ttu-id="6d1cb-116">使用 BizTalk 部署向导来部署最新版本从 RuntimeSchemas.dll *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Assemblies。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-116">Use the BizTalk Deployment Wizard to deploy the latest version of RuntimeSchemas.dll from *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Assemblies.</span></span>  
  
- <span data-ttu-id="6d1cb-117">如果[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]时未启动，启动[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]中[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]Service Manager。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-117">If [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] was not started, start [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] in the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] Service Manager.</span></span> <span data-ttu-id="6d1cb-118">使用 BizTalk 部署向导来部署最新版本从 RuntimeSchemas.dll *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Assemblies。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-118">Use the BizTalk Deployment Wizard to deploy the latest version of RuntimeSchemas.dll from *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Assemblies.</span></span>  
  
- <span data-ttu-id="6d1cb-119">如果运行时架构程序集已部署时尝试升级 A4SWIFT，且被的另一个程序集取消部署 BizTalk 浏览器中引用的程序集，并取消部署 RuntimeSchemas.dll 在 BizTalk 浏览器。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-119">If the Runtime Schemas assembly was already deployed when you tried to upgrade A4SWIFT, and was referenced by another assembly, undeploy the referencing assembly in BizTalk Explorer, and undeploy RuntimeSchemas.dll in BizTalk Explorer.</span></span> <span data-ttu-id="6d1cb-120">使用 BizTalk 部署向导来部署最新版本从 RuntimeSchemas.dll *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Assemblies。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-120">Use the BizTalk Deployment Wizard to deploy the latest version of RuntimeSchemas.dll from *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Assemblies.</span></span>  
  
## <a name="after-the-web-components-feature-is-removed-message-repair-and-reconciliation-is-incorrectly-shown-as-uninstalled"></a><span data-ttu-id="6d1cb-121">删除 Web 组件功能后，消息修复和对帐会错误地显示为已卸载</span><span class="sxs-lookup"><span data-stu-id="6d1cb-121">After the Web Components feature is removed, Message Repair and Reconciliation is incorrectly shown as uninstalled</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6d1cb-122">故障现象</span><span class="sxs-lookup"><span data-stu-id="6d1cb-122">Symptom</span></span>  
 <span data-ttu-id="6d1cb-123">删除消息修复和新提交功能的 A4SWIFT Web 组件后，不能卸载、 安装或配置消息修复和对帐功能 （或 A4SWIFT 组件）。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-123">After you remove the Web Components for Message Repair and New Submission feature of A4SWIFT, you cannot uninstall, install, or configure the Message Repair and Reconciliation feature (or A4SWIFT Components).</span></span> <span data-ttu-id="6d1cb-124">如果安装了消息修复和对帐，A4SWIFT 不识别该功能的安装。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-124">If Message Repair and Reconciliation is installed, A4SWIFT does not recognize that the feature is installed.</span></span> <span data-ttu-id="6d1cb-125">如果你尝试安装、 修改或删除消息修复和对帐源中添加/删除程序 （从控制面板中显示），添加/删除程序将指示未安装的功能。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-125">If you attempt to install, modify, or remove Message Repair and Reconciliation from within Add/Remove Programs (displayed from Control Panel), Add/Remove Programs will indicate that the feature is not installed.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="6d1cb-126">可能的原因</span><span class="sxs-lookup"><span data-stu-id="6d1cb-126">Possible Cause</span></span>  
 <span data-ttu-id="6d1cb-127">已从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员组后已安装用于消息修复和新提交功能和消息修复和对帐功能的 Web 组件。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-127">You were removed from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators group after you had installed the Web Components for Message Repair and New Submission feature and the Message Repair and Reconciliation feature.</span></span> <span data-ttu-id="6d1cb-128">如果您然后删除该 Web 组件功能 (您可以执行此操作不是成员的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Administrators 组)、 A4SWIFT 安装程序将删除该消息修复的文件和对帐功能具有依赖关系。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-128">If you then remove the Web Components feature (which you can do without being a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators group), the A4SWIFT setup program will remove files that the Message Repair and Reconciliation feature has a dependency on.</span></span> <span data-ttu-id="6d1cb-129">这些文件包括 ConfigFramework.exe。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-129">These files include ConfigFramework.exe.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="6d1cb-130">解决方案</span><span class="sxs-lookup"><span data-stu-id="6d1cb-130">Solution</span></span>  
 <span data-ttu-id="6d1cb-131">如果遇到此问题，请继续执行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6d1cb-131">If you encounter this problem, proceed as follows:</span></span>  
  
1. <span data-ttu-id="6d1cb-132">在计算机管理窗口中，将您自己添加回[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员组，注销计算机，然后重新登录。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-132">In the Computer Management window, add yourself back into the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrator group, log off the computer, and then log back on.</span></span>  
  
2. <span data-ttu-id="6d1cb-133">重新安装消息修复和新提交的功能的 Web 组件。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-133">Re-install the Web Components for Message Repair and New Submission feature.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6d1cb-134">步骤 2 将 ConfigFramework.exe 添加回 A4SWIFT 安装。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-134">Step 2 adds ConfigFramework.exe back into the A4SWIFT installation.</span></span>  
  
3. <span data-ttu-id="6d1cb-135">重新安装 MRSR 功能。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-135">Re-install the MRSR feature.</span></span>  
  
4. <span data-ttu-id="6d1cb-136">如果你仍不希望 Web 组件用于消息修复和新提交功能，请将其删除。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-136">If you still do not want the Web Components for Message Repair and New Submission feature, remove it.</span></span>  
  
## <a name="repairing-a4swift-to-add-the-service-folder-can-result-in-improper-access-permissions-for-that-folder"></a><span data-ttu-id="6d1cb-137">修复 A4SWIFT 若要添加的服务文件夹可能会导致为该文件夹不正确的访问权限</span><span class="sxs-lookup"><span data-stu-id="6d1cb-137">Repairing A4SWIFT to add the Service folder can result in improper access permissions for that folder</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6d1cb-138">故障现象</span><span class="sxs-lookup"><span data-stu-id="6d1cb-138">Symptom</span></span>  
 <span data-ttu-id="6d1cb-139">如果删除该文件夹 *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Service A4SWIFT 安装程序以添加服务器文件夹的修复功能重新设置 A4SWIFT 正确配置的 A4SWIFT 安装，然后运行安装中，服务文件夹的访问权限不会正确。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-139">If you delete the folder *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Service from a properly configured A4SWIFT installation, and then run the Repair feature of A4SWIFT setup to add the Server folder back in the A4SWIFT installation, the access permissions for the Service folder will not be correct.</span></span> <span data-ttu-id="6d1cb-140">正确的权限是完全控制 A4SWIFT 管理员和读取和执行 A4SWIFT 用户。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-140">The correct permissions are Full Control for A4SWIFT Administrators and Read & Execute for A4SWIFT Users.</span></span>  
  
 <span data-ttu-id="6d1cb-141">如果您的服务文件夹存在时运行的 A4SWIFT 安装程序修复功能也会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-141">This also occurs if you run the Repair feature of A4SWIFT setup when the Service folder exists.</span></span> <span data-ttu-id="6d1cb-142">访问权限，所设置的 A4SWIFT 配置向导中，将被覆盖不正确的值。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-142">The access permissions, as set by the A4SWIFT Configuration Wizard, will be overwritten with incorrect values.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="6d1cb-143">可能的原因</span><span class="sxs-lookup"><span data-stu-id="6d1cb-143">Possible Cause</span></span>  
 <span data-ttu-id="6d1cb-144">安装 Web 组件用于消息修复和新提交功能将添加的服务文件夹。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-144">Installing the Web Components for Message Repair and New Submission feature adds the Service folder.</span></span> <span data-ttu-id="6d1cb-145">如果你删除该文件夹，然后运行要添加 Web 组件的消息修复和新提交 A4SWIFT 安装程序的修复选项，A4SWIFT 安装程序不会无法运行配置向导 (ConfigFramework.exe) 设置文件夹的权限。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-145">If you delete the folder and then run the Repair option of A4SWIFT setup to add the Web Components for Message Repair and New Submission, A4SWIFT setup does not run the configuration wizard (ConfigFramework.exe) to set the permissions for the folder.</span></span> <span data-ttu-id="6d1cb-146">由于已运行配置向导，它是很难再次运行向导以重置配置。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-146">Because the configuration wizard has already been run, it is very difficult to run the wizard again to reset the configuration.</span></span> <span data-ttu-id="6d1cb-147">因此，修复选项将重新创建所有已删除的文件和文件夹，但它将不会正确设置访问权限。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-147">As a result, the Repair option will re-create all deleted files and folders, but it will not set access permissions correctly.</span></span>  
  
 <span data-ttu-id="6d1cb-148">如果该文件夹存在运行修复时，修复过程也将覆盖服务文件夹的权限。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-148">The repair process also overwrites permissions for the Service folder if the folder exists when repair is run.</span></span> <span data-ttu-id="6d1cb-149">作为运行修复之前删除服务文件夹的情况下它会很难运行配置程序来设置权限。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-149">As with the case of deleting the Service folder before running repair, it will be very difficult to run the configuration program to set the permissions.</span></span> <span data-ttu-id="6d1cb-150">在此情况下，，权限将不正确，必须手动将它们设置。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-150">In this instance, as well, the permissions will be incorrect and you will have to manually set them.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="6d1cb-151">解决方案</span><span class="sxs-lookup"><span data-stu-id="6d1cb-151">Solution</span></span>  
 <span data-ttu-id="6d1cb-152">如果遇到此问题，手动设置的服务文件夹的以下访问权限：</span><span class="sxs-lookup"><span data-stu-id="6d1cb-152">If you encounter this problem, manually set the following access permissions for the Service folder:</span></span>  
  
|<span data-ttu-id="6d1cb-153">组或用户名</span><span class="sxs-lookup"><span data-stu-id="6d1cb-153">Group or User Name</span></span>|<span data-ttu-id="6d1cb-154">权限</span><span class="sxs-lookup"><span data-stu-id="6d1cb-154">Permission</span></span>|  
|------------------------|----------------|  
|<span data-ttu-id="6d1cb-155">A4SWIFT 管理员</span><span class="sxs-lookup"><span data-stu-id="6d1cb-155">A4SWIFT Administrators</span></span>|<span data-ttu-id="6d1cb-156">完全控制</span><span class="sxs-lookup"><span data-stu-id="6d1cb-156">Full Control</span></span>|  
|<span data-ttu-id="6d1cb-157">A4SWIFT 用户</span><span class="sxs-lookup"><span data-stu-id="6d1cb-157">A4SWIFT Users</span></span>|<span data-ttu-id="6d1cb-158">读取及执行</span><span class="sxs-lookup"><span data-stu-id="6d1cb-158">Read & Execute</span></span>|  
  
 <span data-ttu-id="6d1cb-159">若要设置这些权限，请继续阅读，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6d1cb-159">To set these permissions, proceed as follows:</span></span>  
  
 <span data-ttu-id="6d1cb-160">在中[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，转到 *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Service。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-160">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Service.</span></span>  
  
1.  <span data-ttu-id="6d1cb-161">右键单击服务文件夹，单击**属性**，然后单击**安全**选项卡。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-161">Right-click the Service folder, click **Properties**, and then click the **Security** tab.</span></span>  
  
2.  <span data-ttu-id="6d1cb-162">在组或用户名称窗格的服务属性对话框中，单击**外**，输入 ***\<服务器名称\>* \A4SWIFT 管理员**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="6d1cb-162">In the Group or user names pane of the Service Properties dialog box, click **Add**, enter ***\<server name\>*\A4SWIFT Administrators**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6d1cb-163">如果 A4SWIFT Administrators 组的域组，请输入 ***\<域名\>* \A4SWIFT 管理员**。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-163">If the A4SWIFT Administrators group is a domain group, enter ***\<domain name\>*\A4SWIFT Administrators**.</span></span>  
  
3.  <span data-ttu-id="6d1cb-164">重复步骤 2 ***\<服务器名称\>* \A4SWIFT 用户**，或 **\<*域名*\>\A4SWIFT 用户**如果A4SWIFT 用户组是域组。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-164">Repeat step 2 for ***\<server name\>*\A4SWIFT Users**, or **\<*domain name*\>\A4SWIFT Users** if the A4SWIFT Users group is a domain group.</span></span>  
  
4.  <span data-ttu-id="6d1cb-165">在组或用户名称窗格中，选择**A4SWIFT 管理员**。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-165">In the Group or user names pane, select **A4SWIFT Administrators**.</span></span> <span data-ttu-id="6d1cb-166">在权限窗格中，选择**允许**有关**完全控制**。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-166">In the Permissions pane, select **Allow** for **Full Control**.</span></span>  
  
5.  <span data-ttu-id="6d1cb-167">在组或用户名称窗格中，选择**A4SWIFT 用户**。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-167">In the Group or user names pane, select **A4SWIFT Users**.</span></span> <span data-ttu-id="6d1cb-168">在权限窗格中，单击**允许**有关**读取和执行**，**列出文件夹内容**，以及**读取**。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-168">In the Permissions pane, click **Allow** for **Read & Execute**, **List Folder Contents**, and **Read**.</span></span>  
  
6.  <span data-ttu-id="6d1cb-169">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-169">Click **OK**.</span></span>  
  
## <a name="upgrade-results-in-a-side-by-side-installation-of-two-versions-of-a4swift"></a><span data-ttu-id="6d1cb-170">在两个版本的 A4SWIFT 通过并行安装的升级结果</span><span class="sxs-lookup"><span data-stu-id="6d1cb-170">Upgrade results in a side-by-side installation of two versions of A4SWIFT</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6d1cb-171">故障现象</span><span class="sxs-lookup"><span data-stu-id="6d1cb-171">Symptom</span></span>  
 <span data-ttu-id="6d1cb-172">当你尝试升级到[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]，以前版本的 A4SWIFT 可能不会完全删除。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-172">When you attempt to upgrade to [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)], previous versions of A4SWIFT may not be fully removed.</span></span> <span data-ttu-id="6d1cb-173">如果从控制面板运行添加/删除程序，当前和以前的版本可能会显示当前安装的程序的列表。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-173">If you run Add/Remove Programs from the Control Panel, the list of Currently Installed Programs might show the current and the previous versions.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="6d1cb-174">可能的原因</span><span class="sxs-lookup"><span data-stu-id="6d1cb-174">Possible Cause</span></span>  
 <span data-ttu-id="6d1cb-175">任何以下情况可能会导致上述发生：</span><span class="sxs-lookup"><span data-stu-id="6d1cb-175">Any of the following conditions can cause the above to occur:</span></span>  
  
- <span data-ttu-id="6d1cb-176">尝试升级的用户不是成员的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-176">The user attempting to upgrade is not a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
- <span data-ttu-id="6d1cb-177">[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] (MSSQLSERVER) 服务已停止。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-177">The [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] service (MSSQLSERVER) is stopped.</span></span>  
  
- <span data-ttu-id="6d1cb-178">执行无提示升级 using **setup.exe /addlocal**命令。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-178">You performed a silent upgrade using the **setup.exe /addlocal** command.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="6d1cb-179">解决方案</span><span class="sxs-lookup"><span data-stu-id="6d1cb-179">Solution</span></span>  
 <span data-ttu-id="6d1cb-180">若要阻止通过并行安装的[!INCLUDE[btaA4SWIFToldest](../../includes/btaa4swiftoldest-md.md)]并[!INCLUDE[btaA4SWIFT2.3abbrev](../../includes/btaa4swift2-3abbrev-md.md)]发生在升级过程中，确保你 （登录的用户） 的成员[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员组，并且[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]启动服务 (MSSQLSERVER)。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-180">To prevent a side-by-side installation of [!INCLUDE[btaA4SWIFToldest](../../includes/btaa4swiftoldest-md.md)] and [!INCLUDE[btaA4SWIFT2.3abbrev](../../includes/btaa4swift2-3abbrev-md.md)] occurring during upgrade, ensure that you (the logged-on user) are a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators group, and that the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] service (MSSQLSERVER) is started.</span></span>  
  
 <span data-ttu-id="6d1cb-181">如果您得到的通过并行安装[!INCLUDE[btaA4SWIFToldest](../../includes/btaa4swiftoldest-md.md)]或[!INCLUDE[btaA4SWIFT2.1abbrev](../../includes/btaa4swift2-1abbrev-md.md)]和[!INCLUDE[btaA4SWIFT2.3abbrev](../../includes/btaa4swift2-3abbrev-md.md)]，继续操作，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6d1cb-181">If you end up with a side-by-side installation of [!INCLUDE[btaA4SWIFToldest](../../includes/btaa4swiftoldest-md.md)] or [!INCLUDE[btaA4SWIFT2.1abbrev](../../includes/btaa4swift2-1abbrev-md.md)] and [!INCLUDE[btaA4SWIFT2.3abbrev](../../includes/btaa4swift2-3abbrev-md.md)], proceed as follows:</span></span>  
  
1. <span data-ttu-id="6d1cb-182">备份 SWIFT 消息文件夹中的数据。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-182">Back up the data in the SWIFT Messages folder.</span></span>  
  
2. <span data-ttu-id="6d1cb-183">登录到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为 BTS 管理员的成员的组，并确保 MSSQLSERVER 服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-183">Log on to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] as a member of the BTS Administrators group, and ensure that the MSSQLSERVER service is running.</span></span>  
  
3. <span data-ttu-id="6d1cb-184">删除以前版本的 A4SWIFT。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-184">Remove the previous version of A4SWIFT.</span></span>  
  
4. <span data-ttu-id="6d1cb-185">再次升级到 A4SWIFT 的最新版本。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-185">Upgrade to the latest version of A4SWIFT again.</span></span> <span data-ttu-id="6d1cb-186">这一次将进行升级，并且将创建不通过并行安装。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-186">This time the upgrade will work, and no side-by-side installation will be created.</span></span>  
  
5. <span data-ttu-id="6d1cb-187">使用 BizTalk 部署实用工具，手动取消部署 Microsoft。Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll，然后从 A4SWIFT 安装位置的程序集文件夹重新部署。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-187">Using the BizTalk Deployment Utility, manually undeploy Microsoft .Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll, and then redeploy it from the Assemblies folder of your A4SWIFT installation location.</span></span> <span data-ttu-id="6d1cb-188">有关此工具的详细信息，请参阅[BRE 部署实用工具](../../adapters-and-accelerators/accelerator-swift/bre-deployment-utility.md)。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-188">For more information about this tool, see [BRE Deployment Utility](../../adapters-and-accelerators/accelerator-swift/bre-deployment-utility.md).</span></span>  
  
## <a name="the-uninstall-or-upgrade-process-may-not-complete-correctly-if-you-do-not-restart-when-prompted"></a><span data-ttu-id="6d1cb-189">如果你不重新启动系统提示时，在卸载或升级过程可能无法正确完成</span><span class="sxs-lookup"><span data-stu-id="6d1cb-189">The uninstall or upgrade process may not complete correctly if you do not restart when prompted</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6d1cb-190">故障现象</span><span class="sxs-lookup"><span data-stu-id="6d1cb-190">Symptom</span></span>  
 <span data-ttu-id="6d1cb-191">卸载或升级过程未正确完成。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-191">Uninstall or upgrade processes do not complete correctly.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="6d1cb-192">可能的原因</span><span class="sxs-lookup"><span data-stu-id="6d1cb-192">Possible Cause</span></span>  
 <span data-ttu-id="6d1cb-193">如果不具有取消部署一个项目引用现有的已部署程序集，可能会收到一个提示，指示您必须重新启动系统，A4SWIFT 配置更改才能生效。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-193">If you have not undeployed a project that references an existing deployed assembly, you may receive a prompt indicating that you must restart your system for A4SWIFT configuration changes to take effect.</span></span> <span data-ttu-id="6d1cb-194">如果不单击**是**以立即重新启动，在全局程序集缓存中删除已分配某些程序集可能不会删除，从而导致额外的卸载或升级进程，以正确完成。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-194">If you do not click **Yes** to restart immediately, some assemblies that were assigned for removal in the global assembly cache may not be removed, causing additional uninstall or upgrade processes to not complete correctly.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="6d1cb-195">解决方案</span><span class="sxs-lookup"><span data-stu-id="6d1cb-195">Solution</span></span>  
 <span data-ttu-id="6d1cb-196">取消部署任何项目都引用一个现有的已部署程序集，然后再次运行卸载或升级过程。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-196">Undeploy any project that references an existing deployed assembly, and then run the uninstall or upgrade process again.</span></span>  
  
## <a name="if-the-iis-admin-service-is-stopped-during-setup-you-must-reconfigure-the-webservice-feature"></a><span data-ttu-id="6d1cb-197">如果在安装过程已停止 IIS 管理服务，则必须重新配置 web 服务功能</span><span class="sxs-lookup"><span data-stu-id="6d1cb-197">If the IIS Admin Service is stopped during setup, you must reconfigure the WebService feature</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6d1cb-198">故障现象</span><span class="sxs-lookup"><span data-stu-id="6d1cb-198">Symptom</span></span>  
 <span data-ttu-id="6d1cb-199">[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置向导不会正确配置的 web 服务功能。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-199">The [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration Wizard does not configure the WebService feature correctly.</span></span> <span data-ttu-id="6d1cb-200">您收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="6d1cb-200">You receive the following error:</span></span>  
  
 <span data-ttu-id="6d1cb-201">"无法创建 MRSR 项目： 无法连接到远程服务器。"</span><span class="sxs-lookup"><span data-stu-id="6d1cb-201">"Unable to create MRSR artifacts: Unable to connect to the remote server."</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="6d1cb-202">可能的原因</span><span class="sxs-lookup"><span data-stu-id="6d1cb-202">Possible Cause</span></span>  
 <span data-ttu-id="6d1cb-203">IIS 管理服务已停止运行时[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置向导。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-203">The IIS Admin Service was stopped when you ran the [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration Wizard.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="6d1cb-204">解决方案</span><span class="sxs-lookup"><span data-stu-id="6d1cb-204">Solution</span></span>  
 <span data-ttu-id="6d1cb-205">若要成功完成配置过程，请继续阅读，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6d1cb-205">To complete the configuration process successfully, proceed as follows:</span></span>  
  
1. <span data-ttu-id="6d1cb-206">关闭[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置控制台。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-206">Close the [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration console.</span></span>  
  
2. <span data-ttu-id="6d1cb-207">重新启动 IIS 管理服务。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-207">Restart the IIS Admin Service.</span></span>  
  
3. <span data-ttu-id="6d1cb-208">执行 *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Configuration.exe。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-208">Execute *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Configuration.exe.</span></span>  
  
4. <span data-ttu-id="6d1cb-209">在中[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置控制台中，选择**取消对功能**，然后选择**WebService**。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-209">In the [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration console, select **Unconfigure Features** and then select **WebService**.</span></span>  
  
5. <span data-ttu-id="6d1cb-210">请确保配置控制台中的 web 服务功能的状态都显示为未配置。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-210">Ensure that the status of the WebService feature in the Configuration console is shown as unconfigured.</span></span>  
  
6. <span data-ttu-id="6d1cb-211">选择**应用配置**。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-211">Select **Apply Configuration**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6d1cb-212">A4SWIFT 配置向导现在将正确配置的 web 服务功能。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-212">The A4SWIFT Configuration Wizard will now configure the WebService feature correctly.</span></span>  
  
## <a name="a4swift-configuration-will-fail-if-the-biztalkserverapplication-host-was-not-created-in-biztalk-server-configuration"></a><span data-ttu-id="6d1cb-213">如果在 BizTalk Server 配置中未创建 BizTalkServerApplication 主机 A4SWIFT 配置将失败</span><span class="sxs-lookup"><span data-stu-id="6d1cb-213">A4SWIFT configuration will fail if the BizTalkServerApplication host was not created in BizTalk Server configuration</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6d1cb-214">故障现象</span><span class="sxs-lookup"><span data-stu-id="6d1cb-214">Symptom</span></span>  
 <span data-ttu-id="6d1cb-215">[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]配置向导不会正确配置的 web 服务功能。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-215">The [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration Wizard does not configure the WebService feature correctly.</span></span> <span data-ttu-id="6d1cb-216">您收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="6d1cb-216">You receive the following error:</span></span>  
  
 <span data-ttu-id="6d1cb-217">"无法创建 MRSR 项目： 对象引用未设置为某个对象的实例。"</span><span class="sxs-lookup"><span data-stu-id="6d1cb-217">"Unable to create MRSR artifacts: Object reference not set to an instance of an object."</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="6d1cb-218">可能的原因</span><span class="sxs-lookup"><span data-stu-id="6d1cb-218">Possible Cause</span></span>  
 <span data-ttu-id="6d1cb-219">BizTalk Server 运行时配置过程中未创建进程内主机和主机实例。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-219">An In-Process Host and a Host Instance were not created during BizTalk Server Runtime configuration.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="6d1cb-220">解决方案</span><span class="sxs-lookup"><span data-stu-id="6d1cb-220">Solution</span></span>  
 <span data-ttu-id="6d1cb-221">若要修复的 A4SWIFT 配置，请继续阅读，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6d1cb-221">To repair the A4SWIFT configuration, proceed as follows:</span></span>  
  
- <span data-ttu-id="6d1cb-222">在 BizTalk Server 管理中创建一个主机。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-222">Create a host in BizTalk Server Administration.</span></span> <span data-ttu-id="6d1cb-223">没有必要现在具有正在运行的实例。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-223">There is no need to have a running instance now.</span></span>  
  
- <span data-ttu-id="6d1cb-224">在运行 RepairBAS 工具 *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\SDK\Tools 文件夹的 A4SWIFT 安装。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-224">Run the RepairBAS tool in the *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\SDK\Tools folder of the A4SWIFT installation.</span></span>  
  
  <span data-ttu-id="6d1cb-225">为此，请继续操作，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6d1cb-225">To do so, proceed as follows:</span></span>  
  
1.  <span data-ttu-id="6d1cb-226">启动**BizTalk Server 管理**控制台。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-226">Start **BizTalk Server Administration** console.</span></span>  
  
2.  <span data-ttu-id="6d1cb-227">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，然后展开**BizTalk 组**，然后展开**平台设置。**</span><span class="sxs-lookup"><span data-stu-id="6d1cb-227">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, then expand **BizTalk Group**, and then expand **Platform Settings.**</span></span>  
  
3.  <span data-ttu-id="6d1cb-228">右键单击**主机**，依次指向**新建**，然后选择**主机**。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-228">Right-click **Hosts**, point to **New**, and then select **Host**.</span></span>  
  
4.  <span data-ttu-id="6d1cb-229">在主机属性屏幕中，在常规窗格中，输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="6d1cb-229">In the Host Properties screen, in the General pane, enter the following:</span></span>  
  
    -   <span data-ttu-id="6d1cb-230">主机名： **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="6d1cb-230">Host name: **BizTalkServerApplication**</span></span>  
  
    -   <span data-ttu-id="6d1cb-231">类型：**进程内**</span><span class="sxs-lookup"><span data-stu-id="6d1cb-231">Type: **In-Process**</span></span>  
  
    -   <span data-ttu-id="6d1cb-232">Windows 组：  **\<*域*\>\BizTalk 应用程序用户**（或在用于运行 BizTalk 进程内的 BizTalk Server 配置过程中设置的帐户应用程序）</span><span class="sxs-lookup"><span data-stu-id="6d1cb-232">Windows group: **\<*domain*\>\BizTalk Application Users** (or the account that you set up during BizTalk Server configuration for running BizTalk In-Process applications)</span></span>  
  
    -   <span data-ttu-id="6d1cb-233">在选项部分中，选择这两**允许主机跟踪**并**组中将此默认主机**。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-233">In the Options section, select both **Allow Host Tracking** and **Make this the default host in the group**.</span></span>  
  
5.  <span data-ttu-id="6d1cb-234">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-234">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="6d1cb-235">单击**启动**，然后单击运行。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-235">Click **Start** and then click Run.</span></span> <span data-ttu-id="6d1cb-236">类型**cmd** ，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-236">Type **cmd** and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="6d1cb-237">在命令提示符处，导航到 * %programfiles%***\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools**。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-237">At the command prompt, navigate to *%programfiles%***\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools**.</span></span>  
  
8.  <span data-ttu-id="6d1cb-238">类型**RepairBAS.exe** ，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-238">Type **RepairBAS.exe** and then press **Enter**.</span></span>  
  
## <a name="you-must-change-the-bre-deployment-configuration-file-when-running-the-bre-deployment-utility-on-a-64-bit-computer"></a><span data-ttu-id="6d1cb-239">在 64 位计算机上运行 BRE 部署实用工具时，必须更改 BRE 部署配置文件</span><span class="sxs-lookup"><span data-stu-id="6d1cb-239">You must change the BRE Deployment configuration file when running the BRE Deployment Utility on a 64-bit computer</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6d1cb-240">故障现象</span><span class="sxs-lookup"><span data-stu-id="6d1cb-240">Symptom</span></span>  
 <span data-ttu-id="6d1cb-241">BRE 部署实用工具不会无法正常运行时在 64 位计算机上或在非默认的目录 （而不是 C:\Program Files\Microsoft BizTalk Accelerator for SWIFT) 的 32 位计算机上。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-241">The BRE Deployment Utility does not work correctly when you run it on a 64-bit computer or in a non-default directory (other than C:\Program Files\Microsoft BizTalk Accelerator for SWIFT) on a 32-bit computer.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="6d1cb-242">可能的原因</span><span class="sxs-lookup"><span data-stu-id="6d1cb-242">Possible Cause</span></span>  
 <span data-ttu-id="6d1cb-243">BRE 部署实用工具将无法正常工作之前更改中的 BREDeployment.exe.config 文件中的路径\<驱动器\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-243">The BRE Deployment Utility will not work correctly until you change the paths in the BREDeployment.exe.config file located in the \<drive\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools folder.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="6d1cb-244">解决方案</span><span class="sxs-lookup"><span data-stu-id="6d1cb-244">Solution</span></span>  
 <span data-ttu-id="6d1cb-245">在记事本中，打开 BREDeployment.exe.config 并更改的基本策略、 架构和词汇目录的文件夹中更新该实用程序的配置。</span><span class="sxs-lookup"><span data-stu-id="6d1cb-245">Update the utility's configuration by opening BREDeployment.exe.config in Notepad, and changing the folders for the base policies, schemas, and vocabulary directories.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d1cb-246">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d1cb-246">See Also</span></span>  
 [<span data-ttu-id="6d1cb-247">疑难解答：问题和解决方法</span><span class="sxs-lookup"><span data-stu-id="6d1cb-247">Troubleshooting: Issues and Resolutions</span></span>](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)