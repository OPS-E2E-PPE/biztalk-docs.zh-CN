---
title: "读取的已知问题的安装 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 245379f2-4048-4803-83ea-38dc23eb1a81
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6641e7974a0e1872b71794af6553d708e9619dd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="read-the-installation-known-issues"></a><span data-ttu-id="b6549-102">读取安装的已知问题</span><span class="sxs-lookup"><span data-stu-id="b6549-102">Read the installation known issues</span></span>
[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]<span data-ttu-id="b6549-103">具有下列部分中列出已知的问题。</span><span class="sxs-lookup"><span data-stu-id="b6549-103"> have known issues listed in the following sections.</span></span>  
  
## <a name="swift-does-not-support-stress-testing-on-integration-test-bed-itb-and-swiftnet-stub-environment"></a><span data-ttu-id="b6549-104">SWIFT 不支持集成的测试平台上 (ITB) 和 SWIFTNet 存根 （stub） 环境中测试的压力</span><span class="sxs-lookup"><span data-stu-id="b6549-104">SWIFT Does Not Support Stress Testing on Integration Test Bed (ITB) and SWIFTNet Stub Environment</span></span>  
 <span data-ttu-id="b6549-105">ITB 不会根据吞吐量，提供服务级别协议 (SLA)，并且不能保证数据是完全传输还是一致。</span><span class="sxs-lookup"><span data-stu-id="b6549-105">The ITB does not provide Service Level Agreement (SLA) in terms of throughput, and cannot guarantee that data is completely transmitted or consistent.</span></span> <span data-ttu-id="b6549-106">你应在生产环境实现网络在试验环境中的压力测试。</span><span class="sxs-lookup"><span data-stu-id="b6549-106">You should stress test your implementation on the production network in the Pilot environment.</span></span>  
  
 <span data-ttu-id="b6549-107">此外，你必须确保对所有节点 （服务器、 线条和带宽） 将进行正确配置，为了避免丢失任何数据。</span><span class="sxs-lookup"><span data-stu-id="b6549-107">Additionally, you must ensure that all of the nodes (server, lines, and bandwidth) are properly configured to avoid any data loss.</span></span> <span data-ttu-id="b6549-108">以下是典型示例吞吐量：</span><span class="sxs-lookup"><span data-stu-id="b6549-108">Following are typical sample throughputs:</span></span>  
  
-   <span data-ttu-id="b6549-109">交互/Fileact 发送重音计算机下： 20 的邮件/分钟</span><span class="sxs-lookup"><span data-stu-id="b6549-109">Interact/Fileact Send under stressed computer: 20 messages/minute</span></span>  
  
-   <span data-ttu-id="b6549-110">交互/Fileact 接收重音计算机下： 每分钟 300-400 消息数</span><span class="sxs-lookup"><span data-stu-id="b6549-110">Interact/Fileact Receive under stressed computer: 300-400 messages/minute</span></span>  
  
 <span data-ttu-id="b6549-111">有关详细信息，请参阅 SWIFT 文档。</span><span class="sxs-lookup"><span data-stu-id="b6549-111">For more information, see your SWIFT documentation.</span></span>  
  
## <a name="messages-not-pushed-when-queue-is-open"></a><span data-ttu-id="b6549-112">打开队列时未推送的消息</span><span class="sxs-lookup"><span data-stu-id="b6549-112">Messages Not Pushed When Queue Is Open</span></span>  
 <span data-ttu-id="b6549-113">如果你使用交互或 FileAct 应用商店和进 (SnF) 模式下，如果与队列会话保持打开状态，不被推送消息，然后你必须重启 SNLreceiver.exe。</span><span class="sxs-lookup"><span data-stu-id="b6549-113">When you are using InterAct or FileAct Store and Forward (SnF) mode, if the session with the queue is open and messages are not being pushed, then you must restart SNLreceiver.exe.</span></span> <span data-ttu-id="b6549-114">这样就避免了 SWIFT 可能偶尔发生的问题。</span><span class="sxs-lookup"><span data-stu-id="b6549-114">This avoids an issue with SWIFT that can occur occasionally.</span></span>  
  
## <a name="you-must-use-cdata-when-passing-characters-like--and--in-message"></a><span data-ttu-id="b6549-115">你必须使用 CDATA 时将传递字符，例如"<"和"&"消息中</span><span class="sxs-lookup"><span data-stu-id="b6549-115">You Must Use CDATA when Passing Characters like "<" and "&" in message</span></span>  
 <span data-ttu-id="b6549-116">CDATA 使用有关不应由 XML 分析器分析的文本数据的术语。</span><span class="sxs-lookup"><span data-stu-id="b6549-116">The term CDATA is used about text data that should not be parsed by the XML parser.</span></span>  <span data-ttu-id="b6549-117">字符，例如"<"和"&"在 XML 元素中是非法。</span><span class="sxs-lookup"><span data-stu-id="b6549-117">Characters like "<" and "&" are illegal in XML elements.</span></span> <span data-ttu-id="b6549-118">"<"将生成错误，因为分析器将其解释为新元素的开头。</span><span class="sxs-lookup"><span data-stu-id="b6549-118">"<" will generate an error because the parser interprets it as the start of a new element.</span></span> <span data-ttu-id="b6549-119">"&"将生成错误，因为分析器将其解释为字符实体的开头。</span><span class="sxs-lookup"><span data-stu-id="b6549-119">"&" will generate an error because the parser interprets it as the start of a character entity.</span></span> <span data-ttu-id="b6549-120">分析器会忽略所有内容在 CDATA 节内。</span><span class="sxs-lookup"><span data-stu-id="b6549-120">Everything inside a CDATA section is ignored by the parser.</span></span> <span data-ttu-id="b6549-121">CDATA 部分开头介绍"\<！ [CDATA ["和结束的"]]\>"</span><span class="sxs-lookup"><span data-stu-id="b6549-121">A CDATA section starts with "\<![CDATA[" and ends with "]]\>"</span></span>  
  
## <a name="you-must-use-passthrough-pipelines-with-payload-only-mode"></a><span data-ttu-id="b6549-122">你必须使用带有仅负载模式传递管道</span><span class="sxs-lookup"><span data-stu-id="b6549-122">You Must Use Passthrough Pipelines with Payload-Only Mode</span></span>  
 <span data-ttu-id="b6549-123">如果为交互适配器使用仅负载模式，必须传递管道使用这两个发送和接收端口，如果你不使用自定义管道。</span><span class="sxs-lookup"><span data-stu-id="b6549-123">If you are using payload-only mode for the InterAct adapter, you must use pass-through pipelines on both the send and receive ports if you are not using custom pipelines.</span></span>  
  
## <a name="multiple-security-contexts-not-created-swiftnet-stub-computer"></a><span data-ttu-id="b6549-124">未创建 （SWIFTNet 存根 （stub） 计算机） 的多个安全上下文</span><span class="sxs-lookup"><span data-stu-id="b6549-124">Multiple Security Contexts Not Created (SWIFTNet Stub Computer)</span></span>  
 <span data-ttu-id="b6549-125">SWIFTNet 存根 （stub） 在计算机上，多个安全上下文的不被创建不同发送端口。</span><span class="sxs-lookup"><span data-stu-id="b6549-125">On a SWIFTNet stub computer, multiple security contexts are not created for different send ports.</span></span> <span data-ttu-id="b6549-126">ITB 上创建多个安全上下文。</span><span class="sxs-lookup"><span data-stu-id="b6549-126">Multiple security contexts are created on ITB.</span></span>