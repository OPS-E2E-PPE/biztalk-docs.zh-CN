---
title: 安装、 配置和部署中的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed1c08eb-d647-4a4a-b9a3-c4d84e8d4b82
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 040b1921228608deddb3e950613f447d984121c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266202"
---
# <a name="known-issues-in-installation-configuration-and-deployment"></a><span data-ttu-id="05d1e-102">安装、 配置和部署中的已知的问题</span><span class="sxs-lookup"><span data-stu-id="05d1e-102">Known Issues in Installation, Configuration, and Deployment</span></span>
## <a name="some-biztalk-edias2-artifacts-are-still-active-after-unconfiguring"></a><span data-ttu-id="05d1e-103">某些 BizTalk edi/as2 项目在取消后仍处于活动</span><span class="sxs-lookup"><span data-stu-id="05d1e-103">Some BizTalk EDI/AS2 Artifacts Are Still Active After Unconfiguring</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="05d1e-104">问题</span><span class="sxs-lookup"><span data-stu-id="05d1e-104">Problem</span></span>  
 <span data-ttu-id="05d1e-105">取消对 BizTalk EDI/AS2 功能后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，与 EDI 和 AS2 处理相关的某些 BizTalk Server 项目仍将在 BizTalk 组配置的上下文中处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="05d1e-105">After you unconfigure the BizTalk EDI/AS2 feature of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], some BizTalk Server artifacts related to EDI and AS2 processing will still be active in the context of the BizTalk group configuration.</span></span> <span data-ttu-id="05d1e-106">这些项目将包括 EDI 和 AS2 管道以及批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="05d1e-106">These artifacts will include EDI and AS2 pipelines and the batching orchestration.</span></span> <span data-ttu-id="05d1e-107">因此，您将仍然能够执行基本的 EDI 和 AS2 处理后取消 BizTalk EDI/AS2 功能的配置。</span><span class="sxs-lookup"><span data-stu-id="05d1e-107">As a result, you will still be able to perform basic EDI and AS2 processing even after unconfiguring the BizTalk EDI/AS2 feature.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="05d1e-108">原因</span><span class="sxs-lookup"><span data-stu-id="05d1e-108">Cause</span></span>  
 <span data-ttu-id="05d1e-109">有活动与 EDI 和 AS2 处理关联的端口。</span><span class="sxs-lookup"><span data-stu-id="05d1e-109">There are active ports associated with EDI and AS2 processing.</span></span> <span data-ttu-id="05d1e-110">某些项目将继续工作时这些端口保持活动状态。</span><span class="sxs-lookup"><span data-stu-id="05d1e-110">Some artifacts will continue to function while these ports remain active.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="05d1e-111">解决方法</span><span class="sxs-lookup"><span data-stu-id="05d1e-111">Resolution</span></span>  
 <span data-ttu-id="05d1e-112">若要禁用所有 edi/as2 项目，应都禁用、 停止或删除与 EDI 和 AS2 处理关联的端口。</span><span class="sxs-lookup"><span data-stu-id="05d1e-112">To disable all EDI/AS2 artifacts, you should disable, stop, or delete the ports associated with EDI and AS2 processing.</span></span>  
  
## <a name="if-the-biztalk-server-computer-or-sql-server-computer-is-renamed-after-biztalk-server-configuration-the-configuration-wizard-will-fail"></a><span data-ttu-id="05d1e-113">如果 BizTalk Server 计算机或 SQL Server 计算机已重命名 BizTalk Server 配置后，配置向导将失败</span><span class="sxs-lookup"><span data-stu-id="05d1e-113">If the BizTalk Server Computer or SQL Server Computer Is Renamed After BizTalk Server Configuration, the Configuration Wizard Will Fail</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="05d1e-114">问题</span><span class="sxs-lookup"><span data-stu-id="05d1e-114">Problem</span></span>  
 <span data-ttu-id="05d1e-115">此问题可能表现几种方式：</span><span class="sxs-lookup"><span data-stu-id="05d1e-115">This problem may manifest itself in several ways:</span></span>  
  
-   <span data-ttu-id="05d1e-116">BizTalk Server 配置正确，将加载概述页，但在尝试配置功能时不在屏幕上显示功能选项。</span><span class="sxs-lookup"><span data-stu-id="05d1e-116">The BizTalk Server Configuration will load the Overview page correctly, but when attempting to configure a feature the feature options do not display on the screen.</span></span>  
  
-   <span data-ttu-id="05d1e-117">配置向导无法连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="05d1e-117">The configuration wizard cannot connect to the SQL Server.</span></span>  
  
