---
title: "TIBCO 会合适配器中的消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 12699550-22e7-4a11-a024-2302570970af
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b9c3aa4aeb613ea65f7e0d7385871c639afb6d8
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="messages-in-biztalk-adapter-for-tibco-rendezvous"></a><span data-ttu-id="2a998-102">TIBCO Rendezvous 的 BizTalk 适配器中的消息</span><span class="sxs-lookup"><span data-stu-id="2a998-102">Messages in BizTalk Adapter for TIBCO Rendezvous</span></span>
<span data-ttu-id="2a998-103">用于 TIBCO Rendezvous 的 BizTalk 适配器提供了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 TIBCO Rendezvous 之间的双向连接。</span><span class="sxs-lookup"><span data-stu-id="2a998-103">BizTalk Adapter for TIBCO Rendezvous provides bi-directional connectivity between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and TIBCO Rendezvous.</span></span> <span data-ttu-id="2a998-104">此适配器同时使用 TIBCO Rendezvous API 和 BizTalk 适配器框架 API 来提供紧密集成。</span><span class="sxs-lookup"><span data-stu-id="2a998-104">This adapter uses both the TIBCO Rendezvous API and the BizTalk Adapter Framework API to provide tight integration.</span></span>  
  
## <a name="about-tibco-rendezvous"></a><span data-ttu-id="2a998-105">有关 TIBCO 会合</span><span class="sxs-lookup"><span data-stu-id="2a998-105">About TIBCO Rendezvous</span></span>  
 <span data-ttu-id="2a998-106">TIBCO 集合是为企业应用程序集成 (EAI) 提供消息总线程序。</span><span class="sxs-lookup"><span data-stu-id="2a998-106">TIBCO Rendezvous is a programs that provides a message bus for enterprise application integration (EAI).</span></span> <span data-ttu-id="2a998-107">TIBCO 在 C、C++、Java、Visual Basic 中提供了消息传送 API，并为 Microsoft .NET Framework 提供了用于接收 Microsoft Office Excel 工作表及其他所选应用程序上的数据馈送的消息传送 API。</span><span class="sxs-lookup"><span data-stu-id="2a998-107">TIBCO provides messaging APIs in C, C++, Java, Visual Basic and for the Microsoft .NET Framework to receive data feeds on Microsoft Office Excel worksheets and other applications of choice.</span></span> <span data-ttu-id="2a998-108">有关详细信息，请参阅[TIBCO 会合概念](../core/tibco-rendezvous-concepts.md)。</span><span class="sxs-lookup"><span data-stu-id="2a998-108">For more information, see [TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md).</span></span>  
  
## <a name="message-passing"></a><span data-ttu-id="2a998-109">消息传递</span><span class="sxs-lookup"><span data-stu-id="2a998-109">Message Passing</span></span>  
 <span data-ttu-id="2a998-110">消息传递的基本概念相当简单：</span><span class="sxs-lookup"><span data-stu-id="2a998-110">The basic concept of message passing is fairly simple:</span></span>  
  
-   <span data-ttu-id="2a998-111">消息具有单个主题，其中包含用句点分隔的元素。</span><span class="sxs-lookup"><span data-stu-id="2a998-111">A message has a single subject composed of elements separated by periods.</span></span> <span data-ttu-id="2a998-112">尽管消息最终可能会被广播到其他后台程序，但它也会被发送到单个的 Rendezvous 后台程序。</span><span class="sxs-lookup"><span data-stu-id="2a998-112">A message is sent to a single Rendezvous daemon, although it might eventually be broadcast onto other daemons.</span></span>  
  
