---
title: A4SWIFT 清理工具 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- A4SWIFT Cleanup tool
ms.assetid: e694f824-6097-4d60-bc7b-b4f1a40acea0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db6e9f6f6ec25762abc4416bc18f0955055b7e70
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983614"
---
# <a name="a4swift-cleanup-tool"></a><span data-ttu-id="6b860-102">A4SWIFT 清理工具</span><span class="sxs-lookup"><span data-stu-id="6b860-102">A4SWIFT Cleanup Tool</span></span>
<span data-ttu-id="6b860-103">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]清理工具，您可以准备了 Microsoft 的服务器[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]的新安装上安装[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6b860-103">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] cleanup tool enables you to prepare a server that has the Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] installed on it for a new installation of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span> <span data-ttu-id="6b860-104">该工具删除 A4SWIFT 项目，例如协议、 部门和业务规则引擎 (BRE) 策略，并取消部署程序集。</span><span class="sxs-lookup"><span data-stu-id="6b860-104">The tool removes A4SWIFT artifacts such as agreements, departments, and Business Rule Engine (BRE) policies, and undeploys assemblies.</span></span> <span data-ttu-id="6b860-105">运行此工具使你可以避免手动删除许多 A4SWIFT 项目，并用于解决可能与其他程序集引用的取消部署程序集的问题。</span><span class="sxs-lookup"><span data-stu-id="6b860-105">Running the tool enables you to avoid manually removing many A4SWIFT artifacts, and resolves problems with undeploying assemblies that might be referenced from other assemblies.</span></span>  
  
 <span data-ttu-id="6b860-106">当您运行清理工具时，您可以保留 A4SWIFT 安装上的计算机 （默认值） 或卸载 A4SWIFT 后删除这些项目的选择。</span><span class="sxs-lookup"><span data-stu-id="6b860-106">When you run the cleanup tool, you have the choice of leaving A4SWIFT installed on the computer (the default), or uninstalling A4SWIFT after removing the artifacts.</span></span> <span data-ttu-id="6b860-107">您应卸载 A4SWIFT 之前运行该工具。</span><span class="sxs-lookup"><span data-stu-id="6b860-107">You should run the tool before uninstalling A4SWIFT.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="6b860-108">在生产环境中不使用 A4SWIFT 清理工具。</span><span class="sxs-lookup"><span data-stu-id="6b860-108">Do not use the A4SWIFT cleanup tool in a production environment.</span></span> <span data-ttu-id="6b860-109">该工具用于在单一服务器开发环境，不在多服务器部署中使用。</span><span class="sxs-lookup"><span data-stu-id="6b860-109">The tool is intended to be used in a single-server development environment, not in a multiserver deployment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b860-110">默认情况下，清理工具不适用于任何其他语言比英语。</span><span class="sxs-lookup"><span data-stu-id="6b860-110">By default, the cleanup tool does not work for any other language than English.</span></span> <span data-ttu-id="6b860-111">但是，可以修改环境，以便清理工具适用于本地化的计算机。</span><span class="sxs-lookup"><span data-stu-id="6b860-111">You can, however, modify the environment so that the cleanup tool works on a localized computer.</span></span> <span data-ttu-id="6b860-112">使用 t 参数和已本地化的字符串的模板文档库，例如，运行 FormPublish 工具**t:VorLagen**正使用德语的环境中。</span><span class="sxs-lookup"><span data-stu-id="6b860-112">Run the FormPublish tool with the t parameter and the localized string for the Templates document library, for example, **t:VorLagen** in a German environment.</span></span> <span data-ttu-id="6b860-113">然后可以在本地化环境中运行清理工具。</span><span class="sxs-lookup"><span data-stu-id="6b860-113">You can then run the cleanup tool in a localized environment.</span></span>  
  
 <span data-ttu-id="6b860-114">必须满足以下用于运行清理工具：</span><span class="sxs-lookup"><span data-stu-id="6b860-114">The following must be true for the cleanup tool to run:</span></span>  
  
- <span data-ttu-id="6b860-115">您必须是成员[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员组。</span><span class="sxs-lookup"><span data-stu-id="6b860-115">You must be a member the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators groups.</span></span>  
  
- [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]<span data-ttu-id="6b860-116"> 必须在运行该工具的服务器上安装。</span><span class="sxs-lookup"><span data-stu-id="6b860-116"> must be installed on the server on which you run the tool.</span></span>  
  
- <span data-ttu-id="6b860-117">MrsrConfiguration.dll、 Shared.dll 和 RuleEngineExtension.dll 必须部署在运行该工具的服务器上。</span><span class="sxs-lookup"><span data-stu-id="6b860-117">MrsrConfiguration.dll, Shared.dll, and RuleEngineExtension.dll must be deployed on the server on which you run the tool.</span></span>  
  
## <a name="what-the-cleanup-tool-does"></a><span data-ttu-id="6b860-118">清理工具的功能</span><span class="sxs-lookup"><span data-stu-id="6b860-118">What the cleanup tool does</span></span>  
 <span data-ttu-id="6b860-119">A4SWIFT 清理工具执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6b860-119">The A4SWIFT cleanup tool performs the following operations:</span></span>  
  
- <span data-ttu-id="6b860-120">运行**BM 取消部署**针对 ForActivities.xml 和 MRSRBAM.xml</span><span class="sxs-lookup"><span data-stu-id="6b860-120">Runs **BM Undeploy** against ForActivities.xml and MRSRBAM.xml</span></span>  
  
- <span data-ttu-id="6b860-121">如果它们存在，删除 FrrActivities_ConnectionStrings.xml 和 MRSRActivities_ConnectionStrings.xml 文件</span><span class="sxs-lookup"><span data-stu-id="6b860-121">Removes the FrrActivities_ConnectionStrings.xml and MRSRActivities_ConnectionStrings.xml files, if they exist</span></span>  
  
- <span data-ttu-id="6b860-122">删除 A4SWIFT 2.1，如果它存在 (如果已升级到服务器[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]，但安装仍保持 A4SWIFT 2.1 安装)，并删除 A4SWIFT 2.1 文件夹</span><span class="sxs-lookup"><span data-stu-id="6b860-122">Removes A4SWIFT 2.1 if it exists (if you have upgraded the server to [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)], but Setup has left A4SWIFT 2.1 installed) and deletes the A4SWIFT 2.1 folder</span></span>  
  
- <span data-ttu-id="6b860-123">取消部署所有 A4SWIFT 程序集</span><span class="sxs-lookup"><span data-stu-id="6b860-123">Undeploys all A4SWIFT assemblies</span></span>  
  
- <span data-ttu-id="6b860-124">将删除 A4SWIFT 管理员组的 A4SWIFT 用户组</span><span class="sxs-lookup"><span data-stu-id="6b860-124">Deletes the A4SWIFT Administrator group and the A4SWIFT Users group</span></span>  
  
- <span data-ttu-id="6b860-125">删除 A4SWIFT 数据库</span><span class="sxs-lookup"><span data-stu-id="6b860-125">Deletes the A4SWIFT database</span></span>  
  
- <span data-ttu-id="6b860-126">删除 A4SWIFT 虚拟目录</span><span class="sxs-lookup"><span data-stu-id="6b860-126">Deletes the A4SWIFT virtual directory</span></span>  
  
- <span data-ttu-id="6b860-127">运行完全无提示卸载[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]，并删除[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]文件夹 （如果选择）</span><span class="sxs-lookup"><span data-stu-id="6b860-127">Runs a complete silent uninstall of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] and deletes the [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] folder (if selected)</span></span>  
  
  <span data-ttu-id="6b860-128">因为它会删除项目，并取消部署程序集，清理工具还执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6b860-128">As it removes artifacts and undeploys assemblies, the cleanup tool also does the following:</span></span>  
  
