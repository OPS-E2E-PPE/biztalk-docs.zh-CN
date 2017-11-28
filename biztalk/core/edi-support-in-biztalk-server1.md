---
title: "在 BizTalk Server1 的 EDI 支持 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7cddab7a-99ef-4dbb-bb74-9e3d03df3996
caps.latest.revision: "37"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b5edfa2eccfeac9a4d4192b2189877081ddf25a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edi-support-in-biztalk-server"></a><span data-ttu-id="96600-102">BizTalk Server 中的 EDI 支持</span><span class="sxs-lookup"><span data-stu-id="96600-102">EDI Support in BizTalk Server</span></span>
<span data-ttu-id="96600-103">本主题从整体上简要介绍了 EDI 以及 [!INCLUDE[prague](../includes/prague-md.md)] 如何支持 EDI。</span><span class="sxs-lookup"><span data-stu-id="96600-103">This topic provides a brief general overview of EDI and how [!INCLUDE[prague](../includes/prague-md.md)] supports EDI.</span></span>  
  
## <a name="introduction-to-edi"></a><span data-ttu-id="96600-104">EDI 介绍</span><span class="sxs-lookup"><span data-stu-id="96600-104">Introduction to EDI</span></span>  
 <span data-ttu-id="96600-105">电子数据交换 (EDI) 是商业贸易伙伴以电子方式交换数据所最常用的一种手段。</span><span class="sxs-lookup"><span data-stu-id="96600-105">Electronic Data Interchange (EDI) is the single most commonly used means by which business trading partners exchange data electronically.</span></span> <span data-ttu-id="96600-106">EDI 很大程度上是面向消息的。</span><span class="sxs-lookup"><span data-stu-id="96600-106">EDI is largely messaging-oriented.</span></span> <span data-ttu-id="96600-107">文档被实现为可包含批事务集的平面文件。</span><span class="sxs-lookup"><span data-stu-id="96600-107">Documents are implemented as flat files that can include batched transaction sets.</span></span> <span data-ttu-id="96600-108">批交换可以包含多个组，每个组又可以包含多个事务集或消息。</span><span class="sxs-lookup"><span data-stu-id="96600-108">Batched interchanges can contain multiple groups, each of which can contain multiple transaction sets or messages.</span></span>  
  
 <span data-ttu-id="96600-109">EDI 由标准团体协商制订的特定数据交换方法组成。</span><span class="sxs-lookup"><span data-stu-id="96600-109">EDI consists of specific data interchange methods agreed upon by standards bodies.</span></span> <span data-ttu-id="96600-110">主要的 EDI 标准包括 X12（由 ANSI 进行标准化，主要在北美地区使用）和 EDIFACT（由联合国进行标准化，主要在美国以外地区使用）。</span><span class="sxs-lookup"><span data-stu-id="96600-110">The primary EDI standards are X12 (standardized by ANSI and used primarily in North America) and EDIFACT (standardized by the United Nations and used primarily outside the U.S.).</span></span> <span data-ttu-id="96600-111">其他标准都是从这两个标准派生出来的，例如：从 X12 派生的 HIPAA 和从 EDIFACT 派生的韩国的 KEDIFACT 标准。</span><span class="sxs-lookup"><span data-stu-id="96600-111">Other standards are derived from these, for example, HIPAA from X12 and KEDIFACT in Korea from EDIFACT.</span></span> <span data-ttu-id="96600-112">这些标准在消息结构和确认架构上都基本类似，但是也具有一些明显的差异。</span><span class="sxs-lookup"><span data-stu-id="96600-112">The standards are closely parallel in message structure and acknowledgment schemes, but have distinct differences.</span></span>  
  
 <span data-ttu-id="96600-113">EDI 标准规定了以下内容：</span><span class="sxs-lookup"><span data-stu-id="96600-113">The EDI standards prescribe the following:</span></span>  
  
-   <span data-ttu-id="96600-114">文档交换使用的格式、字符集和数据元素</span><span class="sxs-lookup"><span data-stu-id="96600-114">The formats, character sets, and data elements used in the exchange of documents</span></span>  
  
-   <span data-ttu-id="96600-115">EDI 事务中使用的信封</span><span class="sxs-lookup"><span data-stu-id="96600-115">The envelopes used in EDI transaction</span></span>  
  
