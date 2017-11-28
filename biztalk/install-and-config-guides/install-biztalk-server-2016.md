---
title: "安装 BizTalk Server 2016 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f5ac913-0734-45b2-8e25-1db146d81858
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f89aa7599040a2cc6c50f11b70c2751fcf2df1ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="install-biztalk-server-2016"></a><span data-ttu-id="82660-102">安装 BizTalk Server 2016</span><span class="sxs-lookup"><span data-stu-id="82660-102">Install BizTalk Server 2016</span></span>
<span data-ttu-id="82660-103">在单台计算机上安装 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="82660-103">Install BizTalk Server on a single computer.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="82660-104">开始操作之前</span><span class="sxs-lookup"><span data-stu-id="82660-104">Before you get started</span></span>

* <span data-ttu-id="82660-105">**系统管理员** – 安装 SQL Server 时，安装程序会自动向登录的帐户授予系统管理员权限。</span><span class="sxs-lookup"><span data-stu-id="82660-105">**System Administrator** – When you install SQL Server, setup automatically grants your signed-in account System Administrator rights.</span></span> <span data-ttu-id="82660-106">由于安装 BizTalk Server 还需要这些权限，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="82660-106">Since these rights are also required to install BizTalk Server, do one of the following:</span></span>
  * <span data-ttu-id="82660-107">使用在安装 SQL Server 时所用的同一帐户。</span><span class="sxs-lookup"><span data-stu-id="82660-107">Use the same account you used when you installed SQL Server.</span></span>
  * <span data-ttu-id="82660-108">向登录的帐户授予系统管理员权限。</span><span class="sxs-lookup"><span data-stu-id="82660-108">Give the signed-in account System Administrator rights.</span></span>
  * <span data-ttu-id="82660-109">确定登录的帐户是本地管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="82660-109">Confirm the signed-in account is a member of the local administrators group.</span></span>
* <span data-ttu-id="82660-110">**帐户名** – 应尽可能使用默认帐户名。</span><span class="sxs-lookup"><span data-stu-id="82660-110">**Account names** – Use the default account names whenever possible.</span></span> <span data-ttu-id="82660-111">BizTalk Server 安装程序会自动输入默认帐户。</span><span class="sxs-lookup"><span data-stu-id="82660-111">The BizTalk Server setup automatically enters the default accounts.</span></span> <span data-ttu-id="82660-112">如果域中存在多个 BizTalk Server 组，应更改帐户名，以避免冲突。</span><span class="sxs-lookup"><span data-stu-id="82660-112">If there are multiple BizTalk Server groups within the Domain, change the account names to avoid conflicts.</span></span> <span data-ttu-id="82660-113">如果需要更改名称，BizTalk Server 仅支持 *NetBIOS 域名/用户*格式的服务帐户和 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="82660-113">If you change the names, BizTalk Server supports only *NetBIOS domain name\user* for service accounts and Windows groups.</span></span>
* <span data-ttu-id="82660-114">**带有 BAM 管理 Web Service 的帐户名** – BizTalk Server 不支持 BAM 管理 Web Service 用户的内置帐户或无密码的帐户。</span><span class="sxs-lookup"><span data-stu-id="82660-114">**Account names with BAM Management Web Service** – BizTalk Server does not support built-in accounts or accounts without passwords for the BAM Management Web Service User.</span></span> <span data-ttu-id="82660-115">Web 服务会访问 BizTalk Server 数据库，而此类帐户可能带来安全威胁。</span><span class="sxs-lookup"><span data-stu-id="82660-115">The web service accesses the BizTalk Server database and these accounts may suggest a security threat.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="82660-116">使用这些类型的帐户配置 BizTalk Server 可能会成功，但是 BAM 管理 Web Service 会发生故障。</span><span class="sxs-lookup"><span data-stu-id="82660-116">Configuring BizTalk Server with these typs of accounts may succeed, but the BAM Management Web Service fails.</span></span> <span data-ttu-id="82660-117">可以对 BAM 应用程序池使用内置帐户或无密码的帐户。</span><span class="sxs-lookup"><span data-stu-id="82660-117">Built-in accounts or accounts without passwords can be used for the BAM Application pool.</span></span>