-   <span data-ttu-id="05d1e-118">尝试取消对所有 0}run 某些功能，但不是全部。</span><span class="sxs-lookup"><span data-stu-id="05d1e-118">Attempting to Unconfigure All unconfigures some features, but not all.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="05d1e-119">原因</span><span class="sxs-lookup"><span data-stu-id="05d1e-119">Cause</span></span>  
 <span data-ttu-id="05d1e-120">BizTalk Server 配置存储的计算机网络名称。</span><span class="sxs-lookup"><span data-stu-id="05d1e-120">The BizTalk Server configuration stores the computer network name.</span></span> <span data-ttu-id="05d1e-121">如果重命名计算机的 BizTalk Server 配置和配置向导找不到 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="05d1e-121">When the computer is renamed the BizTalk Server Configuration and configuration wizard cannot locate the BizTalk Server.</span></span> <span data-ttu-id="05d1e-122">如果 SQL Server 计算机已重命名 BizTalk Server 配置后，将发生类似的问题。</span><span class="sxs-lookup"><span data-stu-id="05d1e-122">A similar problem will occur if the SQL Server computer is renamed after BizTalk Server is configured.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="05d1e-123">解决方法</span><span class="sxs-lookup"><span data-stu-id="05d1e-123">Resolution</span></span>  
 <span data-ttu-id="05d1e-124">不要重命名 BizTalk Server 计算机或 SQL Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="05d1e-124">Do not rename the BizTalk Server computer or the SQL Server computer.</span></span> <span data-ttu-id="05d1e-125">如果必须重命名服务器，然后再重命名计算机取消所有 BizTalk 功能。</span><span class="sxs-lookup"><span data-stu-id="05d1e-125">If a server must be renamed, unconfigure all BizTalk Features before renaming the computer.</span></span> <span data-ttu-id="05d1e-126">重命名计算机之后, 重新配置 BizTalk Server 功能。</span><span class="sxs-lookup"><span data-stu-id="05d1e-126">After renaming the computer, reconfigure BizTalk Server features.</span></span>  
  
## <a name="the-biztalk-server-business-rules-configuration-wizard-fails"></a><span data-ttu-id="05d1e-127">BizTalk Server 业务规则配置向导失败</span><span class="sxs-lookup"><span data-stu-id="05d1e-127">The BizTalk Server Business Rules Configuration Wizard Fails</span></span>  
  
### <a name="problem"></a><span data-ttu-id="05d1e-128">问题</span><span class="sxs-lookup"><span data-stu-id="05d1e-128">Problem</span></span>  
  
- <span data-ttu-id="05d1e-129">业务规则配置向导失败并出现错误"某些组件的配置失败，这些组件未应用任何设置"。</span><span class="sxs-lookup"><span data-stu-id="05d1e-129">The Business Rules Configuration Wizard fails with the error “Configuration failed for some components and no settings were applied for those components”.</span></span>  
  
- <span data-ttu-id="05d1e-130">在 BizTalk Server 计算机上为其业务规则引擎已成功配置，规则引擎更新服务无法启动，并不能手动启动。</span><span class="sxs-lookup"><span data-stu-id="05d1e-130">On BizTalk Server computers for which the Business Rules Engine has already been successfully configured, the Rules Engine Update service fails to start and cannot be started manually.</span></span>  
  
  <span data-ttu-id="05d1e-131">发生此问题时，可能会在 BizTalk Server 计算机应用程序日志中生成如下错误：</span><span class="sxs-lookup"><span data-stu-id="05d1e-131">When this problem occurs, an error similar to the following may be generated in the BizTalk Server computer Application log:</span></span>  
  
```  
Service could not be started. : System.Net.Sockets.SocketException (10061): No connection could be made because the target machine actively refused it ::1:3132  
  
```  
  
### <a name="cause"></a><span data-ttu-id="05d1e-132">原因</span><span class="sxs-lookup"><span data-stu-id="05d1e-132">Cause</span></span>  
 <span data-ttu-id="05d1e-133">Microsoft 恶意软件防护中心发布更新的签名文件，用于解决可能来自 SettingsModifier:Win32 威胁 / PossibleHostsFileHijack。</span><span class="sxs-lookup"><span data-stu-id="05d1e-133">The Microsoft Malware Protection Center released an updated signature file to address a possible threat from SettingsModifier:Win32/PossibleHostsFileHijack.</span></span> <span data-ttu-id="05d1e-134">此更新的签名文件可能会导致 Microsoft 恶意软件检测软件，如 Windows Defender 更新本地 HOSTS 文件，以消除威胁 SettingsModifier:Win32 / PossibleHostsFileHijack。</span><span class="sxs-lookup"><span data-stu-id="05d1e-134">This updated signature file can cause Microsoft Malware Detection software such as Windows Defender to update the local HOSTS file to mitigate threats from SettingsModifier:Win32/PossibleHostsFileHijack.</span></span> <span data-ttu-id="05d1e-135">这些更改会导致 BizTalk Server 规则引擎更新服务可能无法启动。</span><span class="sxs-lookup"><span data-stu-id="05d1e-135">As a result of these changes, the BizTalk Server Rules Engine Update service may fail to start.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="05d1e-136">解决方法</span><span class="sxs-lookup"><span data-stu-id="05d1e-136">Resolution</span></span>  
 <span data-ttu-id="05d1e-137">更新本地 HOSTS 文件，以包含以下行：</span><span class="sxs-lookup"><span data-stu-id="05d1e-137">Update the local HOSTS file to include the following line:</span></span>  
  
