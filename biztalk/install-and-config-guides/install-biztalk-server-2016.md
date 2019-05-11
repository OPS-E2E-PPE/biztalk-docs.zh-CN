---
title: 安装 BizTalk Server 2016 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f5ac913-0734-45b2-8e25-1db146d81858
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97ea71a309d5073f0c1a00adeff5a94ea62cb958
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266218"
---
# <a name="install-biztalk-server-2016"></a><span data-ttu-id="4e764-102">安装 BizTalk Server 2016</span><span class="sxs-lookup"><span data-stu-id="4e764-102">Install BizTalk Server 2016</span></span>
<span data-ttu-id="4e764-103">一台计算机上安装 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="4e764-103">Install BizTalk Server on a single computer.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="4e764-104">准备工作</span><span class="sxs-lookup"><span data-stu-id="4e764-104">Before you get started</span></span>

* <span data-ttu-id="4e764-105">**系统管理员**： 当你安装 SQL Server 安装程序会自动授予你已登录的帐户系统管理员权限。</span><span class="sxs-lookup"><span data-stu-id="4e764-105">**System Administrator** – When you install SQL Server, setup automatically grants your signed-in account System Administrator rights.</span></span> <span data-ttu-id="4e764-106">由于安装 BizTalk Server 时，还需要执行这些权限，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4e764-106">Since these rights are also required to install BizTalk Server, do one of the following:</span></span>
  * <span data-ttu-id="4e764-107">使用安装 SQL Server 时所用的相同帐户。</span><span class="sxs-lookup"><span data-stu-id="4e764-107">Use the same account you used when you installed SQL Server.</span></span>
  * <span data-ttu-id="4e764-108">向登录的帐户授予系统管理员权限。</span><span class="sxs-lookup"><span data-stu-id="4e764-108">Give the signed-in account System Administrator rights.</span></span>
  * <span data-ttu-id="4e764-109">确认登录的帐户是本地管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="4e764-109">Confirm the signed-in account is a member of the local administrators group.</span></span>
* <span data-ttu-id="4e764-110">**帐户名**– 使用默认帐户名，只要有可能。</span><span class="sxs-lookup"><span data-stu-id="4e764-110">**Account names** – Use the default account names whenever possible.</span></span> <span data-ttu-id="4e764-111">BizTalk Server 安装程序会自动输入默认帐户。</span><span class="sxs-lookup"><span data-stu-id="4e764-111">The BizTalk Server setup automatically enters the default accounts.</span></span> <span data-ttu-id="4e764-112">如果在域中的多个 BizTalk Server 组，更改帐户名，以避免冲突。</span><span class="sxs-lookup"><span data-stu-id="4e764-112">If there are multiple BizTalk Server groups within the Domain, change the account names to avoid conflicts.</span></span> <span data-ttu-id="4e764-113">如果更改名称，BizTalk Server 仅支持*NetBIOS 域 name\user*的服务帐户和 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="4e764-113">If you change the names, BizTalk Server supports only *NetBIOS domain name\user* for service accounts and Windows groups.</span></span>
* <span data-ttu-id="4e764-114">**带有 BAM 管理 Web 服务的帐户名称**– BizTalk Server 不支持内置帐户或无密码的帐户为 BAM 管理 Web 服务用户。</span><span class="sxs-lookup"><span data-stu-id="4e764-114">**Account names with BAM Management Web Service** – BizTalk Server does not support built-in accounts or accounts without passwords for the BAM Management Web Service User.</span></span> <span data-ttu-id="4e764-115">Web 服务会访问 BizTalk Server 数据库和这些帐户可能带来安全威胁。</span><span class="sxs-lookup"><span data-stu-id="4e764-115">The web service accesses the BizTalk Server database and these accounts may suggest a security threat.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="4e764-116">使用这些类型的帐户配置 BizTalk Server 可能会成功，但 BAM 管理 Web 服务会失败。</span><span class="sxs-lookup"><span data-stu-id="4e764-116">Configuring BizTalk Server with these typs of accounts may succeed, but the BAM Management Web Service fails.</span></span> <span data-ttu-id="4e764-117">内置帐户或无密码可用于 BAM 应用程序池。</span><span class="sxs-lookup"><span data-stu-id="4e764-117">Built-in accounts or accounts without passwords can be used for the BAM Application pool.</span></span>

