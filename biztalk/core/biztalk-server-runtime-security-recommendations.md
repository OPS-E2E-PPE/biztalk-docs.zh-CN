---
title: BizTalk Server 运行时安全建议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, runtime
- runtime, security
- discretionary access control lists (DACLs)
- DACLs
- .NET Framework Code Access Security Mechanism
ms.assetid: 1933789d-b79a-47ad-8f70-6f1e99bc2be0
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f929e49a7c7bc94456262ca07a42bfdc02eb1107
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974182"
---
# <a name="biztalk-server-runtime-security-recommendations"></a><span data-ttu-id="6dbd0-102">BizTalk Server 运行时安全建议</span><span class="sxs-lookup"><span data-stu-id="6dbd0-102">BizTalk Server Runtime Security Recommendations</span></span>
<span data-ttu-id="6dbd0-103">必须在用来接收、发送、处理和跟踪消息的所有计算机上安装 BizTalk Server 运行时或引擎。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-103">You must install the BizTalk Server runtime, or engine, on all the computers from which you want to receive, send, process, and track messages.</span></span> <span data-ttu-id="6dbd0-104">换句话说，必须在创建 BizTalk 主机实例（处理服务器）的所有计算机上安装运行时组件。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-104">In other words, you must install the run time components on any computer where you create a BizTalk Host instance (processing servers).</span></span> <span data-ttu-id="6dbd0-105">建议您遵循以下准则以确保您的环境中的 BizTalk Server 运行时的安全并对其进行部署：</span><span class="sxs-lookup"><span data-stu-id="6dbd0-105">It is recommended you follow these guidelines for securing and deploying the BizTalk Server runtime in your environment.</span></span>  
  
- <span data-ttu-id="6dbd0-106">确保使用最低的安全用户权限来执行 BizTalk 运行时任务。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-106">Ensure you have the Minimum Security User Rights to perform BizTalk runtime tasks.</span></span> <span data-ttu-id="6dbd0-107">有关最低安全用户权限的详细信息，请参阅[最低安全用户权限](../core/minimum-security-user-rights.md)。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-107">For more information about the Minimum Security User Rights, see [Minimum Security User Rights](../core/minimum-security-user-rights.md).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="6dbd0-108">BizTalk 配置会为帐户授予执行其任务所需的最低权限。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-108">BizTalk Configuration gives the accounts the minimum permissions they need to perform their tasks.</span></span>  
  
- <span data-ttu-id="6dbd0-109">各个主机实例的服务帐户必须对运行该主机实例的计算机具有“作为服务登录”权限。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-109">The service account for each host instance must have log on as service permissions on the computer where the host instance runs.</span></span>  
  
- <span data-ttu-id="6dbd0-110">只有主机的服务帐户才有权访问与主机相关的 MessageBox 数据，并且只有这些服务才能向 MessageBox 发布数据。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-110">Only the service account(s) for a host have access to MessageBox data related to a host and only these services can post to the MessageBox.</span></span> <span data-ttu-id="6dbd0-111">为了最大限度地减少信息泄露攻击的潜在可能性，不应为多个主机使用同一服务帐户。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-111">To minimize the potential for information disclosure attacks, you should not use the same service account for more than one host.</span></span>  
  
- <span data-ttu-id="6dbd0-112">处理服务器（不承载跟踪任务的主机）只需连接到 MessageBox 和管理数据库以及主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-112">Processing servers (hosts that do not host tracking) only need to connect to the MessageBox and Management databases, and the master secret server.</span></span> <span data-ttu-id="6dbd0-113">如果使用 Internet 协议安全性 (IPSec)，则可以将处理服务器限定为只能访问这两个数据库和主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-113">If you use Internet Protocol security (IPSec), you can restrict the access of the processing servers to these two databases and the master secret server.</span></span>  
  
