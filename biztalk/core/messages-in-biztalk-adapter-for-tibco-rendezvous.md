---
title: TIBCO Rendezvous 适配器中的消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 12699550-22e7-4a11-a024-2302570970af
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 686b8f5764c0d4832770f777cdf65b5287bd848e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394511"
---
# <a name="messages-in-biztalk-adapter-for-tibco-rendezvous"></a><span data-ttu-id="0391a-102">用于 TIBCO Rendezvous 的 BizTalk 适配器中的消息</span><span class="sxs-lookup"><span data-stu-id="0391a-102">Messages in BizTalk Adapter for TIBCO Rendezvous</span></span>
<span data-ttu-id="0391a-103">用于 TIBCO Rendezvous 的 BizTalk 适配器提供之间的双向连接[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 TIBCO Rendezvous。</span><span class="sxs-lookup"><span data-stu-id="0391a-103">BizTalk Adapter for TIBCO Rendezvous provides bi-directional connectivity between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and TIBCO Rendezvous.</span></span> <span data-ttu-id="0391a-104">此适配器使用 TIBCO Rendezvous API 和 BizTalk 适配器框架 API 来提供紧密集成。</span><span class="sxs-lookup"><span data-stu-id="0391a-104">This adapter uses both the TIBCO Rendezvous API and the BizTalk Adapter Framework API to provide tight integration.</span></span>  
  
## <a name="about-tibco-rendezvous"></a><span data-ttu-id="0391a-105">有关 TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="0391a-105">About TIBCO Rendezvous</span></span>  
 <span data-ttu-id="0391a-106">TIBCO Rendezvous 是为企业应用程序集成 (EAI) 提供消息总线的程序。</span><span class="sxs-lookup"><span data-stu-id="0391a-106">TIBCO Rendezvous is a programs that provides a message bus for enterprise application integration (EAI).</span></span> <span data-ttu-id="0391a-107">TIBCO 提供消息传送 Api 在 C 中， C++、 Java、 Visual Basic 和 Microsoft.NET framework，若要接收 Microsoft Office Excel 工作表和所选的其他应用程序上的数据源。</span><span class="sxs-lookup"><span data-stu-id="0391a-107">TIBCO provides messaging APIs in C, C++, Java, Visual Basic and for the Microsoft .NET Framework to receive data feeds on Microsoft Office Excel worksheets and other applications of choice.</span></span> <span data-ttu-id="0391a-108">有关详细信息，请参阅[TIBCO Rendezvous 概念](../core/tibco-rendezvous-concepts.md)。</span><span class="sxs-lookup"><span data-stu-id="0391a-108">For more information, see [TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md).</span></span>  
  
## <a name="message-passing"></a><span data-ttu-id="0391a-109">消息传递</span><span class="sxs-lookup"><span data-stu-id="0391a-109">Message Passing</span></span>  
 <span data-ttu-id="0391a-110">消息传递的基本概念是相当简单：</span><span class="sxs-lookup"><span data-stu-id="0391a-110">The basic concept of message passing is fairly simple:</span></span>  
  
- <span data-ttu-id="0391a-111">消息具有单个主题，其中用句点分隔的元素组成。</span><span class="sxs-lookup"><span data-stu-id="0391a-111">A message has a single subject composed of elements separated by periods.</span></span> <span data-ttu-id="0391a-112">一条消息发送到单个的 Rendezvous 后台程序，尽管可能最终需要广播其他守护程序。</span><span class="sxs-lookup"><span data-stu-id="0391a-112">A message is sent to a single Rendezvous daemon, although it might eventually be broadcast onto other daemons.</span></span>  
  
- <span data-ttu-id="0391a-113">侦听器宣布其感兴趣的后台程序 （使用基本的通配符工具） 的主题。</span><span class="sxs-lookup"><span data-stu-id="0391a-113">A listener announces its subjects of interest to a daemon (with a basic wildcard facility).</span></span> <span data-ttu-id="0391a-114">如果两个守护程序连接到对方，或者它们实际上是同一个守护程序拥有匹配主题的消息传递到它。</span><span class="sxs-lookup"><span data-stu-id="0391a-114">Messages that have matching subjects are delivered to it if the two daemons are connected to each other, or are indeed the same daemon.</span></span>  
  
  <span data-ttu-id="0391a-115">重要"的企业"功能分层到此，如果所需-，容错/可靠或 Certified 选项可能进行-所有已通过基础的基本消息实现。</span><span class="sxs-lookup"><span data-stu-id="0391a-115">Significant "Enterprise" functionality is layered onto this if desired--with Fault Tolerance/Reliable or Certified options possible--all implemented through the underlying basic messages.</span></span>  
  
  <span data-ttu-id="0391a-116">消息本身可看作是键入的名称-值字段或数字-值字段 （在消息中的两个标识机制可以混合和匹配的某些限制）。</span><span class="sxs-lookup"><span data-stu-id="0391a-116">The messages themselves can be viewed as typed name-value fields or number-value fields (the two identification mechanisms in a message can mix and match with certain restrictions).</span></span> <span data-ttu-id="0391a-117">消息本身可包含子消息，可以包含子消息。</span><span class="sxs-lookup"><span data-stu-id="0391a-117">A message itself can contain sub-messages, which can contain sub-messages.</span></span>  
  
  <span data-ttu-id="0391a-118">使用者名称包含一个或多个由圆点字符 （句点） 分隔的元素。</span><span class="sxs-lookup"><span data-stu-id="0391a-118">Subject names consist of one or more elements separated by dot characters (periods).</span></span> <span data-ttu-id="0391a-119">元素实现的信息的结构反映在应用程序系统中的主题名称层次结构。</span><span class="sxs-lookup"><span data-stu-id="0391a-119">The elements implement a subject name hierarchy that reflects the structure of information in an application system.</span></span> <span data-ttu-id="0391a-120">以下字符串是有效的主题名称的示例：</span><span class="sxs-lookup"><span data-stu-id="0391a-120">The following strings are examples of valid subject names:</span></span>  
  
- <span data-ttu-id="0391a-121">运行。主页</span><span class="sxs-lookup"><span data-stu-id="0391a-121">RUN.HOME</span></span>  
  
- <span data-ttu-id="0391a-122">RUN.for.Elected_Office</span><span class="sxs-lookup"><span data-stu-id="0391a-122">RUN.for.Elected_Office</span></span>  
  
  <span data-ttu-id="0391a-123">用于 TIBCO Rendezvous 的 BizTalk 适配器使用 TIBCO Rendezvous SDK 将消息发布到 TIBCO Rendezvous 主题并注册 TIBCO Rendezvous 事件。</span><span class="sxs-lookup"><span data-stu-id="0391a-123">BizTalk Adapter for TIBCO Rendezvous uses the TIBCO Rendezvous SDK to publish messages to TIBCO Rendezvous subjects and to register for TIBCO Rendezvous events.</span></span> <span data-ttu-id="0391a-124">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的相关的类托管在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="0391a-124">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-related classes are hosted in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer.</span></span> <span data-ttu-id="0391a-125">单独的进程 （运行时代理） 启动，并且可作为 Rendezvous 程序，.NET Framework 远程处理用于这两个之间交换消息。</span><span class="sxs-lookup"><span data-stu-id="0391a-125">A separate process (run-time agent) is started and acts as the Rendezvous program, and .NET Framework remoting is used to exchange messages between the two.</span></span>  
  
- <span data-ttu-id="0391a-126">信息级警告级别和错误级别的消息发送到 Windows 事件日志。</span><span class="sxs-lookup"><span data-stu-id="0391a-126">Info-Level, Warning-Level, and Error-level messages are sent to the Windows event log.</span></span>  
  
- <span data-ttu-id="0391a-127">所有级别，包括调试级别消息被都发送到 Windows 跟踪日志。</span><span class="sxs-lookup"><span data-stu-id="0391a-127">All levels, including Debug-level messages, are sent to the Windows Tracing Log.</span></span>  
  
## <a name="transmitter"></a><span data-ttu-id="0391a-128">发送器</span><span class="sxs-lookup"><span data-stu-id="0391a-128">Transmitter</span></span>  
 <span data-ttu-id="0391a-129">用于 TIBCO Rendezvous 的 BizTalk 适配器将启动一个运行时代理，每个发送端口。</span><span class="sxs-lookup"><span data-stu-id="0391a-129">BizTalk Adapter for TIBCO Rendezvous launches one run-time agent per send port.</span></span> <span data-ttu-id="0391a-130">TIBCO Rendezvous.NET Framework API 只允许设置字符编码在全局范围内。</span><span class="sxs-lookup"><span data-stu-id="0391a-130">The TIBCO Rendezvous .NET Framework API only allows setting character encoding at a global scope.</span></span> <span data-ttu-id="0391a-131">因此，一个端口配置选项是一个代码页编号。</span><span class="sxs-lookup"><span data-stu-id="0391a-131">Therefore, one of the port configuration options is a code page number.</span></span> <span data-ttu-id="0391a-132">通过启动的每个代码页不同的进程，适配器可以提供更好地支持全球化。</span><span class="sxs-lookup"><span data-stu-id="0391a-132">By starting a different process for each code page, the adapter can provide better support for globalization.</span></span>  
  
## <a name="receiver"></a><span data-ttu-id="0391a-133">接收方</span><span class="sxs-lookup"><span data-stu-id="0391a-133">Receiver</span></span>  
 <span data-ttu-id="0391a-134">用于 TIBCO Rendezvous 启动一个运行时代理，每个 BizTalk 适配器接收位置。</span><span class="sxs-lookup"><span data-stu-id="0391a-134">BizTalk Adapter for TIBCO Rendezvous launches one run-time agent per receive location.</span></span>  
  
## <a name="transactions"></a><span data-ttu-id="0391a-135">事务</span><span class="sxs-lookup"><span data-stu-id="0391a-135">Transactions</span></span>  
 <span data-ttu-id="0391a-136">TIBCO Rendezvous 产品不是事务性的。</span><span class="sxs-lookup"><span data-stu-id="0391a-136">The TIBCO Rendezvous product is not transactional.</span></span> <span data-ttu-id="0391a-137">需要一个单独的产品，TIBCO Rendezvous TX。</span><span class="sxs-lookup"><span data-stu-id="0391a-137">A separate product, TIBCO Rendezvous TX, is required.</span></span> <span data-ttu-id="0391a-138">用于 TIBCO Rendezvous 的 BizTalk 适配器不在此版本中支持事务。</span><span class="sxs-lookup"><span data-stu-id="0391a-138">BizTalk Adapter for TIBCO Rendezvous does not support transactions in this release.</span></span>  
  
## <a name="security"></a><span data-ttu-id="0391a-139">安全性</span><span class="sxs-lookup"><span data-stu-id="0391a-139">Security</span></span>  
 <span data-ttu-id="0391a-140">TIBCO Rendezvous 仅支持 TIBCO Rendezvous 程序和守护程序之间的身份验证。</span><span class="sxs-lookup"><span data-stu-id="0391a-140">TIBCO Rendezvous only supports authentication between TIBCO Rendezvous programs and daemons.</span></span> <span data-ttu-id="0391a-141">它不会执行授权或加密。</span><span class="sxs-lookup"><span data-stu-id="0391a-141">It does not perform authorization or encryption.</span></span> <span data-ttu-id="0391a-142">需要一个单独的产品，TIBCO Rendezvous DataSecurity。</span><span class="sxs-lookup"><span data-stu-id="0391a-142">A separate product, TIBCO Rendezvous DataSecurity, is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0391a-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="0391a-143">See Also</span></span>  
 <span data-ttu-id="0391a-144">[TIBCO Rendezvous 概念](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="0391a-144">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="0391a-145">入门</span><span class="sxs-lookup"><span data-stu-id="0391a-145">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)