-   <span data-ttu-id="96600-116">验证是否送达所需的确认</span><span class="sxs-lookup"><span data-stu-id="96600-116">The acknowledgments required to verify delivery</span></span>  
  
-   <span data-ttu-id="96600-117">如何提供有保障且只需一次的传递，以及对损坏数据或不正确数据的自动检测和报告。</span><span class="sxs-lookup"><span data-stu-id="96600-117">How to provide guaranteed, exactly-once delivery, and automatic detection and reporting of corrupted or incorrect data.</span></span>  
  
 <span data-ttu-id="96600-118">尽管 EDI 标准确定了文档结构的规则，但是贸易伙伴必须对要传输的特定信息和如何使用该特定信息达成一致。</span><span class="sxs-lookup"><span data-stu-id="96600-118">While the EDI standards establish the rules for the structure of the document, trading partners must agree on the specific information to be transmitted and how it should be used.</span></span> <span data-ttu-id="96600-119">连接两个贸易伙伴的 EDI 系统的设计是由标准所要求的内容和贸易伙伴所达成一致的内容共同决定的。</span><span class="sxs-lookup"><span data-stu-id="96600-119">The design of an EDI system connecting two trading partners is determined by what the standards require, and what the trading partners agree upon.</span></span> <span data-ttu-id="96600-120">有关 EDI 消息传送的详细信息，请参阅[EDI 消息传递](../core/edi-messaging.md)。</span><span class="sxs-lookup"><span data-stu-id="96600-120">For more information about EDI messaging, see [EDI Messaging](../core/edi-messaging.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96600-121">EDI 消息的传输方式多种多样。</span><span class="sxs-lookup"><span data-stu-id="96600-121">EDI messages are distinguished from their transport.</span></span> <span data-ttu-id="96600-122">EDI 标准没有对消息传输加以规定，因此可以通过各种不同的手段发送 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="96600-122">The EDI standards do not prescribe message transport, and EDI messages can be sent by a variety of different means.</span></span>  
  
## <a name="how-edi-is-implemented-in-biztalk-server"></a><span data-ttu-id="96600-123">BizTalk Server 中 EDI 的实现方式</span><span class="sxs-lookup"><span data-stu-id="96600-123">How EDI Is Implemented in BizTalk Server</span></span>  
 [!INCLUDE[prague](../includes/prague-md.md)]<span data-ttu-id="96600-124"> 包括了可提供 EDI 支持的本机功能。</span><span class="sxs-lookup"><span data-stu-id="96600-124"> includes native functionality that provides support for EDI.</span></span> <span data-ttu-id="96600-125">EDI 内置于产品中。它不是外接程序，例如适配器或快捷键。</span><span class="sxs-lookup"><span data-stu-id="96600-125">EDI is built into the product; it is not an add-in, such as an adapter or an accelerator .</span></span>  
  
 <span data-ttu-id="96600-126">**交换处理**</span><span class="sxs-lookup"><span data-stu-id="96600-126">**Interchange Processing**</span></span>  
  
 <span data-ttu-id="96600-127">此 EDI 功能在强制实施 EDI 标准所规定的规则的管道中执行以下接收端和发送端处理。</span><span class="sxs-lookup"><span data-stu-id="96600-127">The EDI feature performs the following receive-side and send-side processing in pipelines that enforces the rules dictated by the EDI standards.</span></span>  
  
-   <span data-ttu-id="96600-128">处理传入的 EDI 消息，包括验证交换和生成确认。</span><span class="sxs-lookup"><span data-stu-id="96600-128">Processes incoming EDI messages, including validating interchanges and generating acknowledgments.</span></span>  
  
-   <span data-ttu-id="96600-129">生成并将传出 EDI 消息，包括验证的交换和处理收到的具体取决于配置的确认。</span><span class="sxs-lookup"><span data-stu-id="96600-129">Generates and sends outgoing EDI messages, including validating interchanges and processing received ACKs depending upon the configuration.</span></span>  
  
 <span data-ttu-id="96600-130">**批处理**</span><span class="sxs-lookup"><span data-stu-id="96600-130">**Batch Processing**</span></span>  
  
 <span data-ttu-id="96600-131">批处理由接收管道和业务流程进行处理：</span><span class="sxs-lookup"><span data-stu-id="96600-131">Batch processing is handled by the receive pipeline and orchestration:</span></span>  
  
-   <span data-ttu-id="96600-132">如果收到的批交换将被拆分，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会拆分为其构成事务集，同时为每个事务集生成一个 XML 文件并且升级执行发送端批生成操作所需的属性。</span><span class="sxs-lookup"><span data-stu-id="96600-132">If a received batched interchange is to be split, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] splits it into its constituent transaction sets, generating an XML file for each transaction set and promoting properties required for send-side batch generation.</span></span>  
  
