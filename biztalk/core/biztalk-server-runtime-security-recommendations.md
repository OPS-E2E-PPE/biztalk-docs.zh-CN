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
ms.openlocfilehash: b1e452a7cf78f63ac128064620db3084e91946fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357873"
---
# <a name="biztalk-server-runtime-security-recommendations"></a><span data-ttu-id="66c94-102">BizTalk Server 运行时安全建议</span><span class="sxs-lookup"><span data-stu-id="66c94-102">BizTalk Server Runtime Security Recommendations</span></span>
<span data-ttu-id="66c94-103">必须在你想要接收、 发送、 处理和跟踪消息的所有计算机上安装 BizTalk Server 运行时或引擎。</span><span class="sxs-lookup"><span data-stu-id="66c94-103">You must install the BizTalk Server runtime, or engine, on all the computers from which you want to receive, send, process, and track messages.</span></span> <span data-ttu-id="66c94-104">换而言之，你必须在其中创建 BizTalk 主机实例 （处理服务器） 的任何计算机上安装运行的时组件。</span><span class="sxs-lookup"><span data-stu-id="66c94-104">In other words, you must install the run time components on any computer where you create a BizTalk Host instance (processing servers).</span></span> <span data-ttu-id="66c94-105">建议您遵循这些准则以保护和部署你的环境中的 BizTalk Server 运行时。</span><span class="sxs-lookup"><span data-stu-id="66c94-105">It is recommended you follow these guidelines for securing and deploying the BizTalk Server runtime in your environment.</span></span>  
  
- <span data-ttu-id="66c94-106">确保具有最低安全用户权限来执行 BizTalk 运行时任务。</span><span class="sxs-lookup"><span data-stu-id="66c94-106">Ensure you have the Minimum Security User Rights to perform BizTalk runtime tasks.</span></span> <span data-ttu-id="66c94-107">有关最低安全用户权限的详细信息，请参阅[最低安全用户权限](../core/minimum-security-user-rights.md)。</span><span class="sxs-lookup"><span data-stu-id="66c94-107">For more information about the Minimum Security User Rights, see [Minimum Security User Rights](../core/minimum-security-user-rights.md).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="66c94-108">BizTalk 配置会为帐户授予执行其任务所需的最低权限。</span><span class="sxs-lookup"><span data-stu-id="66c94-108">BizTalk Configuration gives the accounts the minimum permissions they need to perform their tasks.</span></span>  
  
- <span data-ttu-id="66c94-109">每个主机实例的服务帐户必须具有日志作为服务运行该主机实例的计算机上的权限。</span><span class="sxs-lookup"><span data-stu-id="66c94-109">The service account for each host instance must have log on as service permissions on the computer where the host instance runs.</span></span>  
  
- <span data-ttu-id="66c94-110">仅在主机的服务帐户有权访问与主机相关的 MessageBox 数据，只有这些服务可以发布到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="66c94-110">Only the service account(s) for a host have access to MessageBox data related to a host and only these services can post to the MessageBox.</span></span> <span data-ttu-id="66c94-111">为了尽量减少信息泄露攻击的可能性，您不应为多个主机使用相同的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="66c94-111">To minimize the potential for information disclosure attacks, you should not use the same service account for more than one host.</span></span>  
  
- <span data-ttu-id="66c94-112">处理服务器 （不承载跟踪的主机） 只需连接到 MessageBox 和管理数据库和主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="66c94-112">Processing servers (hosts that do not host tracking) only need to connect to the MessageBox and Management databases, and the master secret server.</span></span> <span data-ttu-id="66c94-113">如果使用 Internet 协议安全 (IPSec)，可以限制到这两个数据库的处理服务器与主密钥服务器的访问权限。</span><span class="sxs-lookup"><span data-stu-id="66c94-113">If you use Internet Protocol security (IPSec), you can restrict the access of the processing servers to these two databases and the master secret server.</span></span>  
  