- <span data-ttu-id="6dbd0-114">在同一 BizTalk 主机中运行的所有组件都具有与该主机相同的信任级别。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-114">All components running within the same BizTalk Host have the same level of trust as the host.</span></span> <span data-ttu-id="6dbd0-115">至于哪些组件应在同一主机下运行从而共享同一信任级别，这需要由 BizTalk 管理员来决定。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-115">It is up to the BizTalk administrator to determine which components should run under the same host, and therefore, share the same level of trust.</span></span> <span data-ttu-id="6dbd0-116">BizTalk 确保在 BizTalk 主机中只运行 BizTalk 管理员安装的程序集。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-116">BizTalk makes sure that only assemblies installed by BizTalk administrators run in a BizTalk Host.</span></span> <span data-ttu-id="6dbd0-117">若要进一步限制 BizTalk 可使用的程序集（例如，若要将 BizTalk 限制为只能运行特定供应商签署的程序集）或验证业务流程的强名称签名，可以使用 [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] 代码访问安全机制。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-117">If you want to create further restrictions as to what assemblies BizTalk uses, for example, if you want to restrict BizTalk only to run assemblies signed by a particular vendor or validate the strong name signature for an orchestration, you can use the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Code Access Security Mechanism.</span></span> <span data-ttu-id="6dbd0-118">有关 Microsoft MSDN 网站上的详细信息[ http://go.microsoft.com/fwlink/?LinkId=60947 ](http://go.microsoft.com/fwlink/?LinkId=60947)。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-118">For more information about the Microsoft MSDN Web site at [http://go.microsoft.com/fwlink/?LinkId=60947](http://go.microsoft.com/fwlink/?LinkId=60947).</span></span>  
  
- <span data-ttu-id="6dbd0-119">发布消息的授权粒度处于 BizTalk 主机级别上。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-119">The authorization granularity for posting messages is at the BizTalk Host level.</span></span> <span data-ttu-id="6dbd0-120">换句话说，如果在同一 BizTalk 主机中运行有多个业务流程或适配器，则无法限制为由某个特定的业务流程来接收发送到该主机的消息。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-120">In other words, if you have multiple orchestrations or adapters running within the same BizTalk Host, you cannot restrict one specific orchestration to receive messages sent to the host.</span></span>  
  
- <span data-ttu-id="6dbd0-121">如果主机未获得接收消息的授权，则该主机将把消息放在其挂起队列中。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-121">When a host is not authorized to receive a message, the host places the message in its suspended queue.</span></span> <span data-ttu-id="6dbd0-122">默认情况下，如果接收适配器和业务流程运行在同一主机中，则业务流程可以读取主机的挂起队列。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-122">By default, when receive adapters and orchestrations are running in the same host, the orchestration can read the suspended queue of the host.</span></span> <span data-ttu-id="6dbd0-123">这样，业务流程就可以提取由于授权失败而被 BizTalk 挂起的消息。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-123">It is then possible for an orchestration to pick up a message that BizTalk suspended due to authorization failure.</span></span> <span data-ttu-id="6dbd0-124">因此，建议不要在同一主机中运行业务流程和接收适配器。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-124">Therefore, it is recommended you do not run orchestrations and receive adapters in the same host.</span></span>  
  
- <span data-ttu-id="6dbd0-125">主机实例是在特定计算机中运行的 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-125">Host instances are Windows services running on a specific computer.</span></span> <span data-ttu-id="6dbd0-126">若要创建主机实例，您必须为要在其中创建主机实例的计算机的 BizTalk 管理员和 Windows 管理员，因为 BizTalk 需要创建与主机实例对应的 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-126">In order to create a host instance, you must be both a BizTalk administrator and a Windows administrator on the computer where you want to create the host instance, as BizTalk creates a Windows service to correspond to the host instance.</span></span>  
  
- <span data-ttu-id="6dbd0-127">当 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 生成程序集时，它会使用集成开发人员环境 (IDE) 生成的自定义密钥。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-127">When Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] generates an assembly, it uses a custom key generated by the Integrated Developer Environment (IDE).</span></span> <span data-ttu-id="6dbd0-128">如果你的环境需要使用特定密钥进行签名的所有程序集，你必须配置为所有开发计算机 IDE 使用该密钥，或者使用延迟签名的程序集...</span><span class="sxs-lookup"><span data-stu-id="6dbd0-128">If your environment requires you to sign all assemblies with a specific key, you must either configure the IDE for all development computers to use that key or use delay signing of assemblies..</span></span>  
  
- <span data-ttu-id="6dbd0-129">接收和发送管道中的所有组件都会试图保持较低的内存占用率。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-129">All the components in the receive and send pipelines try to keep the memory footprint low.</span></span> <span data-ttu-id="6dbd0-130">当数据大于特定阈值时，这些组件会将数据保存到磁盘上的临时文件夹 (%TEMP%) 中。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-130">When the data is larger than a particular threshold, these components stream data to disk in the temporary folder (%TEMP%).</span></span> <span data-ttu-id="6dbd0-131">必须确保主机实例的服务帐户的临时文件夹具有正确的任意访问控制列表 (DACL)，以便只有该服务帐户才能读取这些文件。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-131">You must ensure the temporary folders for the service accounts for the host instances have proper discretionary access control lists (DACLs), so that only the service account can read these files.</span></span> <span data-ttu-id="6dbd0-132">还必须确保临时文件夹具有足够的空间来存储可能的大型文件。</span><span class="sxs-lookup"><span data-stu-id="6dbd0-132">You must also ensure the temporary folder have room to store potentially large files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dbd0-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="6dbd0-133">See Also</span></span>  
 <span data-ttu-id="6dbd0-134">[管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md) </span><span class="sxs-lookup"><span data-stu-id="6dbd0-134">[Managing BizTalk Server Security](../core/managing-biztalk-server-security.md) </span></span>  
 <span data-ttu-id="6dbd0-135">[用于处理服务器的端口](../core/ports-for-the-processing-servers.md) </span><span class="sxs-lookup"><span data-stu-id="6dbd0-135">[Ports for the Processing Servers](../core/ports-for-the-processing-servers.md) </span></span>  
 <span data-ttu-id="6dbd0-136">[BizTalk Server 部署的安全建议](../core/security-recommendations-for-a-biztalk-server-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="6dbd0-136">[Security Recommendations for a BizTalk Server Deployment](../core/security-recommendations-for-a-biztalk-server-deployment.md) </span></span>  
 [<span data-ttu-id="6dbd0-137">规划安全性</span><span class="sxs-lookup"><span data-stu-id="6dbd0-137">Planning for Security</span></span>](../core/planning-for-security.md)