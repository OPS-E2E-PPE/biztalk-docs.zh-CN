---
title: 安装、 配置和部署中的已知问题 |Microsoft 文档
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
ms.openlocfilehash: cda1bd5c8167bbf9f6049b3620c0c949950b1e89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299829"
---
# <a name="known-issues-in-installation-configuration-and-deployment"></a><span data-ttu-id="521b5-102">安装、配置和部署过程中的已知问题</span><span class="sxs-lookup"><span data-stu-id="521b5-102">Known Issues in Installation, Configuration, and Deployment</span></span>
## <a name="some-biztalk-edias2-artifacts-are-still-active-after-unconfiguring"></a><span data-ttu-id="521b5-103">某些 BizTalk EDI/AS2 项目在取消配置后仍处于活动状态</span><span class="sxs-lookup"><span data-stu-id="521b5-103">Some BizTalk EDI/AS2 Artifacts Are Still Active After Unconfiguring</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="521b5-104">Problem</span><span class="sxs-lookup"><span data-stu-id="521b5-104">Problem</span></span>  
 <span data-ttu-id="521b5-105">取消对 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的 BizTalk EDI/AS2 功能的配置后，与 EDI 和 AS2 处理相关的某些 BizTalk Server 项目在 BizTalk 组配置的上下文中将仍处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="521b5-105">After you unconfigure the BizTalk EDI/AS2 feature of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], some BizTalk Server artifacts related to EDI and AS2 processing will still be active in the context of the BizTalk group configuration.</span></span> <span data-ttu-id="521b5-106">这些项目将包括 EDI 和 AS2 管道以及批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="521b5-106">These artifacts will include EDI and AS2 pipelines and the batching orchestration.</span></span> <span data-ttu-id="521b5-107">因此，即使在取消对 BizTalk EDI/AS2 功能的配置后，您仍然能够执行基本的 EDI 和 AS2 处理。</span><span class="sxs-lookup"><span data-stu-id="521b5-107">As a result, you will still be able to perform basic EDI and AS2 processing even after unconfiguring the BizTalk EDI/AS2 feature.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="521b5-108">原因</span><span class="sxs-lookup"><span data-stu-id="521b5-108">Cause</span></span>  
 <span data-ttu-id="521b5-109">存在与 EDI 和 AS2 处理关联的活动端口。</span><span class="sxs-lookup"><span data-stu-id="521b5-109">There are active ports associated with EDI and AS2 processing.</span></span> <span data-ttu-id="521b5-110">某些项目在这些端口保持活动时会继续工作。</span><span class="sxs-lookup"><span data-stu-id="521b5-110">Some artifacts will continue to function while these ports remain active.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="521b5-111">解决方法</span><span class="sxs-lookup"><span data-stu-id="521b5-111">Resolution</span></span>  
 <span data-ttu-id="521b5-112">若要禁用所有 EDI/AS2 项目，应禁用、停止或删除与 EDI 和 AS2 处理关联的端口。</span><span class="sxs-lookup"><span data-stu-id="521b5-112">To disable all EDI/AS2 artifacts, you should disable, stop, or delete the ports associated with EDI and AS2 processing.</span></span>  
  
## <a name="if-the-biztalk-server-computer-or-sql-server-computer-is-renamed-after-biztalk-server-configuration-the-configuration-wizard-will-fail"></a><span data-ttu-id="521b5-113">如果在对 BizTalk Server 进行配置之后重命名了 BizTalk Server 计算机或 SQL Server 计算机，则配置向导将失败</span><span class="sxs-lookup"><span data-stu-id="521b5-113">If the BizTalk Server Computer or SQL Server Computer Is Renamed After BizTalk Server Configuration, the Configuration Wizard Will Fail</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="521b5-114">Problem</span><span class="sxs-lookup"><span data-stu-id="521b5-114">Problem</span></span>  
 <span data-ttu-id="521b5-115">此问题的表现方式有多种：</span><span class="sxs-lookup"><span data-stu-id="521b5-115">This problem may manifest itself in several ways:</span></span>  
  
-   <span data-ttu-id="521b5-116">BizTalk Server 配置可以正确加载“概述”页，但在尝试配置功能时，屏幕上不显示功能选项。</span><span class="sxs-lookup"><span data-stu-id="521b5-116">The BizTalk Server Configuration will load the Overview page correctly, but when attempting to configure a feature the feature options do not display on the screen.</span></span>  
  
-   <span data-ttu-id="521b5-117">配置向导无法连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="521b5-117">The configuration wizard cannot connect to the SQL Server.</span></span>  
  