-   <span data-ttu-id="2a998-113">侦听器会向后台程序宣布其感兴趣的主题（带有基本通配符）。</span><span class="sxs-lookup"><span data-stu-id="2a998-113">A listener announces its subjects of interest to a daemon (with a basic wildcard facility).</span></span> <span data-ttu-id="2a998-114">如果两个后台程序相互连接，或者它们实际上是同一个后台程序，则会将拥有匹配主题的消息传递到该侦听程序。</span><span class="sxs-lookup"><span data-stu-id="2a998-114">Messages that have matching subjects are delivered to it if the two daemons are connected to each other, or are indeed the same daemon.</span></span>  
  
 <span data-ttu-id="2a998-115">可以使用可能的“容错/可靠”或“已认证”选项，根据需要将重要的“企业”功能分层部署到此后台程序，所有操作均通过潜在的基本消息实现。</span><span class="sxs-lookup"><span data-stu-id="2a998-115">Significant "Enterprise" functionality is layered onto this if desired--with Fault Tolerance/Reliable or Certified options possible--all implemented through the underlying basic messages.</span></span>  
  
 <span data-ttu-id="2a998-116">消息本身可看作是键入的名称-值字段或数字-值字段（消息中的两个标识机制可以混合，并且可以与某些限制混合使用）。</span><span class="sxs-lookup"><span data-stu-id="2a998-116">The messages themselves can be viewed as typed name-value fields or number-value fields (the two identification mechanisms in a message can mix and match with certain restrictions).</span></span> <span data-ttu-id="2a998-117">消息本身可包含子消息，子消息中还可以包含子消息。</span><span class="sxs-lookup"><span data-stu-id="2a998-117">A message itself can contain sub-messages, which can contain sub-messages.</span></span>  
  
 <span data-ttu-id="2a998-118">主题名称由圆点字符（句点）分隔的一个或多个元素组成。</span><span class="sxs-lookup"><span data-stu-id="2a998-118">Subject names consist of one or more elements separated by dot characters (periods).</span></span> <span data-ttu-id="2a998-119">这些元素实现一个主题名称层次结构，反映信息在应用程序系统中的结构。</span><span class="sxs-lookup"><span data-stu-id="2a998-119">The elements implement a subject name hierarchy that reflects the structure of information in an application system.</span></span> <span data-ttu-id="2a998-120">以下字符串是有效主题名称的示例：</span><span class="sxs-lookup"><span data-stu-id="2a998-120">The following strings are examples of valid subject names:</span></span>  
  
-   <span data-ttu-id="2a998-121">运行。主页</span><span class="sxs-lookup"><span data-stu-id="2a998-121">RUN.HOME</span></span>  
  
-   <span data-ttu-id="2a998-122">RUN.for.Elected_Office</span><span class="sxs-lookup"><span data-stu-id="2a998-122">RUN.for.Elected_Office</span></span>  
  
 <span data-ttu-id="2a998-123">用于 TIBCO Rendezvous 的 BizTalk 适配器使用 TIBCO Rendezvous SDK 来将消息发布到 TIBCO Rendezvous 主题，并注册 TIBCO Rendezvous 事件。</span><span class="sxs-lookup"><span data-stu-id="2a998-123">BizTalk Adapter for TIBCO Rendezvous uses the TIBCO Rendezvous SDK to publish messages to TIBCO Rendezvous subjects and to register for TIBCO Rendezvous events.</span></span> <span data-ttu-id="2a998-124">与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 相关的类在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机中托管。</span><span class="sxs-lookup"><span data-stu-id="2a998-124">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-related classes are hosted in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer.</span></span> <span data-ttu-id="2a998-125">将启动单独的进程（运行时代理）并用作 Rendezvous 程序，.NET Framework 远程调用用于在这两者之间交换消息。</span><span class="sxs-lookup"><span data-stu-id="2a998-125">A separate process (run-time agent) is started and acts as the Rendezvous program, and .NET Framework remoting is used to exchange messages between the two.</span></span>  
  
-   <span data-ttu-id="2a998-126">信息级别、警告级别和错误级别的消息将被发送到 Windows 事件日志。</span><span class="sxs-lookup"><span data-stu-id="2a998-126">Info-Level, Warning-Level, and Error-level messages are sent to the Windows event log.</span></span>  
  
-   <span data-ttu-id="2a998-127">包括调试级别消息在内的所有级别的消息都将被发送到 Windows 跟踪日志。</span><span class="sxs-lookup"><span data-stu-id="2a998-127">All levels, including Debug-level messages, are sent to the Windows Tracing Log.</span></span>  
  