-   <span data-ttu-id="96600-133">如果收到的批交换将被保留，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会对批进行处理，使批保留收到它时所包含的事务集和组。</span><span class="sxs-lookup"><span data-stu-id="96600-133">If a received batched interchange is to be preserved, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes the batch such that it retains the transaction sets and groups that it contained when the batch was received.</span></span>  
  
-   <span data-ttu-id="96600-134">如果收到的批交换将进行配置，则批会将 EDI 事务集和组接收到传出交换中。</span><span class="sxs-lookup"><span data-stu-id="96600-134">If a received batched interchange is to be configured, batches receive EDI transaction sets and groups into an outgoing interchange.</span></span>  
  
-   <span data-ttu-id="96600-135">如果有多个参与方订阅了某个批交换，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会向每个参与方发送该批的一个副本。</span><span class="sxs-lookup"><span data-stu-id="96600-135">If multiple parties subscribe to a batched interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends a copy of the batch to each party.</span></span>  
  
 <span data-ttu-id="96600-136">**贸易合作伙伴协议**</span><span class="sxs-lookup"><span data-stu-id="96600-136">**Trading Partner Agreements**</span></span>  
  
 <span data-ttu-id="96600-137">贸易合作伙伴相互定义贸易合作伙伴协议这是一组在 BizTalk Server 管理控制台中定义的属性。</span><span class="sxs-lookup"><span data-stu-id="96600-137">Trading partners mutually define the Trading Partner Agreement which is a set of properties defined in the BizTalk Server Administration Console.</span></span> <span data-ttu-id="96600-138">这些参与方属性、发送和接收端口/位置属性决定了接收端和发送端的 EDI 处理过程。</span><span class="sxs-lookup"><span data-stu-id="96600-138">These party properties, send and receive port/location properties, determine receive-side and send-side EDI processing.</span></span> <span data-ttu-id="96600-139">有关贸易合作伙伴协议的详细信息，请参阅[贸易合作伙伴协议](../core/trading-partner-agreement.md)。</span><span class="sxs-lookup"><span data-stu-id="96600-139">For more information about trading partner agreements, see [Trading Partner Agreement](../core/trading-partner-agreement.md).</span></span>  
  
 <span data-ttu-id="96600-140">**交换状态**</span><span class="sxs-lookup"><span data-stu-id="96600-140">**Interchange Status**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="96600-141"> 可提供特定于 EDI 的状态报告。</span><span class="sxs-lookup"><span data-stu-id="96600-141"> provides EDI-specific status reporting.</span></span> <span data-ttu-id="96600-142">这些状态报告提供了 EDI 文档交换事务的全面状态，包括与交换有关的确认状态。</span><span class="sxs-lookup"><span data-stu-id="96600-142">These status reports provide a comprehensive status of an EDI document exchange transaction, including acknowledgments correlated to the interchange.</span></span>  
  
## <a name="edi-components-in-biztalk-server"></a><span data-ttu-id="96600-143">BizTalk Server 中的 EDI 组件</span><span class="sxs-lookup"><span data-stu-id="96600-143">EDI Components in BizTalk Server</span></span>  
 <span data-ttu-id="96600-144">用于 EDI 处理的 Microsoft [!INCLUDE[prague](../includes/prague-md.md)] 组件包括如下：</span><span class="sxs-lookup"><span data-stu-id="96600-144">Microsoft [!INCLUDE[prague](../includes/prague-md.md)] components used for EDI processing include the following:</span></span>  
  
