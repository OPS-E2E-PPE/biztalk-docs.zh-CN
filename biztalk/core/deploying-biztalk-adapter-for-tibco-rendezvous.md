---
title: 用于 TIBCO Rendezvous 将绑定导入 |Microsoft Docs
description: 部署 TIBCO Rendezvous 应用程序在 BizTalk Server 中使用导入绑定功能的 BizTalk 适配器
ms.custom: ''
ms.date: 10/24/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec5751a9-0a08-4cf8-a3ef-e51e488a4180
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bb362afb23b165c31df34adf521be81f93a621f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994006"
---
# <a name="deploy-tibco-rendezvous-ports-and-assemblies"></a><span data-ttu-id="3b33b-103">部署 TIBCO Rendezvous 端口和程序集</span><span class="sxs-lookup"><span data-stu-id="3b33b-103">Deploy TIBCO Rendezvous ports and assemblies</span></span>
  
## <a name="overview"></a><span data-ttu-id="3b33b-104">概述</span><span class="sxs-lookup"><span data-stu-id="3b33b-104">Overview</span></span>
<span data-ttu-id="3b33b-105">使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可在目标计算机上复制端口和程序集。</span><span class="sxs-lookup"><span data-stu-id="3b33b-105">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> <span data-ttu-id="3b33b-106">该向导将发送端口/接收位置配置导出到一个 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="3b33b-106">The wizard exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="3b33b-107">您可以使用 BizTalk Server 来执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="3b33b-107">You use BizTalk Server to do the following tasks:</span></span>  
  
- <span data-ttu-id="3b33b-108">将 BizTalk Server 程序集部署到 BizTalk 配置数据库中或从其删除。</span><span class="sxs-lookup"><span data-stu-id="3b33b-108">Deploy or remove BizTalk Server assemblies in a BizTalk Configuration database.</span></span>  
  
- <span data-ttu-id="3b33b-109">将程序集安装在全局程序集缓存 (GAC) 中或从其卸载。</span><span class="sxs-lookup"><span data-stu-id="3b33b-109">Install or uninstall the assemblies in the global assembly cache (GAC).</span></span>  
  
- <span data-ttu-id="3b33b-110">将 BizTalk Server 程序集绑定信息导入到绑定文件或从其导出。</span><span class="sxs-lookup"><span data-stu-id="3b33b-110">Import or export BizTalk Server assembly binding information to and from binding files.</span></span>  
  
  <span data-ttu-id="3b33b-111">有关如何使用信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="3b33b-111">For information about how to use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b33b-112">TIBCO Rendezvous 的 Microsoft BizTalk 适配器只要求在源（开发）计算机上具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="3b33b-112">Microsoft BizTalk Adapter for TIBCO Rendezvous only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="3b33b-113">在生产计算机上不要求使用 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="3b33b-113">Visual Studio is not required on the production computer.</span></span>  

## <a name="confirm-your-setup"></a><span data-ttu-id="3b33b-114">确认您的安装程序</span><span class="sxs-lookup"><span data-stu-id="3b33b-114">Confirm your setup</span></span>

<span data-ttu-id="3b33b-115">在使用之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要导入绑定文件，请确认，用于响应文件夹存在，并且它们是相同的新计算机上，或必须编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="3b33b-115">Before you use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to import a binding file, confirm that the folders for the responses exist, and that they are identical on the new computer, or you must edit the binding file.</span></span>  
  
## <a name="clean-the-target-computer"></a><span data-ttu-id="3b33b-116">清理目标计算机</span><span class="sxs-lookup"><span data-stu-id="3b33b-116">Clean the target computer</span></span>
<span data-ttu-id="3b33b-117">部署会覆盖接收位置配置。</span><span class="sxs-lookup"><span data-stu-id="3b33b-117">Deployment overwrites the receive location configuration.</span></span> <span data-ttu-id="3b33b-118">当将绑定文件 （和程序集） 部署的目标计算机上，发送端口和接收位置将替换 XML 绑定文件中所导入。</span><span class="sxs-lookup"><span data-stu-id="3b33b-118">When you deploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
<span data-ttu-id="3b33b-119">在导入之前，删除发送端口和接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="3b33b-119">Before you import, remove send ports and receive locations bound to the orchestration.</span></span>  
  
<span data-ttu-id="3b33b-120">如果没有在目标计算机上安装 Microsoft Visual Studio，则可以通过运行这些脚本删除端口：</span><span class="sxs-lookup"><span data-stu-id="3b33b-120">If you do not have Microsoft Visual Studio installed on the target computer, you can remove the ports by running these scripts:</span></span>  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="3b33b-121">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="3b33b-121">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="3b33b-122">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="3b33b-122">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
<span data-ttu-id="3b33b-123">例如，在命令提示符下运行：</span><span class="sxs-lookup"><span data-stu-id="3b33b-123">For example, at a command prompt, run:</span></span>  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```
  
## <a name="next-steps"></a><span data-ttu-id="3b33b-124">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3b33b-124">Next steps</span></span>
[<span data-ttu-id="3b33b-125">在您的业务流程中使用 BizTalk Server 异常处理</span><span class="sxs-lookup"><span data-stu-id="3b33b-125">Use BizTalk Server Exception Handling in your orchestration</span></span>](../core/using-biztalk-server-exception-handling4.md)  
[<span data-ttu-id="3b33b-126">故障排除</span><span class="sxs-lookup"><span data-stu-id="3b33b-126">Troubleshoot</span></span>](../core/troubleshooting-tibco-rendezvous.md)