-   <span data-ttu-id="521b5-118">尝试使用“取消对所有功能的配置”时仅取消了对部分功能而不是所有功能的配置。</span><span class="sxs-lookup"><span data-stu-id="521b5-118">Attempting to Unconfigure All unconfigures some features, but not all.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="521b5-119">原因</span><span class="sxs-lookup"><span data-stu-id="521b5-119">Cause</span></span>  
 <span data-ttu-id="521b5-120">BizTalk Server 配置存储了计算机的网络名称。</span><span class="sxs-lookup"><span data-stu-id="521b5-120">The BizTalk Server configuration stores the computer network name.</span></span> <span data-ttu-id="521b5-121">如果重命名了计算机，“BizTalk Server 配置”和配置向导将无法找到 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="521b5-121">When the computer is renamed the BizTalk Server Configuration and configuration wizard cannot locate the BizTalk Server.</span></span> <span data-ttu-id="521b5-122">如果在对 BizTalk Server 进行配置之后重命名了 SQL Server 计算机，将会出现类似的问题。</span><span class="sxs-lookup"><span data-stu-id="521b5-122">A similar problem will occur if the SQL Server computer is renamed after BizTalk Server is configured.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="521b5-123">解决方法</span><span class="sxs-lookup"><span data-stu-id="521b5-123">Resolution</span></span>  
 <span data-ttu-id="521b5-124">请不要重命名 BizTalk Server 计算机或 SQL Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="521b5-124">Do not rename the BizTalk Server computer or the SQL Server computer.</span></span> <span data-ttu-id="521b5-125">如果必须对服务器进行重命名，请取消对所有 BizTalk 功能的配置，然后再重命名计算机。</span><span class="sxs-lookup"><span data-stu-id="521b5-125">If a server must be renamed, unconfigure all BizTalk Features before renaming the computer.</span></span> <span data-ttu-id="521b5-126">在重命名计算机后，请重新配置 BizTalk Server 功能。</span><span class="sxs-lookup"><span data-stu-id="521b5-126">After renaming the computer, reconfigure BizTalk Server features.</span></span>  
  
## <a name="the-biztalk-server-business-rules-configuration-wizard-fails"></a><span data-ttu-id="521b5-127">BizTalk Server 业务规则配置向导失败</span><span class="sxs-lookup"><span data-stu-id="521b5-127">The BizTalk Server Business Rules Configuration Wizard Fails</span></span>  
  
### <a name="problem"></a><span data-ttu-id="521b5-128">Problem</span><span class="sxs-lookup"><span data-stu-id="521b5-128">Problem</span></span>  
  
-   <span data-ttu-id="521b5-129">业务规则配置向导失败，并显示错误“某些组件配置失败，没有为这些组件应用任何设置”。</span><span class="sxs-lookup"><span data-stu-id="521b5-129">The Business Rules Configuration Wizard fails with the error “Configuration failed for some components and no settings were applied for those components”.</span></span>  
  
-   <span data-ttu-id="521b5-130">在已为其成功配置业务规则引擎的 BizTalk Server 计算机上，规则引擎更新服务启动失败并且不能手动启动。</span><span class="sxs-lookup"><span data-stu-id="521b5-130">On BizTalk Server computers for which the Business Rules Engine has already been successfully configured, the Rules Engine Update service fails to start and cannot be started manually.</span></span>  
  
 <span data-ttu-id="521b5-131">出现此问题时，可能会在 BizTalk Server 计算机的应用程序日志中生成与下面类似的错误：</span><span class="sxs-lookup"><span data-stu-id="521b5-131">When this problem occurs, an error similar to the following may be generated in the BizTalk Server computer Application log:</span></span>  
  
```  
Service could not be started. : System.Net.Sockets.SocketException (10061): No connection could be made because the target machine actively refused it ::1:3132  
  
```  
  
### <a name="cause"></a><span data-ttu-id="521b5-132">原因</span><span class="sxs-lookup"><span data-stu-id="521b5-132">Cause</span></span>  
 <span data-ttu-id="521b5-133">Microsoft 恶意软件防护中心发布了一个更新的签名文件，用于解决可能来自 SettingsModifier:Win32/PossibleHostsFileHijack 的威胁。</span><span class="sxs-lookup"><span data-stu-id="521b5-133">The Microsoft Malware Protection Center released an updated signature file to address a possible threat from SettingsModifier:Win32/PossibleHostsFileHijack.</span></span> <span data-ttu-id="521b5-134">此更新的签名文件可能导致 Microsoft 恶意软件检测软件（例如 Windows Defender）更新本地 HOSTS 文件，以缓解来自 SettingsModifier:Win32/PossibleHostsFileHijack 的威胁。</span><span class="sxs-lookup"><span data-stu-id="521b5-134">This updated signature file can cause Microsoft Malware Detection software such as Windows Defender to update the local HOSTS file to mitigate threats from SettingsModifier:Win32/PossibleHostsFileHijack.</span></span> <span data-ttu-id="521b5-135">由于这些更改，BizTalk Server 规则引擎更新服务可能启动失败。</span><span class="sxs-lookup"><span data-stu-id="521b5-135">As a result of these changes, the BizTalk Server Rules Engine Update service may fail to start.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="521b5-136">解决方法</span><span class="sxs-lookup"><span data-stu-id="521b5-136">Resolution</span></span>  
 <span data-ttu-id="521b5-137">更新本地 HOSTS 文件以包括以下行：</span><span class="sxs-lookup"><span data-stu-id="521b5-137">Update the local HOSTS file to include the following line:</span></span>  
  