- <span data-ttu-id="6b860-129">若要运行启动 Internet Information Services (IIS) 管理服务</span><span class="sxs-lookup"><span data-stu-id="6b860-129">Starts Internet Information Services (IIS) Admin Service in order to run</span></span>  
  
- <span data-ttu-id="6b860-130">停止并重新启动 MSSQLSERVER、 SQLSERVERAGENT、 BizTalk，和企业单一登录服务</span><span class="sxs-lookup"><span data-stu-id="6b860-130">Stops and then restarts the MSSQLSERVER, SQLSERVERAGENT, BizTalk, and Enterprise Single Sign-On services</span></span>  
  
#### <a name="to-run-the-a4swift-cleanup-tool"></a><span data-ttu-id="6b860-131">若要运行 A4SWIFT 清理工具</span><span class="sxs-lookup"><span data-stu-id="6b860-131">To run the A4SWIFT cleanup tool</span></span>  
  
1. <span data-ttu-id="6b860-132">在运行之前 A4SWIFT 清理工具，取消部署任何 A4SWIFT 默认程序集是指任何项目。</span><span class="sxs-lookup"><span data-stu-id="6b860-132">Prior to running the A4SWIFT cleanup tool, undeploy any project that refers to any of the A4SWIFT default assemblies.</span></span>  
  