- <span data-ttu-id="66c94-114">相同的 BizTalk 主机中运行的所有组件都具有与主机相同的信任级别。</span><span class="sxs-lookup"><span data-stu-id="66c94-114">All components running within the same BizTalk Host have the same level of trust as the host.</span></span> <span data-ttu-id="66c94-115">它是信任的由 BizTalk 管理员，以确定哪些组件应在同一主机下运行，因此，共享相同级别。</span><span class="sxs-lookup"><span data-stu-id="66c94-115">It is up to the BizTalk administrator to determine which components should run under the same host, and therefore, share the same level of trust.</span></span> <span data-ttu-id="66c94-116">BizTalk 可确保只有 BizTalk 管理员安装的程序集运行 BizTalk 主机中。</span><span class="sxs-lookup"><span data-stu-id="66c94-116">BizTalk makes sure that only assemblies installed by BizTalk administrators run in a BizTalk Host.</span></span> <span data-ttu-id="66c94-117">如果你想要进一步限制 BizTalk 可使用的例如，如果你想要将 BizTalk 仅运行特定供应商签署的程序集或验证业务流程的强名称签名限制为可以使用[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]代码访问安全机制。</span><span class="sxs-lookup"><span data-stu-id="66c94-117">If you want to create further restrictions as to what assemblies BizTalk uses, for example, if you want to restrict BizTalk only to run assemblies signed by a particular vendor or validate the strong name signature for an orchestration, you can use the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Code Access Security Mechanism.</span></span> <span data-ttu-id="66c94-118">有关 Microsoft MSDN 网站上的详细信息[ http://go.microsoft.com/fwlink/?LinkId=60947 ](http://go.microsoft.com/fwlink/?LinkId=60947)。</span><span class="sxs-lookup"><span data-stu-id="66c94-118">For more information about the Microsoft MSDN Web site at [http://go.microsoft.com/fwlink/?LinkId=60947](http://go.microsoft.com/fwlink/?LinkId=60947).</span></span>  
  
- <span data-ttu-id="66c94-119">发布消息的授权粒度处于 BizTalk 主机级别。</span><span class="sxs-lookup"><span data-stu-id="66c94-119">The authorization granularity for posting messages is at the BizTalk Host level.</span></span> <span data-ttu-id="66c94-120">换而言之，如果有多个业务流程或适配器相同的 BizTalk 主机中运行，你不能限制一个特定的业务流程接收消息发送到主机。</span><span class="sxs-lookup"><span data-stu-id="66c94-120">In other words, if you have multiple orchestrations or adapters running within the same BizTalk Host, you cannot restrict one specific orchestration to receive messages sent to the host.</span></span>  
  
- <span data-ttu-id="66c94-121">当主机无权收到一条消息时，主机会将消息放置在其挂起队列。</span><span class="sxs-lookup"><span data-stu-id="66c94-121">When a host is not authorized to receive a message, the host places the message in its suspended queue.</span></span> <span data-ttu-id="66c94-122">默认情况下，如果接收适配器和在同一主机中运行业务流程、 业务流程可以读取主机的挂起的队列。</span><span class="sxs-lookup"><span data-stu-id="66c94-122">By default, when receive adapters and orchestrations are running in the same host, the orchestration can read the suspended queue of the host.</span></span> <span data-ttu-id="66c94-123">这样，它将使业务流程可以提取由于授权失败而被 BizTalk 挂起的消息。</span><span class="sxs-lookup"><span data-stu-id="66c94-123">It is then possible for an orchestration to pick up a message that BizTalk suspended due to authorization failure.</span></span> <span data-ttu-id="66c94-124">因此，建议不运行业务流程和接收适配器在同一主机中。</span><span class="sxs-lookup"><span data-stu-id="66c94-124">Therefore, it is recommended you do not run orchestrations and receive adapters in the same host.</span></span>  
  
- <span data-ttu-id="66c94-125">主机实例是特定计算机上运行的 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="66c94-125">Host instances are Windows services running on a specific computer.</span></span> <span data-ttu-id="66c94-126">若要创建的主机实例，您必须是 BizTalk 管理员并且想要创建该主机实例，因为 BizTalk 需要创建要与该主机实例相对应的 Windows 服务的计算机上的 Windows 管理员。</span><span class="sxs-lookup"><span data-stu-id="66c94-126">In order to create a host instance, you must be both a BizTalk administrator and a Windows administrator on the computer where you want to create the host instance, as BizTalk creates a Windows service to correspond to the host instance.</span></span>  
  
- <span data-ttu-id="66c94-127">当 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]生成一个程序集，它使用的集成开发环境 (IDE) 生成的自定义密钥。</span><span class="sxs-lookup"><span data-stu-id="66c94-127">When Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] generates an assembly, it uses a custom key generated by the Integrated Developer Environment (IDE).</span></span> <span data-ttu-id="66c94-128">如果你的环境需要使用特定密钥进行签名的所有程序集，你必须配置为所有开发计算机 IDE 使用该密钥，或者使用延迟签名的程序集...</span><span class="sxs-lookup"><span data-stu-id="66c94-128">If your environment requires you to sign all assemblies with a specific key, you must either configure the IDE for all development computers to use that key or use delay signing of assemblies..</span></span>  
  
- <span data-ttu-id="66c94-129">接收和发送管道中的所有组件都尝试保持较低的内存占用量。</span><span class="sxs-lookup"><span data-stu-id="66c94-129">All the components in the receive and send pipelines try to keep the memory footprint low.</span></span> <span data-ttu-id="66c94-130">数据大小超过特定阈值时，这些组件流式传输到磁盘的临时文件夹 （%TEMP%) 中的数据。</span><span class="sxs-lookup"><span data-stu-id="66c94-130">When the data is larger than a particular threshold, these components stream data to disk in the temporary folder (%TEMP%).</span></span> <span data-ttu-id="66c94-131">必须确保主机实例的服务帐户的临时文件夹具有正确的任意访问控制列表 (Dacl)，以便只有该服务帐户可以读取这些文件。</span><span class="sxs-lookup"><span data-stu-id="66c94-131">You must ensure the temporary folders for the service accounts for the host instances have proper discretionary access control lists (DACLs), so that only the service account can read these files.</span></span> <span data-ttu-id="66c94-132">你还必须确保临时文件夹具有足够的空间来存储可能很大的文件。</span><span class="sxs-lookup"><span data-stu-id="66c94-132">You must also ensure the temporary folder have room to store potentially large files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66c94-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="66c94-133">See Also</span></span>  
 <span data-ttu-id="66c94-134">[管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md) </span><span class="sxs-lookup"><span data-stu-id="66c94-134">[Managing BizTalk Server Security](../core/managing-biztalk-server-security.md) </span></span>  
 <span data-ttu-id="66c94-135">[用于处理服务器的端口](../core/ports-for-the-processing-servers.md) </span><span class="sxs-lookup"><span data-stu-id="66c94-135">[Ports for the Processing Servers](../core/ports-for-the-processing-servers.md) </span></span>  
 <span data-ttu-id="66c94-136">[BizTalk Server 部署的安全建议](../core/security-recommendations-for-a-biztalk-server-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="66c94-136">[Security Recommendations for a BizTalk Server Deployment](../core/security-recommendations-for-a-biztalk-server-deployment.md) </span></span>  
 [<span data-ttu-id="66c94-137">规划安全性</span><span class="sxs-lookup"><span data-stu-id="66c94-137">Planning for Security</span></span>](../core/planning-for-security.md)