```  
127.0.0.1         localhost  
```  
  
 <span data-ttu-id="521b5-138">HOSTS 文件位于 %systemroot%\drivers\etc\ 目录中。</span><span class="sxs-lookup"><span data-stu-id="521b5-138">The HOSTS file is located in the %systemroot%\drivers\etc\ directory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="521b5-139">有关解决可能来自 SettingsModifier:Win32/PossibleHostsFileHijack 的威胁的 Microsoft 恶意软件防护中心签名更新的详细信息，请参阅 [http://go.microsoft.com/fwlink/?LinkId=146221](http://go.microsoft.com/fwlink/?LinkId=146221)。</span><span class="sxs-lookup"><span data-stu-id="521b5-139">For more information about the Microsoft Malware Protection Center signature update that addresses a possible threat from SettingsModifier:Win32/PossibleHostsFileHijack, go to [http://go.microsoft.com/fwlink/?LinkId=146221](http://go.microsoft.com/fwlink/?LinkId=146221).</span></span>  
  
## <a name="enlistment-of-an-orchestration-fails-if-referenced-assemblies-are-missing-from-the-gacmgmt-db"></a><span data-ttu-id="521b5-140">如果 GAC/Mgmt 数据库中缺少引用的程序集，则业务流程登记将失败</span><span class="sxs-lookup"><span data-stu-id="521b5-140">Enlistment of an Orchestration Fails if Referenced Assemblies are Missing from the GAC/Mgmt DB</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="521b5-141">Problem</span><span class="sxs-lookup"><span data-stu-id="521b5-141">Problem</span></span>  
 <span data-ttu-id="521b5-142">如果 GAC/Mgmt 数据库中缺少引用（业务流程中引用的 C# 程序集），则业务流程登记将失败。</span><span class="sxs-lookup"><span data-stu-id="521b5-142">Enlistment of an orchestration fails if references (C# assemblies which are referenced to orchestrations) are missing from the GAC/Mgmt db.</span></span> <span data-ttu-id="521b5-143">在重新部署过程中，可能会需要基于业务流程的现有状态登记业务流程。</span><span class="sxs-lookup"><span data-stu-id="521b5-143">During re-deployment, there may be a need to enlist the orchestration based on its existing state.</span></span> <span data-ttu-id="521b5-144">如果缺少引用，则部署也会失败。</span><span class="sxs-lookup"><span data-stu-id="521b5-144">If references are missing then the deployment also fails.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="521b5-145">原因</span><span class="sxs-lookup"><span data-stu-id="521b5-145">Cause</span></span>  
 <span data-ttu-id="521b5-146">GAC/Mgmt 数据库中缺少引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="521b5-146">Referenced assemblies are missing from GAC/Mgmt db.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="521b5-147">解决方法</span><span class="sxs-lookup"><span data-stu-id="521b5-147">Resolution</span></span>  
 <span data-ttu-id="521b5-148">在 GAC 中添加引用的程序集，或者将它们作为资源添加，以便可以将它们存储在 Mgmt 数据库中，并且可以在业务流程登记过程中访问它们。</span><span class="sxs-lookup"><span data-stu-id="521b5-148">Add the referenced assemblies in GAC or add them as resources, so that they are stored in Mgmt db and are accessible during enlistment of orchestration.</span></span>  

## <a name="community-blog-biztalk-2013-r2-bugs-issues--quirks"></a><span data-ttu-id="521b5-149">社区博客：BizTalk 2013 R2 bug、问题和 quirks</span><span class="sxs-lookup"><span data-stu-id="521b5-149">Community blog: BizTalk 2013 R2 bugs, issues & quirks</span></span>

<span data-ttu-id="521b5-150">[BizTalk Server 2013 R2 known bugs, issues, quirks](https://cdijkgraaf.wordpress.com/2016/08/12/biztalk-2013-r2-known-bugs-issues-quirks/)（BizTalk Server 2013 R2 已知 bug、问题和 quirks）</span><span class="sxs-lookup"><span data-stu-id="521b5-150">[BizTalk Server 2013 R2 known bugs, issues, quirks](https://cdijkgraaf.wordpress.com/2016/08/12/biztalk-2013-r2-known-bugs-issues-quirks/)</span></span>
  
## <a name="additional-configuration-topics"></a><span data-ttu-id="521b5-151">其他配置主题</span><span class="sxs-lookup"><span data-stu-id="521b5-151">Additional Configuration Topics</span></span>  
  
 [<span data-ttu-id="521b5-152">配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="521b5-152">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)  
  
 [<span data-ttu-id="521b5-153">在 Azure VM 上配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="521b5-153">Configuring BizTalk Server on an Azure VM</span></span>](http://msdn.microsoft.com/library/azure/jj248689.aspx)  
  
  [<span data-ttu-id="521b5-154">在群集中配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="521b5-154">Configure BizTalk Server in a Cluster</span></span>](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)
  
 [<span data-ttu-id="521b5-155">确保 BizTalk Server 部署的安全</span><span class="sxs-lookup"><span data-stu-id="521b5-155">Securing Your BizTalk Server Deployment</span></span>](../install-and-config-guides/securing-your-biztalk-server-deployment.md)  
  