* <span data-ttu-id="4e764-118">**BizTalk 程序集查看器**– 在 64 位平台上不受支持。</span><span class="sxs-lookup"><span data-stu-id="4e764-118">**BizTalk Assembly Viewer** – Not supported on a 64-bit platform.</span></span> 
* <span data-ttu-id="4e764-119">**安装和卸载**– 卸载 BizTalk Server 需要手动删除 BizTalk Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="4e764-119">**Install and Uninstall** – Uninstalling BizTalk Server requires manually deleting the BizTalk Server databases.</span></span> <span data-ttu-id="4e764-120">如果以开发人员或评估师身份安装 BizTalk Server，使用虚拟机。</span><span class="sxs-lookup"><span data-stu-id="4e764-120">If you are installing BizTalk Server as a developer or evaluator, use a virtual machine.</span></span> <span data-ttu-id="4e764-121">如果你需要重新安装，您可以轻松回滚虚拟机而无需卸载和删除数据库。</span><span class="sxs-lookup"><span data-stu-id="4e764-121">If you need to reinstall, you can easily roll back the virtual machine without having to uninstall and delete the databases.</span></span>
* <span data-ttu-id="4e764-122">**32 位和 64 位计算机**– 有一些不同之处 32 位或 64 位计算机上安装 BizTalk Server 时。</span><span class="sxs-lookup"><span data-stu-id="4e764-122">**32-bit and 64-bit computers** – There are few differences when installing BizTalk Server on 32-bit or 64-bit computer.</span></span> <span data-ttu-id="4e764-123">安装和配置对 32 位和 64 位计算机。</span><span class="sxs-lookup"><span data-stu-id="4e764-123">The installation and configuration covers 32-bit and 64-bit computers.</span></span> <span data-ttu-id="4e764-124">任何对差异进行说明。</span><span class="sxs-lookup"><span data-stu-id="4e764-124">Any differences are noted.</span></span>
* <span data-ttu-id="4e764-125">**工作组**-安装和配置 BizTalk Server 的单台计算机上的工作组环境中受支持。</span><span class="sxs-lookup"><span data-stu-id="4e764-125">**Workgroups** - Installing and configuring BizTalk Server in the workgroup environment on a single computer is supported.</span></span> <span data-ttu-id="4e764-126">安装并在同一台计算机上配置 SQL Server 和 BizTalk Server 功能和组件。</span><span class="sxs-lookup"><span data-stu-id="4e764-126">SQL Server and BizTalk Server features and components are installed and configured on the same computer.</span></span>


## <a name="install-biztalk-server"></a><span data-ttu-id="4e764-127">安装 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="4e764-127">Install BizTalk Server</span></span>
1. <span data-ttu-id="4e764-128">关闭任何打开的程序。</span><span class="sxs-lookup"><span data-stu-id="4e764-128">Close any open programs.</span></span> <span data-ttu-id="4e764-129">以管理员身份运行 BizTalk Server 安装程序。</span><span class="sxs-lookup"><span data-stu-id="4e764-129">Run the BizTalk Server setup as an Administrator.</span></span>
2. <span data-ttu-id="4e764-130">选择**安装 Microsoft BizTalk Server 2016**。</span><span class="sxs-lookup"><span data-stu-id="4e764-130">Select **Install Microsoft BizTalk Server 2016**.</span></span>
3. <span data-ttu-id="4e764-131">输入你**用户名**、 你**组织**，和你的产品密钥。</span><span class="sxs-lookup"><span data-stu-id="4e764-131">Enter your **User name**, your **Organization**, and your product key.</span></span> <span data-ttu-id="4e764-132">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4e764-132">Select **Next**.</span></span>
4. <span data-ttu-id="4e764-133">接受许可协议，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4e764-133">Accept the license agreement, and select **Next**.</span></span>
5. <span data-ttu-id="4e764-134">选择参与客户体验改善计划，并选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4e764-134">Choose to participate in the Customer Experience Improvement Program, and select **Next**.</span></span>
6. <span data-ttu-id="4e764-135">选择你想要安装的组件：</span><span class="sxs-lookup"><span data-stu-id="4e764-135">Choose which components you want to install:</span></span>

    ![bts2016install_components](../install-and-config-guides/media/bts2016install-components.gif)
  
    <span data-ttu-id="4e764-137">请务必选择**其他软件**。</span><span class="sxs-lookup"><span data-stu-id="4e764-137">Be sure to select **Additional Software**.</span></span> <span data-ttu-id="4e764-138">此外可以更改安装位置：</span><span class="sxs-lookup"><span data-stu-id="4e764-138">You can also change the installation location:</span></span> 
  
    ![bts2016install_additional](../install-and-config-guides/media/bts2016install-additional.gif)

    <span data-ttu-id="4e764-140">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4e764-140">Select **Next**.</span></span>   
  
   7. <span data-ttu-id="4e764-141">根据你选择的组件，可能有一些其他先决条件，如 ADOMD.NET。</span><span class="sxs-lookup"><span data-stu-id="4e764-141">Depending on the components you choose, there may be some additional prerequisites, such as ADOMD.NET.</span></span> <span data-ttu-id="4e764-142">安装程序可以安装可再发行组件会自动为您的所有必备组件。</span><span class="sxs-lookup"><span data-stu-id="4e764-142">The setup can install all the redistributable prerequisites automatically for you.</span></span> <span data-ttu-id="4e764-143">您的选择包括：</span><span class="sxs-lookup"><span data-stu-id="4e764-143">Your options include:</span></span>