* <span data-ttu-id="82660-118">**BizTalk 程序集查看器** – 在 64 位平台上不受支持。</span><span class="sxs-lookup"><span data-stu-id="82660-118">**BizTalk Assembly Viewer** – Not supported on a 64-bit platform.</span></span> 
* <span data-ttu-id="82660-119">**安装和卸载**卸载 BizTalk Server 需要手动删除 BizTalk Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="82660-119">**Install and Uninstall** – Uninstalling BizTalk Server requires manually deleting the BizTalk Server databases.</span></span> <span data-ttu-id="82660-120">如果以开发人员或评估人员身份安装 BizTalk Server，请使用虚拟机。</span><span class="sxs-lookup"><span data-stu-id="82660-120">If you are installing BizTalk Server as a developer or evaluator, use a virtual machine.</span></span> <span data-ttu-id="82660-121">如果需要进行重新安装，可以轻松回滚虚拟机，而无需卸载和删除数据库。</span><span class="sxs-lookup"><span data-stu-id="82660-121">If you need to reinstall, you can easily roll back the virtual machine without having to uninstall and delete the databases.</span></span>
* <span data-ttu-id="82660-122">**32 位和 64 位计算机** – 在 32 位与 64 位计算机上安装 BizTalk Server 之间的差异较少。</span><span class="sxs-lookup"><span data-stu-id="82660-122">**32-bit and 64-bit computers** – There are few differences when installing BizTalk Server on 32-bit or 64-bit computer.</span></span> <span data-ttu-id="82660-123">安装和配置对 32 位和 64 位计算机均适用。</span><span class="sxs-lookup"><span data-stu-id="82660-123">The installation and configuration covers 32-bit and 64-bit computers.</span></span> <span data-ttu-id="82660-124">将介绍两者之间的差别。</span><span class="sxs-lookup"><span data-stu-id="82660-124">Any differences are noted.</span></span>
* <span data-ttu-id="82660-125">**工作组** - 支持在单台计算机上的工作组环境中安装和配置 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="82660-125">**Workgroups** - Installing and configuring BizTalk Server in the workgroup environment on a single computer is supported.</span></span> <span data-ttu-id="82660-126">SQL Server 和 BizTalk Server 的功能和组件在同一计算机上安装和配置。</span><span class="sxs-lookup"><span data-stu-id="82660-126">SQL Server and BizTalk Server features and components are installed and configured on the same computer.</span></span>


## <a name="install-biztalk-server"></a><span data-ttu-id="82660-127">安装 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="82660-127">Install BizTalk Server</span></span>
1. <span data-ttu-id="82660-128">关闭所有打开的程序。</span><span class="sxs-lookup"><span data-stu-id="82660-128">Close any open programs.</span></span> <span data-ttu-id="82660-129">以管理员身份运行 BizTalk Server 安装程序。</span><span class="sxs-lookup"><span data-stu-id="82660-129">Run the BizTalk Server setup as an Administrator.</span></span>
2. <span data-ttu-id="82660-130">选择“安装 Microsoft BizTalk Server 2016”。</span><span class="sxs-lookup"><span data-stu-id="82660-130">Select **Install Microsoft BizTalk Server 2016**.</span></span>
3. <span data-ttu-id="82660-131">输入“用户名”、“组织”和产品密钥。</span><span class="sxs-lookup"><span data-stu-id="82660-131">Enter your **User name**, your **Organization**, and your product key.</span></span> <span data-ttu-id="82660-132">选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="82660-132">Select **Next**.</span></span>
4. <span data-ttu-id="82660-133">接受许可协议，然后选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="82660-133">Accept the license agreement, and select **Next**.</span></span>
5. <span data-ttu-id="82660-134">选择参与客户体验改善计划，然后选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="82660-134">Choose to participate in the Customer Experience Improvement Program, and select **Next**.</span></span>
6. <span data-ttu-id="82660-135">选择想要安装的组件：</span><span class="sxs-lookup"><span data-stu-id="82660-135">Choose which components you want to install:</span></span>

    ![bts2016install_components](../install-and-config-guides/media/bts2016install-components.gif)
  
    <span data-ttu-id="82660-137">请务必选择“其他软件”。</span><span class="sxs-lookup"><span data-stu-id="82660-137">Be sure to select **Additional Software**.</span></span> <span data-ttu-id="82660-138">还可以更改安装位置：</span><span class="sxs-lookup"><span data-stu-id="82660-138">You can also change the installation location:</span></span> 
  
    ![bts2016install_additional](../install-and-config-guides/media/bts2016install-additional.gif)

    <span data-ttu-id="82660-140">选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="82660-140">Select **Next**.</span></span>   
  
 7. <span data-ttu-id="82660-141">具体取决于选择的组件，可能有一些其他系统必备组件，如 ADOMD.NET。</span><span class="sxs-lookup"><span data-stu-id="82660-141">Depending on the components you choose, there may be some additional prerequisites, such as ADOMD.NET.</span></span> <span data-ttu-id="82660-142">安装程序可自动安装所有可再发行的必备组件。</span><span class="sxs-lookup"><span data-stu-id="82660-142">The setup can install all the redistributable prerequisites automatically for you.</span></span> <span data-ttu-id="82660-143">您的选择包括: </span><span class="sxs-lookup"><span data-stu-id="82660-143">Your options include:</span></span>