-   <span data-ttu-id="96600-145">BizTalk EDI 应用程序，包含处理 EDI 文档所需的项目（包括管道、业务流程和架构）。</span><span class="sxs-lookup"><span data-stu-id="96600-145">The BizTalk EDI Application contains artifacts (including pipelines, orchestrations, and schemas) that are needed to process EDI documents.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="96600-146">当你在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中配置的 EDI 功能时，配置程序会创建此应用程序。</span><span class="sxs-lookup"><span data-stu-id="96600-146">When you configure the EDI feature in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the configuration program creates this application.</span></span> <span data-ttu-id="96600-147">只要你创建了将处理 EDI 交换的应用程序，就必须从该应用程序中添加对 BizTalk EDI 应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="96600-147">Whenever you create an application that will process EDI interchanges, you must add a reference to the BizTalk EDI Application from your application.</span></span> <span data-ttu-id="96600-148">有关详细信息，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。</span><span class="sxs-lookup"><span data-stu-id="96600-148">For more information, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
-   <span data-ttu-id="96600-149">BizTalk EDI 接收管道（EdiReceive 管道），用于分析 EDI 编码的文档，拆分 EDI 批，将 EDI 编码的文档转换为 XML 编码，执行 EDI 和 XSD 验证，以及执行 HIPAA X12 子文档拆分。</span><span class="sxs-lookup"><span data-stu-id="96600-149">The BizTalk EDI Receive Pipeline (EdiReceive pipeline) parses EDI-encoded documents, splits EDI batches, converts the EDI-encoded documents into XML encoding, performs EDI and XSD validation, and performs HIPAA X12 sub-document splitting.</span></span> <span data-ttu-id="96600-150">有关详细信息，请参阅[EDI 接收组件](../core/edi-receive-components.md)。</span><span class="sxs-lookup"><span data-stu-id="96600-150">For more information, see [EDI Receive Components](../core/edi-receive-components.md).</span></span>  
  
-   <span data-ttu-id="96600-151">BizTalk EDI 发送管道（EdiSend 管道），用于将 XML 文档转换为 X12 或 EDIFACT 编码，序列化 EDI 编码的文档以及执行 EDI 和 XSD 验证。</span><span class="sxs-lookup"><span data-stu-id="96600-151">The BizTalk EDI Send Pipeline (EdiSend pipeline) converts XML documents into X12 or EDIFACT encoding, serializes EDI-encoded documents, and performs EDI and XSD validation.</span></span> <span data-ttu-id="96600-152">有关详细信息，请参阅[EDI 发送组件](../core/edi-send-components.md)。</span><span class="sxs-lookup"><span data-stu-id="96600-152">For more information, see [EDI Send Components](../core/edi-send-components.md).</span></span>  
  