7. <span data-ttu-id="4e764-144">**手动安装可再发行的必备组件**:这会关闭安装向导，以便你可以手动安装缺少的必备组件。</span><span class="sxs-lookup"><span data-stu-id="4e764-144">**Manually install the redistributable prerequisites** : The installation wizard closes so you can manually install the missing prerequisites.</span></span>
8. <span data-ttu-id="4e764-145">**自动从 web 安装可再发行的必备组件**:默认值。</span><span class="sxs-lookup"><span data-stu-id="4e764-145">**Automatically install the redistributable prerequisites from the web** : Default.</span></span> <span data-ttu-id="4e764-146">需要 internet 访问权限。</span><span class="sxs-lookup"><span data-stu-id="4e764-146">Requires internet access.</span></span>
9. <span data-ttu-id="4e764-147">**下载可再发行的必备组件 CAB 文件**:下载的 CAB 文件，你可以安装更高版本。</span><span class="sxs-lookup"><span data-stu-id="4e764-147">**Download the redistributable prerequisites CAB file** : Downloads a CAB file, which you can install later.</span></span>
10. <span data-ttu-id="4e764-148">**自动从 CAB 文件安装可再发行的必备组件**:如果你以前下载的 CAB 文件，可以选择此选项可以使用这些 CAB 文件。</span><span class="sxs-lookup"><span data-stu-id="4e764-148">**Automatically install the redistributable prerequisites from a CAB file**: If you previously downloaded the CAB files, you can select this option to use those CAB files.</span></span> 

    <span data-ttu-id="4e764-149">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4e764-149">Select **Next**.</span></span>
  
11. <span data-ttu-id="4e764-150">查看摘要页。</span><span class="sxs-lookup"><span data-stu-id="4e764-150">Review the summary page.</span></span> <span data-ttu-id="4e764-151">若要进行任何更改，请选择**回**来选中或取消选中任何组件。</span><span class="sxs-lookup"><span data-stu-id="4e764-151">To make any changes, select **Back** to check or uncheck any components.</span></span> 

      <span data-ttu-id="4e764-152">若要使系统重新启动后自动登录，请选择**设置**，并输入登录帐户。</span><span class="sxs-lookup"><span data-stu-id="4e764-152">To enable auto-logon after a system reboot, select **Set**, and enter the sign-in account.</span></span> <span data-ttu-id="4e764-153">在 BizTalk 安装程序期间才启用此项。</span><span class="sxs-lookup"><span data-stu-id="4e764-153">This is only enabled during the BizTalk setup.</span></span> <span data-ttu-id="4e764-154">安装程序完成后，禁用此设置。</span><span class="sxs-lookup"><span data-stu-id="4e764-154">When setup is complete, this setting is disabled.</span></span> 

     <span data-ttu-id="4e764-155">选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="4e764-155">Select **Install**.</span></span>
  
12. <span data-ttu-id="4e764-156">若要立即配置 BizTalk，请检查**启动 BizTalk Server 配置**。</span><span class="sxs-lookup"><span data-stu-id="4e764-156">To configure BizTalk now, check **Launch BizTalk Server Configuration**.</span></span> <span data-ttu-id="4e764-157">如果不想要立即配置 BizTalk，然后取消选中此选项，并选择**完成**若要关闭安装向导。</span><span class="sxs-lookup"><span data-stu-id="4e764-157">If you don't want to configure BizTalk now, then uncheck this option, and select **Finish** to close the installation wizard.</span></span> 

<span data-ttu-id="4e764-158">安装日志文件生成于临时文件夹，类似于： `C:\Users\*username*\AppData\Local\Setup(011217 xxxxxx).htm`</span><span class="sxs-lookup"><span data-stu-id="4e764-158">A setup log file is generated in a temp folder, similar to: `C:\Users\*username*\AppData\Local\Setup(011217 xxxxxx).htm`</span></span>
  
## <a name="check-the-installation"></a><span data-ttu-id="4e764-159">检查安装</span><span class="sxs-lookup"><span data-stu-id="4e764-159">Check the installation</span></span>

* <span data-ttu-id="4e764-160">BizTalk Server 所示**程序和功能**。</span><span class="sxs-lookup"><span data-stu-id="4e764-160">BizTalk Server is listed in **Programs and Features**.</span></span>
* <span data-ttu-id="4e764-161">`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0`注册表项列出了 BizTalk Server 版本、 安装路径、 版本和其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="4e764-161">The `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0` registry key lists the BizTalk Server version, the install path, the edition, and other details.</span></span>
* <span data-ttu-id="4e764-162">BizTalk Server 管理、 配置和其他组件在您的应用程序中列出。</span><span class="sxs-lookup"><span data-stu-id="4e764-162">BizTalk Server Administration, Configuration, and other components are listed in your Apps.</span></span> 

## <a name="next-step"></a><span data-ttu-id="4e764-163">下一步</span><span class="sxs-lookup"><span data-stu-id="4e764-163">Next step</span></span>
[<span data-ttu-id="4e764-164">配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="4e764-164">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)