2. <span data-ttu-id="6b860-133">打开命令提示符，并将移动到\<*驱动器*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools。</span><span class="sxs-lookup"><span data-stu-id="6b860-133">Open a command prompt and move to \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools.</span></span>  
  
3. <span data-ttu-id="6b860-134">类型**A4SWIFTCleanupTool.exe** ，然后按**ENTER**。</span><span class="sxs-lookup"><span data-stu-id="6b860-134">Type **A4SWIFTCleanupTool.exe** and then press **ENTER**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6b860-135">在最初运行 A4SWIFTCleanupTool.exe 时，该工具显示帮助屏幕，并提示您输入参数。</span><span class="sxs-lookup"><span data-stu-id="6b860-135">When you initially run A4SWIFTCleanupTool.exe, the tool displays a help screen, and prompts you to enter a parameter.</span></span> <span data-ttu-id="6b860-136">该工具将不运行，直到输入参数。</span><span class="sxs-lookup"><span data-stu-id="6b860-136">The tool will not run until you enter the parameter.</span></span>  
  
4. <span data-ttu-id="6b860-137">根据您希望该工具执行的操作，按以下项之一，然后按**ENTER**:</span><span class="sxs-lookup"><span data-stu-id="6b860-137">Depending upon the actions that you want the tool to take, press one of the following keys, and then press **ENTER**:</span></span>  
  
   - <span data-ttu-id="6b860-138">**0**的执行 （默认值） 无操作</span><span class="sxs-lookup"><span data-stu-id="6b860-138">**0** for no actions taken (the default)</span></span>  
  
   - <span data-ttu-id="6b860-139">**1**若要删除的计算机上，包括虚拟目录和注册表设置的所有本地 A4SWIFT 资源</span><span class="sxs-lookup"><span data-stu-id="6b860-139">**1** to remove all the local A4SWIFT resources on the computer, including the virtual directory and registry settings</span></span>  
  
   - <span data-ttu-id="6b860-140">**2**若要删除的 BizTalk Server 组中，包括 Sharepoint Web 文件夹、 FIN 消息模板、 BRE 策略和词汇、 BizTalk 项目和 A4SWIFT 数据库上的所有共享的 A4SWIFT 资源</span><span class="sxs-lookup"><span data-stu-id="6b860-140">**2** to remove all the shared A4SWIFT resources on the BizTalk Server group, including Sharepoint Web folders, FIN message templates, BRE policies and vocabularies, BizTalk artifacts, and the A4SWIFT database</span></span>  
  
   - <span data-ttu-id="6b860-141">**3**若要删除所有本地和共享资源</span><span class="sxs-lookup"><span data-stu-id="6b860-141">**3** to remove all the local and shared resources</span></span>  
  
   - <span data-ttu-id="6b860-142">**4**若要删除所有本地和共享资源并卸载[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]产品。</span><span class="sxs-lookup"><span data-stu-id="6b860-142">**4** to remove all the local and shared resources and uninstall the [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] product.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b860-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b860-143">See Also</span></span>  
 [<span data-ttu-id="6b860-144">工具</span><span class="sxs-lookup"><span data-stu-id="6b860-144">Tools</span></span>](../../adapters-and-accelerators/accelerator-swift/tools.md)