```  
127.0.0.1         localhost  
```  
  
 <span data-ttu-id="05d1e-138">主机文件位于 %systemroot%\drivers\etc\ 目录中。</span><span class="sxs-lookup"><span data-stu-id="05d1e-138">The HOSTS file is located in the %systemroot%\drivers\etc\ directory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05d1e-139">有关解决可能来自 SettingsModifier:Win32 威胁的 Microsoft 恶意软件防护中心签名更新的详细信息 / PossibleHostsFileHijack，请转到[ http://go.microsoft.com/fwlink/?LinkId=146221 ](http://go.microsoft.com/fwlink/?LinkId=146221)。</span><span class="sxs-lookup"><span data-stu-id="05d1e-139">For more information about the Microsoft Malware Protection Center signature update that addresses a possible threat from SettingsModifier:Win32/PossibleHostsFileHijack, go to [http://go.microsoft.com/fwlink/?LinkId=146221](http://go.microsoft.com/fwlink/?LinkId=146221).</span></span>  
  
## <a name="enlistment-of-an-orchestration-fails-if-referenced-assemblies-are-missing-from-the-gacmgmt-db"></a><span data-ttu-id="05d1e-140">Enlistment 的业务流程失败，如果引用程序集缺少 GAC/Mgmt 数据库中</span><span class="sxs-lookup"><span data-stu-id="05d1e-140">Enlistment of an Orchestration Fails if Referenced Assemblies are Missing from the GAC/Mgmt DB</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="05d1e-141">问题</span><span class="sxs-lookup"><span data-stu-id="05d1e-141">Problem</span></span>  
 <span data-ttu-id="05d1e-142">如果业务流程登记将失败的引用 (C#中引用的业务流程的程序集) 缺少 GAC/Mgmt 数据库中。</span><span class="sxs-lookup"><span data-stu-id="05d1e-142">Enlistment of an orchestration fails if references (C# assemblies which are referenced to orchestrations) are missing from the GAC/Mgmt db.</span></span> <span data-ttu-id="05d1e-143">在重新部署过程都可能有需要登记业务流程基于其现有状态。</span><span class="sxs-lookup"><span data-stu-id="05d1e-143">During re-deployment, there may be a need to enlist the orchestration based on its existing state.</span></span> <span data-ttu-id="05d1e-144">如果缺少引用然后部署也会失败。</span><span class="sxs-lookup"><span data-stu-id="05d1e-144">If references are missing then the deployment also fails.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="05d1e-145">原因</span><span class="sxs-lookup"><span data-stu-id="05d1e-145">Cause</span></span>  
 <span data-ttu-id="05d1e-146">GAC/Mgmt 数据库中缺少引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="05d1e-146">Referenced assemblies are missing from GAC/Mgmt db.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="05d1e-147">解决方法</span><span class="sxs-lookup"><span data-stu-id="05d1e-147">Resolution</span></span>  
 <span data-ttu-id="05d1e-148">在 GAC 中添加引用的程序集或将其添加为资源，以便存储在 Mgmt 数据库中并在业务流程登记过程进行访问。</span><span class="sxs-lookup"><span data-stu-id="05d1e-148">Add the referenced assemblies in GAC or add them as resources, so that they are stored in Mgmt db and are accessible during enlistment of orchestration.</span></span>  

## <a name="community-blog-biztalk-2013-r2-bugs-issues-quirks"></a><span data-ttu-id="05d1e-149">社区博客：BizTalk 2013 R2 bug、 问题和 quirks</span><span class="sxs-lookup"><span data-stu-id="05d1e-149">Community blog: BizTalk 2013 R2 bugs, issues & quirks</span></span>

[<span data-ttu-id="05d1e-150">BizTalk Server 2013 R2 已知 bug、 问题、 quirks</span><span class="sxs-lookup"><span data-stu-id="05d1e-150">BizTalk Server 2013 R2 known bugs, issues, quirks</span></span>](https://cdijkgraaf.wordpress.com/2016/08/12/biztalk-2013-r2-known-bugs-issues-quirks/)
  
## <a name="additional-configuration-topics"></a><span data-ttu-id="05d1e-151">其他配置主题</span><span class="sxs-lookup"><span data-stu-id="05d1e-151">Additional Configuration Topics</span></span>  
  
 [<span data-ttu-id="05d1e-152">配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="05d1e-152">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)  
  
 [<span data-ttu-id="05d1e-153">在 Azure VM 上配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="05d1e-153">Configuring BizTalk Server on an Azure VM</span></span>](http://msdn.microsoft.com/library/azure/jj248689.aspx)  
  
  [<span data-ttu-id="05d1e-154">在群集中配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="05d1e-154">Configure BizTalk Server in a Cluster</span></span>](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)
  
 [<span data-ttu-id="05d1e-155">保护 BizTalk Server 部署</span><span class="sxs-lookup"><span data-stu-id="05d1e-155">Securing Your BizTalk Server Deployment</span></span>](../install-and-config-guides/securing-your-biztalk-server-deployment.md)  
  