-   <span data-ttu-id="96600-153">使用贸易合作伙伴管理 (TPM) 用户接口，你可以为参与 EDI 文档交换和 AS2 文档传输的贸易合作伙伴设置处理属性。</span><span class="sxs-lookup"><span data-stu-id="96600-153">The Trading Partner Management (TPM) user interface enables you to set processing properties for trading partners engaging in EDI document exchange and AS2 document transport.</span></span> <span data-ttu-id="96600-154">有关详细信息，请参阅[在 EDI 处理中的协议角色](../core/the-role-of-agreements-in-edi-processing.md)和**EDI 和 AS2 UI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="96600-154">For more information, see [The Role of Agreements in EDI Processing](../core/the-role-of-agreements-in-edi-processing.md) and **EDI and AS2 UI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
-   <span data-ttu-id="96600-155">批处理业务流程，用于对 EDI 交换进行批处理，以及设置用于发送批交换的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="96600-155">The batching orchestration batches EDI interchanges and sets context properties for sending of the batched interchange.</span></span> <span data-ttu-id="96600-156">路由业务流程处理其中消息匹配多个批处理的实例，创建需要的多个消息副本。</span><span class="sxs-lookup"><span data-stu-id="96600-156">The routing orchestration handles the instances in which messages match multiple batches, creating as many copies of the message as required.</span></span> <span data-ttu-id="96600-157">有关详细信息，请参阅[处理传入批](../core/processing-incoming-batches.md)和[批处理传出的 EDI 消息](../core/batching-outgoing-edi-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="96600-157">For more information, see [Processing Incoming Batches](../core/processing-incoming-batches.md) and [Batching Outgoing EDI Messages](../core/batching-outgoing-edi-messages.md).</span></span>  
  
-   <span data-ttu-id="96600-158">状态报告用户界面，提供了 EDI 交换和相关确认的全面状态信息。</span><span class="sxs-lookup"><span data-stu-id="96600-158">The status reporting user interface provides comprehensive status of EDI interchanges and correlated acknowledgments.</span></span> <span data-ttu-id="96600-159">有关详细信息，请参阅[EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)。</span><span class="sxs-lookup"><span data-stu-id="96600-159">For more information, see [EDI and AS2 Status Reporting](../core/edi-and-as2-status-reporting.md).</span></span>  
  
-   <span data-ttu-id="96600-160">Visual Studio 中的设计时工具，通过这些工具，可以生成实例、验证实例，验证架构，测试映射以及验证映射。</span><span class="sxs-lookup"><span data-stu-id="96600-160">Design time tools in Visual Studio enable you to generate an instance, validate an instance, validate a schema, test a map, and validating a map.</span></span> <span data-ttu-id="96600-161">有关详细信息，请参阅[使用设计时 XML 工具](../core/using-design-time-xml-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="96600-161">For more information, see [Using Design-Time XML Tools](../core/using-design-time-xml-tools.md).</span></span>  
  
-   <span data-ttu-id="96600-162">架构存储库，包括 X12、EDIFACT、HIPAA X12N 4010A XSD、EANCOM 以及控制架构。</span><span class="sxs-lookup"><span data-stu-id="96600-162">A schema repository includes X12, EDIFACT, HIPAA X12N 4010A XSD, EANCOM, and control schemas.</span></span> <span data-ttu-id="96600-163">有关详细信息，请参阅[EDI 文档架构支持](../core/edi-document-schema-support.md)。</span><span class="sxs-lookup"><span data-stu-id="96600-163">For more information, see [EDI Document Schema Support](../core/edi-document-schema-support.md).</span></span>  
  
-   <span data-ttu-id="96600-164">通过迁移工具（参与方迁移工具），可以将 EDI 参与方数据从 BizTalk Server 2006 R2 或 BizTalk Server 2009 迁移到 [!INCLUDE[prague](../includes/prague-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="96600-164">A migration tool (Party Migration Tool) enables you to migrate EDI party data from BizTalk Server 2006 R2 or BizTalk Server 2009 to [!INCLUDE[prague](../includes/prague-md.md)].</span></span> <span data-ttu-id="96600-165">有关详细信息，请参阅[迁移 BizTalk Server 以前版本中的 EDI 项目](http://msdn.microsoft.com/library/b956a97e-03d0-47ea-a2ce-c07a339c0f2c)。</span><span class="sxs-lookup"><span data-stu-id="96600-165">For more information, see [Migrating EDI Artifacts from a Previous Version of BizTalk Server](http://msdn.microsoft.com/library/b956a97e-03d0-47ea-a2ce-c07a339c0f2c).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96600-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96600-166">See Also</span></span>  
 <span data-ttu-id="96600-167">[BizTalk Server 中的 EDI 处理](../core/edi-processing-in-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="96600-167">[EDI Processing in BizTalk Server](../core/edi-processing-in-biztalk-server.md) </span></span>  
 <span data-ttu-id="96600-168">[BizTalk Server 中的 HIPAA 支持](../core/hipaa-support-in-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="96600-168">[HIPAA Support in BizTalk Server](../core/hipaa-support-in-biztalk-server.md) </span></span>  
 <span data-ttu-id="96600-169">[EDI 支持问题](../core/edi-support-issues.md) </span><span class="sxs-lookup"><span data-stu-id="96600-169">[EDI Support Issues](../core/edi-support-issues.md) </span></span>  
 <span data-ttu-id="96600-170">[EDI 解决方案体系结构](../core/edi-solution-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="96600-170">[EDI Solution Architecture](../core/edi-solution-architecture.md) </span></span>  
 <span data-ttu-id="96600-171">[EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md) </span><span class="sxs-lookup"><span data-stu-id="96600-171">[EDI and AS2 Status Reporting](../core/edi-and-as2-status-reporting.md) </span></span>  
 [<span data-ttu-id="96600-172">开发和配置 BizTalk Server EDI 解决方案</span><span class="sxs-lookup"><span data-stu-id="96600-172">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)