## <a name="transmitter"></a><span data-ttu-id="2a998-128">发送器</span><span class="sxs-lookup"><span data-stu-id="2a998-128">Transmitter</span></span>  
 <span data-ttu-id="2a998-129">用于 TIBCO Rendezvous 的 BizTalk 适配器会对每个发送端口启动一个运行时代理。</span><span class="sxs-lookup"><span data-stu-id="2a998-129">BizTalk Adapter for TIBCO Rendezvous launches one run-time agent per send port.</span></span> <span data-ttu-id="2a998-130">TIBCO Rendezvous .net Framework API 只允许在全局范围内设置字符编码。</span><span class="sxs-lookup"><span data-stu-id="2a998-130">The TIBCO Rendezvous .NET Framework API only allows setting character encoding at a global scope.</span></span> <span data-ttu-id="2a998-131">因此，其中一个端口配置选项是代码页数。</span><span class="sxs-lookup"><span data-stu-id="2a998-131">Therefore, one of the port configuration options is a code page number.</span></span> <span data-ttu-id="2a998-132">通过为每个代码页启动不同的进程，适配器可以为全球化提供更好的支持。</span><span class="sxs-lookup"><span data-stu-id="2a998-132">By starting a different process for each code page, the adapter can provide better support for globalization.</span></span>  
  
## <a name="receiver"></a><span data-ttu-id="2a998-133">接收方</span><span class="sxs-lookup"><span data-stu-id="2a998-133">Receiver</span></span>  
 <span data-ttu-id="2a998-134">用于 TIBCO Rendezvous 的 BizTalk 适配器会对每个接收位置启动一个运行时代理。</span><span class="sxs-lookup"><span data-stu-id="2a998-134">BizTalk Adapter for TIBCO Rendezvous launches one run-time agent per receive location.</span></span>  
  
## <a name="transactions"></a><span data-ttu-id="2a998-135">中的</span><span class="sxs-lookup"><span data-stu-id="2a998-135">Transactions</span></span>  
 <span data-ttu-id="2a998-136">TIBCO Rendezvous 产品不是事务性的。</span><span class="sxs-lookup"><span data-stu-id="2a998-136">The TIBCO Rendezvous product is not transactional.</span></span> <span data-ttu-id="2a998-137">需要一个单独的产品，即 TIBCO Rendezvous TX。</span><span class="sxs-lookup"><span data-stu-id="2a998-137">A separate product, TIBCO Rendezvous TX, is required.</span></span> <span data-ttu-id="2a998-138">用于 TIBCO Rendezvous 的 BizTalk 适配器不支持此版本中的事务。</span><span class="sxs-lookup"><span data-stu-id="2a998-138">BizTalk Adapter for TIBCO Rendezvous does not support transactions in this release.</span></span>  
  
## <a name="security"></a><span data-ttu-id="2a998-139">安全性</span><span class="sxs-lookup"><span data-stu-id="2a998-139">Security</span></span>  
 <span data-ttu-id="2a998-140">TIBCO Rendezvous 仅支持 TIBCO Rendezvous 程序与后台程序之间的身份验证。</span><span class="sxs-lookup"><span data-stu-id="2a998-140">TIBCO Rendezvous only supports authentication between TIBCO Rendezvous programs and daemons.</span></span> <span data-ttu-id="2a998-141">它不会执行授权或加密。</span><span class="sxs-lookup"><span data-stu-id="2a998-141">It does not perform authorization or encryption.</span></span> <span data-ttu-id="2a998-142">需要一个单独的产品，即 TIBCO Rendezvous DataSecurity。</span><span class="sxs-lookup"><span data-stu-id="2a998-142">A separate product, TIBCO Rendezvous DataSecurity, is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a998-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a998-143">See Also</span></span>  
 <span data-ttu-id="2a998-144">[TIBCO 会合概念](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="2a998-144">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="2a998-145">入门</span><span class="sxs-lookup"><span data-stu-id="2a998-145">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)