* <span data-ttu-id="82660-144">**手动安装可再发行必备组件**：此选项会关闭安装向导，以便可以手动安装缺少的必备组件。</span><span class="sxs-lookup"><span data-stu-id="82660-144">**Manually install the redistributable prerequisites** : The installation wizard closes so you can manually install the missing prerequisites.</span></span>
* <span data-ttu-id="82660-145">**自动从 Web 安装可再发行的必备组件**：默认选项。</span><span class="sxs-lookup"><span data-stu-id="82660-145">**Automatically install the redistributable prerequisites from the web** : Default.</span></span> <span data-ttu-id="82660-146">需要 Internet 访问权限。</span><span class="sxs-lookup"><span data-stu-id="82660-146">Requires internet access.</span></span>
* <span data-ttu-id="82660-147">**下载可再发行的必备组件 CAB 文件**：下载 CAB 文件，以便稍后进行安装。</span><span class="sxs-lookup"><span data-stu-id="82660-147">**Download the redistributable prerequisites CAB file** : Downloads a CAB file, which you can install later.</span></span>
* <span data-ttu-id="82660-148">**自动从 CAB 文件安装可再发行的必备组件**：如果之前已下载 CAB 文件，则选择此选项可使用这些 CAB 文件。</span><span class="sxs-lookup"><span data-stu-id="82660-148">**Automatically install the redistributable prerequisites from a CAB file**: If you previously downloaded the CAB files, you can select this option to use those CAB files.</span></span> 

  <span data-ttu-id="82660-149">选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="82660-149">Select **Next**.</span></span>
  
8. <span data-ttu-id="82660-150">查看摘要页。</span><span class="sxs-lookup"><span data-stu-id="82660-150">Review the summary page.</span></span> <span data-ttu-id="82660-151">若要进行任何更改，请选择“返回”以选中或取消选中任何组件。</span><span class="sxs-lookup"><span data-stu-id="82660-151">To make any changes, select **Back** to check or uncheck any components.</span></span> 

     <span data-ttu-id="82660-152">若要使系统在重新启动后自动登录，请选择“设置”，然后输入登录帐户。</span><span class="sxs-lookup"><span data-stu-id="82660-152">To enable auto-logon after a system reboot, select **Set**, and enter the sign-in account.</span></span> <span data-ttu-id="82660-153">仅在 BizTalk 安装程序中启用此设置。</span><span class="sxs-lookup"><span data-stu-id="82660-153">This is only enabled during the BizTalk setup.</span></span> <span data-ttu-id="82660-154">安装完成后，会禁用此设置。</span><span class="sxs-lookup"><span data-stu-id="82660-154">When setup is complete, this setting is disabled.</span></span> 

    <span data-ttu-id="82660-155">选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="82660-155">Select **Install**.</span></span>
  
9. <span data-ttu-id="82660-156">若要立即配置 BizTalk，请选中“启动 BizTalk Server 配置”。</span><span class="sxs-lookup"><span data-stu-id="82660-156">To configure BizTalk now, check **Launch BizTalk Server Configuration**.</span></span> <span data-ttu-id="82660-157">如果不想立即配置 BizTalk，则取消选中此选项，然后选择“完成”关闭安装向导。</span><span class="sxs-lookup"><span data-stu-id="82660-157">If you don't want to configure BizTalk now, then uncheck this option, and select **Finish** to close the installation wizard.</span></span> 

<span data-ttu-id="82660-158">安装日志文件生成于临时文件夹，如下所示：`C:\Users\*username*\AppData\Local\Setup(011217 xxxxxx).htm`</span><span class="sxs-lookup"><span data-stu-id="82660-158">A setup log file is generated in a temp folder, similar to: `C:\Users\*username*\AppData\Local\Setup(011217 xxxxxx).htm`</span></span>
  
## <a name="check-the-installation"></a><span data-ttu-id="82660-159">检查安装</span><span class="sxs-lookup"><span data-stu-id="82660-159">Check the installation</span></span>

* <span data-ttu-id="82660-160">“程序和功能”中会列出 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="82660-160">BizTalk Server is listed in **Programs and Features**.</span></span>
* <span data-ttu-id="82660-161">`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0` 注册表项列出了 BizTalk Server 版本、安装路径、版本和其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="82660-161">The `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0` registry key lists the BizTalk Server version, the install path, the edition, and other details.</span></span>
* <span data-ttu-id="82660-162">应用中列出了 BizTalk Server 管理、配置和其他组件。</span><span class="sxs-lookup"><span data-stu-id="82660-162">BizTalk Server Administration, Configuration, and other components are listed in your Apps.</span></span> 

## <a name="next-step"></a><span data-ttu-id="82660-163">下一步</span><span class="sxs-lookup"><span data-stu-id="82660-163">Next step</span></span>
[<span data-ttu-id="82660-164">配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="82660-164">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)