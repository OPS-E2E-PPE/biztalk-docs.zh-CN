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
ms.openlocfilehash: 13f68268cc23255bb18128757b7ee879376572e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390025"
---
# <a name="deploy-tibco-rendezvous-ports-and-assemblies"></a><span data-ttu-id="b623a-103">部署 TIBCO Rendezvous 端口和程序集</span><span class="sxs-lookup"><span data-stu-id="b623a-103">Deploy TIBCO Rendezvous ports and assemblies</span></span>
  
## <a name="overview"></a><span data-ttu-id="b623a-104">概述</span><span class="sxs-lookup"><span data-stu-id="b623a-104">Overview</span></span>
<span data-ttu-id="b623a-105">使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以复制端口和目标计算机上的程序集。</span><span class="sxs-lookup"><span data-stu-id="b623a-105">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> <span data-ttu-id="b623a-106">向导导出的发送端口/接收位置配置为 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="b623a-106">The wizard exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="b623a-107">BizTalk Server 用于执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="b623a-107">You use BizTalk Server to do the following tasks:</span></span>  
  
- <span data-ttu-id="b623a-108">部署或 BizTalk 配置数据库中删除 BizTalk Server 程序集。</span><span class="sxs-lookup"><span data-stu-id="b623a-108">Deploy or remove BizTalk Server assemblies in a BizTalk Configuration database.</span></span>  
  
- <span data-ttu-id="b623a-109">安装或卸载的程序集在全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="b623a-109">Install or uninstall the assemblies in the global assembly cache (GAC).</span></span>  
  
- <span data-ttu-id="b623a-110">导入或导出 BizTalk Server 程序集绑定信息与绑定文件。</span><span class="sxs-lookup"><span data-stu-id="b623a-110">Import or export BizTalk Server assembly binding information to and from binding files.</span></span>  
  
  <span data-ttu-id="b623a-111">有关如何使用信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="b623a-111">For information about how to use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b623a-112">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器只要求在源 （开发） 计算机上安装 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="b623a-112">Microsoft BizTalk Adapter for TIBCO Rendezvous only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="b623a-113">Visual Studio 不需要在生产计算机上。</span><span class="sxs-lookup"><span data-stu-id="b623a-113">Visual Studio is not required on the production computer.</span></span>  

## <a name="confirm-your-setup"></a><span data-ttu-id="b623a-114">确认您的安装程序</span><span class="sxs-lookup"><span data-stu-id="b623a-114">Confirm your setup</span></span>

<span data-ttu-id="b623a-115">在使用之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要导入绑定文件，请确认，用于响应文件夹存在，并且它们是相同的新计算机上，或必须编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="b623a-115">Before you use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to import a binding file, confirm that the folders for the responses exist, and that they are identical on the new computer, or you must edit the binding file.</span></span>  
  
## <a name="clean-the-target-computer"></a><span data-ttu-id="b623a-116">清理目标计算机</span><span class="sxs-lookup"><span data-stu-id="b623a-116">Clean the target computer</span></span>
<span data-ttu-id="b623a-117">部署会覆盖接收位置配置。</span><span class="sxs-lookup"><span data-stu-id="b623a-117">Deployment overwrites the receive location configuration.</span></span> <span data-ttu-id="b623a-118">当将绑定文件 （和程序集） 部署的目标计算机上，发送端口和接收位置将替换 XML 绑定文件中所导入。</span><span class="sxs-lookup"><span data-stu-id="b623a-118">When you deploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
<span data-ttu-id="b623a-119">在导入之前，删除发送端口和接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="b623a-119">Before you import, remove send ports and receive locations bound to the orchestration.</span></span>  
  
<span data-ttu-id="b623a-120">如果没有在目标计算机上安装 Microsoft Visual Studio，则可以通过运行这些脚本删除端口：</span><span class="sxs-lookup"><span data-stu-id="b623a-120">If you do not have Microsoft Visual Studio installed on the target computer, you can remove the ports by running these scripts:</span></span>  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="b623a-121">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="b623a-121">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="b623a-122">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="b623a-122">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
<span data-ttu-id="b623a-123">例如，在命令提示符下运行：</span><span class="sxs-lookup"><span data-stu-id="b623a-123">For example, at a command prompt, run:</span></span>  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```
  
## <a name="next-steps"></a><span data-ttu-id="b623a-124">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b623a-124">Next steps</span></span>
[<span data-ttu-id="b623a-125">在您的业务流程中使用 BizTalk Server 异常处理</span><span class="sxs-lookup"><span data-stu-id="b623a-125">Use BizTalk Server Exception Handling in your orchestration</span></span>](../core/using-biztalk-server-exception-handling4.md)  
[<span data-ttu-id="b623a-126">故障排除</span><span class="sxs-lookup"><span data-stu-id="b623a-126">Troubleshoot</span></span>](../core/troubleshooting-tibco-rendezvous.md)