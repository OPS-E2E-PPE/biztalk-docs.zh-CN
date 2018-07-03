---
title: 阅读已知问题安装 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 245379f2-4048-4803-83ea-38dc23eb1a81
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4bc572cc18ca7d9d5515fe9f189287df5d1440f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022947"
---
# <a name="read-the-installation-known-issues"></a><span data-ttu-id="51059-102">阅读安装的已知问题</span><span class="sxs-lookup"><span data-stu-id="51059-102">Read the installation known issues</span></span>
[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]<span data-ttu-id="51059-103"> 具有以下各节中列出的已知的问题。</span><span class="sxs-lookup"><span data-stu-id="51059-103"> have known issues listed in the following sections.</span></span>  
  
## <a name="swift-does-not-support-stress-testing-on-integration-test-bed-itb-and-swiftnet-stub-environment"></a><span data-ttu-id="51059-104">SWIFT 不支持压力测试集成测试平台 (ITB) 和 SWIFTNet 存根 （stub） 环境</span><span class="sxs-lookup"><span data-stu-id="51059-104">SWIFT Does Not Support Stress Testing on Integration Test Bed (ITB) and SWIFTNet Stub Environment</span></span>  
 <span data-ttu-id="51059-105">ITB 不在吞吐量方面提供服务级别协议 (SLA)，并且无法保证数据是完全传输还是一致。</span><span class="sxs-lookup"><span data-stu-id="51059-105">The ITB does not provide Service Level Agreement (SLA) in terms of throughput, and cannot guarantee that data is completely transmitted or consistent.</span></span> <span data-ttu-id="51059-106">应在试验环境中实现对生产网络进行压力测试。</span><span class="sxs-lookup"><span data-stu-id="51059-106">You should stress test your implementation on the production network in the Pilot environment.</span></span>  
  
 <span data-ttu-id="51059-107">此外，必须确保所有的节点 （服务器、 线条和带宽） 进行正确配置以避免丢失任何数据。</span><span class="sxs-lookup"><span data-stu-id="51059-107">Additionally, you must ensure that all of the nodes (server, lines, and bandwidth) are properly configured to avoid any data loss.</span></span> <span data-ttu-id="51059-108">以下是典型的示例执行次数：</span><span class="sxs-lookup"><span data-stu-id="51059-108">Following are typical sample throughputs:</span></span>  
  
- <span data-ttu-id="51059-109">交互/Fileact 发送用量较大的计算机下： 20 消息/分钟</span><span class="sxs-lookup"><span data-stu-id="51059-109">Interact/Fileact Send under stressed computer: 20 messages/minute</span></span>  
  
- <span data-ttu-id="51059-110">交互/Fileact 接收用量较大的计算机下： 300-400 消息/分钟</span><span class="sxs-lookup"><span data-stu-id="51059-110">Interact/Fileact Receive under stressed computer: 300-400 messages/minute</span></span>  
  
  <span data-ttu-id="51059-111">有关详细信息，请参阅 SWIFT 文档。</span><span class="sxs-lookup"><span data-stu-id="51059-111">For more information, see your SWIFT documentation.</span></span>  
  
## <a name="messages-not-pushed-when-queue-is-open"></a><span data-ttu-id="51059-112">当队列处于打开状态时，未推送的消息</span><span class="sxs-lookup"><span data-stu-id="51059-112">Messages Not Pushed When Queue Is Open</span></span>  
 <span data-ttu-id="51059-113">使用时交互或 FileAct 存储和转发 (SnF) 模式下，如果与队列会话处于打开状态，并且不推送消息，然后必须重新启动 SNLreceiver.exe。</span><span class="sxs-lookup"><span data-stu-id="51059-113">When you are using InterAct or FileAct Store and Forward (SnF) mode, if the session with the queue is open and messages are not being pushed, then you must restart SNLreceiver.exe.</span></span> <span data-ttu-id="51059-114">这样可避免 SWIFT 可能偶尔发生的问题。</span><span class="sxs-lookup"><span data-stu-id="51059-114">This avoids an issue with SWIFT that can occur occasionally.</span></span>  
  
## <a name="you-must-use-cdata-when-passing-characters-like--and--in-message"></a><span data-ttu-id="51059-115">您必须使用 CDATA 时将传递字符如"<"和"&"消息中</span><span class="sxs-lookup"><span data-stu-id="51059-115">You Must Use CDATA when Passing Characters like "<" and "&" in message</span></span>  
 <span data-ttu-id="51059-116">有关不应由 XML 分析器进行分析的文本数据使用 CDATA 的术语。</span><span class="sxs-lookup"><span data-stu-id="51059-116">The term CDATA is used about text data that should not be parsed by the XML parser.</span></span>  <span data-ttu-id="51059-117">字符如"<"和"&"是非法的 XML 元素中。</span><span class="sxs-lookup"><span data-stu-id="51059-117">Characters like "<" and "&" are illegal in XML elements.</span></span> <span data-ttu-id="51059-118">"<"将生成错误，因为分析器将其解释为新元素的开头。</span><span class="sxs-lookup"><span data-stu-id="51059-118">"<" will generate an error because the parser interprets it as the start of a new element.</span></span> <span data-ttu-id="51059-119">"&"将生成错误，因为分析器将其解释为字符实体的开头。</span><span class="sxs-lookup"><span data-stu-id="51059-119">"&" will generate an error because the parser interprets it as the start of a character entity.</span></span> <span data-ttu-id="51059-120">分析器将忽略 CDATA 节内的所有内容。</span><span class="sxs-lookup"><span data-stu-id="51059-120">Everything inside a CDATA section is ignored by the parser.</span></span> <span data-ttu-id="51059-121">CDATA 部分开头介绍"\<！ [CDATA ["结尾"]]\>"</span><span class="sxs-lookup"><span data-stu-id="51059-121">A CDATA section starts with "\<![CDATA[" and ends with "]]\>"</span></span>  
  
## <a name="you-must-use-passthrough-pipelines-with-payload-only-mode"></a><span data-ttu-id="51059-122">必须使用仅限有效负载的模式下使用直通管道</span><span class="sxs-lookup"><span data-stu-id="51059-122">You Must Use Passthrough Pipelines with Payload-Only Mode</span></span>  
 <span data-ttu-id="51059-123">InterAct 适配器使用仅限有效负载的模式下，如果您必须使用直通管道在这两个发送和接收端口，如果不使用自定义管道。</span><span class="sxs-lookup"><span data-stu-id="51059-123">If you are using payload-only mode for the InterAct adapter, you must use pass-through pipelines on both the send and receive ports if you are not using custom pipelines.</span></span>  
  
## <a name="multiple-security-contexts-not-created-swiftnet-stub-computer"></a><span data-ttu-id="51059-124">未创建 （SWIFTNet 存根 （stub） 计算机） 的多个安全上下文</span><span class="sxs-lookup"><span data-stu-id="51059-124">Multiple Security Contexts Not Created (SWIFTNet Stub Computer)</span></span>  
 <span data-ttu-id="51059-125">SWIFTNet 存根 （stub） 在计算机上，多个安全上下文的不被创建不同的发送端口。</span><span class="sxs-lookup"><span data-stu-id="51059-125">On a SWIFTNet stub computer, multiple security contexts are not created for different send ports.</span></span> <span data-ttu-id="51059-126">ITB 上创建多个安全上下文。</span><span class="sxs-lookup"><span data-stu-id="51059-126">Multiple security contexts are created on ITB.</span></span>