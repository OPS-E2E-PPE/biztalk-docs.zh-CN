---
title: RosettaNet 快捷键 BizTalk Server 中的术语表 |Microsoft 文档
description: 常见术语和定义知道并了解用于 BizTalk Accelerator RosettaNet
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d98a5ed4-adc5-4ca9-b9d9-38ab02a0bda6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd89d75b0d36359fcf59f7edae0bb950a7196ca7
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
ms.locfileid: "22211725"
---
# <a name="glossary"></a><span data-ttu-id="55ebe-103">词汇表</span><span class="sxs-lookup"><span data-stu-id="55ebe-103">Glossary</span></span>
[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]<span data-ttu-id="55ebe-104"> 使用以下术语表术语和定义。</span><span class="sxs-lookup"><span data-stu-id="55ebe-104"> uses the following glossary terms and definitions.</span></span>  

  
## <a name="a"></a><span data-ttu-id="55ebe-105">指向</span><span class="sxs-lookup"><span data-stu-id="55ebe-105">A</span></span>  
 <span data-ttu-id="55ebe-106">**应用程序适配器**</span><span class="sxs-lookup"><span data-stu-id="55ebe-106">**application adapter**</span></span>  
 <span data-ttu-id="55ebe-107">实现的应用程序的应用程序适配器接口。</span><span class="sxs-lookup"><span data-stu-id="55ebe-107">An application that implements the application adapter interface.</span></span> <span data-ttu-id="55ebe-108">接受传入的操作消息 （请求或响应） 上的通知机制调用的应用程序适配器。</span><span class="sxs-lookup"><span data-stu-id="55ebe-108">The notification mechanism on the acceptance of an incoming action message (request or response) invokes the application adapter.</span></span> <span data-ttu-id="55ebe-109">它实现两种方法：`BeginNotify`和`EndNotify`。</span><span class="sxs-lookup"><span data-stu-id="55ebe-109">It implements two methods: `BeginNotify` and `EndNotify`.</span></span> <span data-ttu-id="55ebe-110">公共响应方时，将调用`BeginNotify`方法，而现成可用的专用响应方时，将调用`EndNotify`方法。</span><span class="sxs-lookup"><span data-stu-id="55ebe-110">The public responder invokes the `BeginNotify` method, whereas the out-of-the-box private responder invokes the `EndNotify` method.</span></span> <span data-ttu-id="55ebe-111">调用`Notify`方法意味着消息已成功保存到 MessagesToLOB 表。</span><span class="sxs-lookup"><span data-stu-id="55ebe-111">The call to the `Notify` method means that the message was successfully saved into the MessagesToLOB table.</span></span>  
  
 <span data-ttu-id="55ebe-112">**操作 URL**</span><span class="sxs-lookup"><span data-stu-id="55ebe-112">**action URL**</span></span>  
 <span data-ttu-id="55ebe-113">到本组织传输操作消息在异步过程中，例如，合作伙伴 URL http://FabrikamServer/BTARNApp/RNIFReceive.aspx。</span><span class="sxs-lookup"><span data-stu-id="55ebe-113">The partner URL to which the home organization transmits an action message during an asynchronous process, for example, http://FabrikamServer/BTARNApp/RNIFReceive.aspx.</span></span>  
  
## <a name="b"></a><span data-ttu-id="55ebe-114">B</span><span class="sxs-lookup"><span data-stu-id="55ebe-114">B</span></span>  
 <span data-ttu-id="55ebe-115">**BizTalk Accelerator for RosettaNet**</span><span class="sxs-lookup"><span data-stu-id="55ebe-115">**BizTalk Accelerator for RosettaNet**</span></span>  
 <span data-ttu-id="55ebe-116">给 BizTalk Server，可帮助组织构建 RosettaNet 实现框架 (RNIF) 外接程序产品-合规的解决方案。</span><span class="sxs-lookup"><span data-stu-id="55ebe-116">An add-on product to BizTalk Server that helps organizations to build RosettaNet Implementation Framework (RNIF)-compliant solutions.</span></span>  
  
 <span data-ttu-id="55ebe-117">**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] 管理**</span><span class="sxs-lookup"><span data-stu-id="55ebe-117">**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] Administration**</span></span>  
 <span data-ttu-id="55ebe-118">一个 Microsoft [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] 应用程序，使用它可以描述流程模板和管理合作伙伴协议。</span><span class="sxs-lookup"><span data-stu-id="55ebe-118">A Microsoft [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] application that lets you describe process templates and manage partner agreements.</span></span>  
  
 <span data-ttu-id="55ebe-119">**BizTalk 编辑器**</span><span class="sxs-lookup"><span data-stu-id="55ebe-119">**BizTalk Editor**</span></span>  
 <span data-ttu-id="55ebe-120">一种工具，这可以用于创建、 编辑和管理规范。</span><span class="sxs-lookup"><span data-stu-id="55ebe-120">A tool with which you can create, edit, and manage specifications.</span></span> <span data-ttu-id="55ebe-121">使用 BizTalk 编辑器可以创建基于规范模板、 现有架构、 文档实例，某些类型的规范或空白的规范。</span><span class="sxs-lookup"><span data-stu-id="55ebe-121">With BizTalk Editor you can create a specification based on a specification template, an existing schema, certain types of document instances, or a blank specification.</span></span>  
  
 <span data-ttu-id="55ebe-122">**BizTalk 业务流程设计器**</span><span class="sxs-lookup"><span data-stu-id="55ebe-122">**BizTalk Orchestration Designer**</span></span>  
 <span data-ttu-id="55ebe-123">可用于创建绘图可描述长时间运行的设计工具松散耦合，可执行业务流程。</span><span class="sxs-lookup"><span data-stu-id="55ebe-123">A design tool you can use to create drawings that describe long running, loosely coupled, executable business processes.</span></span> <span data-ttu-id="55ebe-124">绘制 XLANG 计划是用于运行自动化的业务流程 XLANG 计划在编译的。</span><span class="sxs-lookup"><span data-stu-id="55ebe-124">The XLANG schedule drawing is compiled in an XLANG schedule that you use to run the automated business process.</span></span>  
  
 <span data-ttu-id="55ebe-125">**BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="55ebe-125">**BizTalk Server**</span></span>  
 <span data-ttu-id="55ebe-126">用于业务流程自动化和应用程序集成在和企业之间的 Microsoft 产品。</span><span class="sxs-lookup"><span data-stu-id="55ebe-126">A Microsoft product for business-process automation and application integration both in and between businesses.</span></span> <span data-ttu-id="55ebe-127">BizTalk Server 提供了一个功能强大的基于 Web 的开发和执行环境集成松散耦合，长时间运行业务流程，在和企业之间。</span><span class="sxs-lookup"><span data-stu-id="55ebe-127">BizTalk Server provides a powerful Web-based development and execution environment that integrates loosely coupled, long-running business processes, both in and between businesses.</span></span>  
  
 <span data-ttu-id="55ebe-128">BizTalk Server 功能包括新的和现有 XLANG 计划; 组成现有应用程序; 之间的集成文档规范和规范转换; 的定义监视和运行时活动日志记录。</span><span class="sxs-lookup"><span data-stu-id="55ebe-128">BizTalk Server features include the composition of new and existing XLANG schedules; integration among existing applications; the definition of document specifications and specification transformations; and the monitoring and logging of run-time activity.</span></span>  
  
 <span data-ttu-id="55ebe-129">服务器发送和接收文档分布在 Internet 提供标准网关，并提供一系列可帮助确保数据完整性、 传递、 安全性和对 BizTalk 框架和其他密钥的文档格式的支持的服务。</span><span class="sxs-lookup"><span data-stu-id="55ebe-129">The server provides a standard gateway for sending and receiving documents across the Internet, and provides a range of services that help to ensure data integrity, delivery, security, and support for the BizTalk Framework and other key document formats.</span></span>  
  
 <span data-ttu-id="55ebe-130">**BtarnClean**</span><span class="sxs-lookup"><span data-stu-id="55ebe-130">**BtarnClean**</span></span>  
 <span data-ttu-id="55ebe-131">关闭计算机的干净 BTARN 项目到实用工具。</span><span class="sxs-lookup"><span data-stu-id="55ebe-131">A utility to clean BTARN artifacts off a computer.</span></span>  
  
 <span data-ttu-id="55ebe-132">**业务操作**</span><span class="sxs-lookup"><span data-stu-id="55ebe-132">**business action**</span></span>  
 <span data-ttu-id="55ebe-133">RosettaNet 消息包含业务如采购订单请求或报价请求的内容。</span><span class="sxs-lookup"><span data-stu-id="55ebe-133">A RosettaNet message that contains business content such as a purchase order request or a request for a quote.</span></span> <span data-ttu-id="55ebe-134">业务的信号，以及这些操作构成了所需的元素以完成指定的特定合作伙伴接口过程 (PIP) 的业务活动。</span><span class="sxs-lookup"><span data-stu-id="55ebe-134">Together with business signals, these actions make up the necessary elements to complete the business activity specified by a particular Partner Interface Process (PIP).</span></span>  
  
 <span data-ttu-id="55ebe-135">**业务活动监视 (BAM)**</span><span class="sxs-lookup"><span data-stu-id="55ebe-135">**Business Activity Monitoring (BAM)**</span></span>  
 <span data-ttu-id="55ebe-136">一个 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 功能，它向业务用户提供各种业务流程的实时视图。</span><span class="sxs-lookup"><span data-stu-id="55ebe-136">A [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] feature that gives business users a real-time view of their heterogeneous business processes.</span></span> <span data-ttu-id="55ebe-137">这使他们能够做出重要的业务决策。</span><span class="sxs-lookup"><span data-stu-id="55ebe-137">This enables them to make important business decisions.</span></span>  
  
 <span data-ttu-id="55ebe-138">**业务信号**</span><span class="sxs-lookup"><span data-stu-id="55ebe-138">**business signal**</span></span>  
 <span data-ttu-id="55ebe-139">RosettaNet 消息，例如 ReceiptAcknowledgement 或异常，两个 RosettaNet 网络应用程序进行通信的 PIP 实例执行过程中的某些事件之间交换。</span><span class="sxs-lookup"><span data-stu-id="55ebe-139">A RosettaNet message, such as a ReceiptAcknowledgement or Exception, exchanged between two RosettaNet network applications to communicate certain events in the execution of a PIP instance.</span></span> <span data-ttu-id="55ebe-140">业务操作，以及这些信号构成了所需的元素以完成指定特定 PIP 的业务活动。</span><span class="sxs-lookup"><span data-stu-id="55ebe-140">Together with business actions, these signals make up the necessary elements to complete the business activity specified by a particular PIP.</span></span>  
 
  
## <a name="c"></a><span data-ttu-id="55ebe-141">C</span><span class="sxs-lookup"><span data-stu-id="55ebe-141">C</span></span>  
 <span data-ttu-id="55ebe-142">**CertWizard**</span><span class="sxs-lookup"><span data-stu-id="55ebe-142">**CertWizard**</span></span>  
 <span data-ttu-id="55ebe-143">用于签名或加密证书 (.p12).pfx 或.cer (.der) 文件中导入与 BTARN 一起使用的私有或公用存储区的实用工具。</span><span class="sxs-lookup"><span data-stu-id="55ebe-143">A utility to import a signing or encryption certificate from a .pfx (.p12) or .cer (.der) file into a private or public store for use with BTARN.</span></span> <span data-ttu-id="55ebe-144">.Pfx 文件，也称为个人信息交换-PKCS #12，通常受密码，因为它包含用于解密或签名的私钥。</span><span class="sxs-lookup"><span data-stu-id="55ebe-144">A .pfx file, also known as Personal Information Exchange–PKCS #12, is typically protected by a password as it holds a private key that is used for decryption or signing.</span></span> <span data-ttu-id="55ebe-145">.Cer 文件 （证书文件） 包含用于加密和验证签名的公钥。</span><span class="sxs-lookup"><span data-stu-id="55ebe-145">A .cer file (certificate file) holds the public key for encryption and validation of the signature.</span></span>  
  
 <span data-ttu-id="55ebe-146">**筛选数据交换 (CIDX) Chem eStandards**</span><span class="sxs-lookup"><span data-stu-id="55ebe-146">**Chemical Data Exchange (CIDX) Chem eStandards**</span></span>  
 <span data-ttu-id="55ebe-147">专门为购买、 销售，和传递化学品开发统一标准的数据交换。</span><span class="sxs-lookup"><span data-stu-id="55ebe-147">Uniform standards of data exchange developed specifically for the buying, selling, and delivery of chemicals.</span></span> <span data-ttu-id="55ebe-148">这些标准基于对于电子数据交换的公认标准-XML。</span><span class="sxs-lookup"><span data-stu-id="55ebe-148">These standards are based on the universally recognized standards for electronic data exchange—XML.</span></span> <span data-ttu-id="55ebe-149">BTARN 支持 CIDX Chem eStandards。</span><span class="sxs-lookup"><span data-stu-id="55ebe-149">BTARN supports CIDX Chem eStandards.</span></span>  
  
 <span data-ttu-id="55ebe-150">**群集**</span><span class="sxs-lookup"><span data-stu-id="55ebe-150">**cluster**</span></span>  
 <span data-ttu-id="55ebe-151">高级业务流程，例如订单管理、 库存管理或服务和支持组。</span><span class="sxs-lookup"><span data-stu-id="55ebe-151">A group of high-level business processes, such as order management, inventory management, or service and support.</span></span> <span data-ttu-id="55ebe-152">由 RosettaNet 确定分类表示供应链行业的核心业务流程。</span><span class="sxs-lookup"><span data-stu-id="55ebe-152">The clusters addressed by RosettaNet represent core business processes for the supply chain industry.</span></span>  
  
## <a name="d"></a><span data-ttu-id="55ebe-153">D</span><span class="sxs-lookup"><span data-stu-id="55ebe-153">D</span></span>  
 <span data-ttu-id="55ebe-154">**数据通用编号系统 (D-U-N-S) 编号**</span><span class="sxs-lookup"><span data-stu-id="55ebe-154">**Data Universal Numbering System (D-U-N-S) number**</span></span>  
 <span data-ttu-id="55ebe-155">按顺序生成的包含 9 位数字，用于唯一标识业务位置，以及的作用域具有全局性。</span><span class="sxs-lookup"><span data-stu-id="55ebe-155">A sequentially generated nine-digit number that uniquely identifies business locations, and is global in scope.</span></span>  
  
 <span data-ttu-id="55ebe-156">**传递标头**</span><span class="sxs-lookup"><span data-stu-id="55ebe-156">**delivery header**</span></span>  
 <span data-ttu-id="55ebe-157">RosettaNet 消息的一部分。</span><span class="sxs-lookup"><span data-stu-id="55ebe-157">A part of a RosettaNet message.</span></span> <span data-ttu-id="55ebe-158">传递标头是一个标识邮件发件人、 收件人和消息实例信息的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="55ebe-158">The delivery header is an XML document that identifies the message sender, the recipient, and message instance information.</span></span>  
  
 <span data-ttu-id="55ebe-159">**目标组织**</span><span class="sxs-lookup"><span data-stu-id="55ebe-159">**destination organization**</span></span>  
 <span data-ttu-id="55ebe-160">用作文档的目标已指定在消息传递端口中的组织。</span><span class="sxs-lookup"><span data-stu-id="55ebe-160">An organization that has been designated in a messaging port as the destination for documents.</span></span>  
  
 <span data-ttu-id="55ebe-161">**数字算法**</span><span class="sxs-lookup"><span data-stu-id="55ebe-161">**digital algorithms**</span></span>  
 <span data-ttu-id="55ebe-162">将作为输入一条消息，并生成哈希或它一组固定长度以某种非常复杂的方式取决于消息内容的位的摘要算法。</span><span class="sxs-lookup"><span data-stu-id="55ebe-162">An algorithm that takes a message as input and produces a hash or digest of it, a fixed-length set of bits that depend on the message contents in some highly complex manner.</span></span> <span data-ttu-id="55ebe-163">设计标准包括这使得任何人伪造摘要或更改一条消息，而不更改其摘要式极其困难。</span><span class="sxs-lookup"><span data-stu-id="55ebe-163">Design criteria include making it extremely difficult for anyone to counterfeit a digest or to change a message without changing its digest.</span></span> <span data-ttu-id="55ebe-164">应用程序通常使用摘要算法是在消息身份验证和数字签名方案。</span><span class="sxs-lookup"><span data-stu-id="55ebe-164">Applications that typically use digest algorithms are in message authentication and digital signature schemes.</span></span> <span data-ttu-id="55ebe-165">广泛使用的算法包括 MD5 和 SHA1。</span><span class="sxs-lookup"><span data-stu-id="55ebe-165">Widely used algorithms include MD5 and SHA1.</span></span> <span data-ttu-id="55ebe-166">BTARN 支持 MD5 和 SHA1 对于传入消息，并仅 SHA1 为传出消息。</span><span class="sxs-lookup"><span data-stu-id="55ebe-166">BTARN supports both MD5 and SHA1 for incoming messages, and only SHA1 for outgoing messages.</span></span>  
  
 <span data-ttu-id="55ebe-167">**文档定义**</span><span class="sxs-lookup"><span data-stu-id="55ebe-167">**document definition**</span></span>  
 <span data-ttu-id="55ebe-168">表示特定文档的属性集。</span><span class="sxs-lookup"><span data-stu-id="55ebe-168">A set of properties that represents a specific document.</span></span> <span data-ttu-id="55ebe-169">文档定义属性包括指向文档规范的并且只能包含全局跟踪字段和选择条件。</span><span class="sxs-lookup"><span data-stu-id="55ebe-169">Document definition properties include a pointer to a document specification and can include global tracking fields and selection criteria.</span></span>  
  
 <span data-ttu-id="55ebe-170">**文档实例**</span><span class="sxs-lookup"><span data-stu-id="55ebe-170">**document instance**</span></span>  
 <span data-ttu-id="55ebe-171">发送到 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 的实际数据的表示形式。</span><span class="sxs-lookup"><span data-stu-id="55ebe-171">A representation of the actual data that is sent to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="55ebe-172">文档实例与不同，文档规范的规范定义的数据结构的文档实例时的表示形式包含在结构的特定数据。</span><span class="sxs-lookup"><span data-stu-id="55ebe-172">A document instance differs from a document specification in that the specification defines the structure of the data, while a document instance is a representation of the specific data that is contained in a structure.</span></span>  
  
 <span data-ttu-id="55ebe-173">**文档类型定义 (DTD)**</span><span class="sxs-lookup"><span data-stu-id="55ebe-173">**document type definition (DTD)**</span></span>  
 <span data-ttu-id="55ebe-174">指定的元素和属性的标准定义可能会出现在其他元素和属性，用于指定其排序、 频率和内容的任何约束。</span><span class="sxs-lookup"><span data-stu-id="55ebe-174">A standard definition that specifies which elements and attributes might be present in other elements and attributes and that specifies any constraints on their ordering, frequency, and content.</span></span>  
  
 <span data-ttu-id="55ebe-175">**double 操作事务** </span><span class="sxs-lookup"><span data-stu-id="55ebe-175">**double action transaction** </span></span>  
 <span data-ttu-id="55ebe-176">其中发起方发送一个请求的操作，一个进程收到信号，其后是从响应方的响应操作。</span><span class="sxs-lookup"><span data-stu-id="55ebe-176">A process where an initiator sends a request action, receives a signal, followed by a response action from the responder.</span></span> <span data-ttu-id="55ebe-177">发起方将通过将信号发送到响应操作完成过程。</span><span class="sxs-lookup"><span data-stu-id="55ebe-177">The initiator finishes the process by sending a signal to the response action.</span></span>  
  
## <a name="e"></a><span data-ttu-id="55ebe-178">E</span><span class="sxs-lookup"><span data-stu-id="55ebe-178">E</span></span>  
 <span data-ttu-id="55ebe-179">**可扩展标记语言 (XML)**</span><span class="sxs-lookup"><span data-stu-id="55ebe-179">**Extensible Markup Language (XML)**</span></span>  
 <span data-ttu-id="55ebe-180">由万维网联合会 (W3C) 规范，它使设计器来创建超出标准 HTML 功能的自定义的标记。</span><span class="sxs-lookup"><span data-stu-id="55ebe-180">A specification developed by the World Wide Web Consortium (W3C) that enables designers to create customized tags beyond the capabilities of standard HTML.</span></span> <span data-ttu-id="55ebe-181">尽管 HTML 使用仅预定义的标记来描述页中的元素，XML 将使页面的开发人员定义的标记。</span><span class="sxs-lookup"><span data-stu-id="55ebe-181">While HTML uses only predefined tags to describe elements in the page, XML enables tags to be defined by the developer of the page.</span></span> <span data-ttu-id="55ebe-182">对于几乎任何数据项，如产品或金额，由于标记可以用于特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="55ebe-182">Tags for virtually any data item, such as a product or an amount due, can be used for specific applications.</span></span> <span data-ttu-id="55ebe-183">这使网页能够充当数据库记录。</span><span class="sxs-lookup"><span data-stu-id="55ebe-183">This enables Web pages to function as database records.</span></span>  
  
 <span data-ttu-id="55ebe-184">**可扩展样式表语言 (XSL)**</span><span class="sxs-lookup"><span data-stu-id="55ebe-184">**Extensible Stylesheet Language (XSL)**</span></span>  
 <span data-ttu-id="55ebe-185">样式表的格式为 XML 文档的。</span><span class="sxs-lookup"><span data-stu-id="55ebe-185">A style sheet format for XML documents.</span></span> <span data-ttu-id="55ebe-186">XSL 用于一样级联样式表 (CSS) 用于定义的 HTML 显示定义的 XML 的显示。</span><span class="sxs-lookup"><span data-stu-id="55ebe-186">XSL is used to define the display of XML just like cascading style sheets (CSS) are used to define the display of HTML.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="55ebe-187"> 使用 XSL 作为两个规范之间的转换语言。</span><span class="sxs-lookup"><span data-stu-id="55ebe-187"> uses XSL as the translation language between two specifications.</span></span>  
  
## <a name="g"></a><span data-ttu-id="55ebe-188">G</span><span class="sxs-lookup"><span data-stu-id="55ebe-188">G</span></span>  
 <span data-ttu-id="55ebe-189">**全局业务标识 (GBI)**</span><span class="sxs-lookup"><span data-stu-id="55ebe-189">**Global Business Identification (GBI)**</span></span>  
 <span data-ttu-id="55ebe-190">若要标识贸易方唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="55ebe-190">A unique identifier to identify trading parties.</span></span> <span data-ttu-id="55ebe-191">RosettaNet GBI 中用作九位数 Dun 和 Bradstreet 编码系统 (DUNS)。</span><span class="sxs-lookup"><span data-stu-id="55ebe-191">RosettaNet uses the nine-digit Dun and Bradstreet Numbering System (DUNS) as the GBI.</span></span>  
  
## <a name="h"></a><span data-ttu-id="55ebe-192">H</span><span class="sxs-lookup"><span data-stu-id="55ebe-192">H</span></span>  
 <span data-ttu-id="55ebe-193">**本组织** </span><span class="sxs-lookup"><span data-stu-id="55ebe-193">**home organization** </span></span>  
 <span data-ttu-id="55ebe-194">别名以识别您的组织。</span><span class="sxs-lookup"><span data-stu-id="55ebe-194">An alias to identify your organization.</span></span>  
  
## <a name="i"></a><span data-ttu-id="55ebe-195">I</span><span class="sxs-lookup"><span data-stu-id="55ebe-195">I</span></span>  
 <span data-ttu-id="55ebe-196">**发起程序**</span><span class="sxs-lookup"><span data-stu-id="55ebe-196">**initiator**</span></span>  
 <span data-ttu-id="55ebe-197">启动到贸易合作伙伴过程的事务或通知过程中组织的角色。</span><span class="sxs-lookup"><span data-stu-id="55ebe-197">The role of an organization in a transaction or notification process that initiates a process to a trading partner.</span></span>  
  
## <a name="l"></a><span data-ttu-id="55ebe-198">L</span><span class="sxs-lookup"><span data-stu-id="55ebe-198">L</span></span>  
 <span data-ttu-id="55ebe-199">**(LOB) 业务线应用程序**</span><span class="sxs-lookup"><span data-stu-id="55ebe-199">**Line of Business (LOB) Application**</span></span>  
 <span data-ttu-id="55ebe-200">应用程序作为后端系统 BTARN 与之通信。</span><span class="sxs-lookup"><span data-stu-id="55ebe-200">The application that communicates with BTARN as the backend system.</span></span>  
  
 <span data-ttu-id="55ebe-201">**环回实用程序**</span><span class="sxs-lookup"><span data-stu-id="55ebe-201">**Loopback utility**</span></span>  
 <span data-ttu-id="55ebe-202">用于开发人员能够自动生成实例是镜像副本主页合作伙伴协议的环回协议的实用程序。</span><span class="sxs-lookup"><span data-stu-id="55ebe-202">A utility for developers to automatically generate a loopback agreement that is a mirror copy of a home-to-partner agreement.</span></span> <span data-ttu-id="55ebe-203">这使你能够在单个计算机上执行本组织到合作伙伴以及合作伙伴到本组织的消息交换。</span><span class="sxs-lookup"><span data-stu-id="55ebe-203">This lets you perform home-to-partner and partner-to-home message exchanges on a single computer.</span></span>  
  
## <a name="m"></a><span data-ttu-id="55ebe-204">M</span><span class="sxs-lookup"><span data-stu-id="55ebe-204">M</span></span>  
 <span data-ttu-id="55ebe-205">**映射**</span><span class="sxs-lookup"><span data-stu-id="55ebe-205">**map**</span></span>  
 <span data-ttu-id="55ebe-206">定义一种规范的记录和字段与另一种规范的记录和字段之间对应关系的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="55ebe-206">An XML file that defines the correspondence between the records and fields in one specification and the records and fields in another specification.</span></span> <span data-ttu-id="55ebe-207">映射中包含一个 XSL 样式表，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 使用该样式表来执行映射中描述的转换。</span><span class="sxs-lookup"><span data-stu-id="55ebe-207">A map contains an XSL style sheet that [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] uses to perform the transformation described in the map.</span></span> <span data-ttu-id="55ebe-208">在 BizTalk 映射程序中创建映射。</span><span class="sxs-lookup"><span data-stu-id="55ebe-208">Maps are created in BizTalk Mapper.</span></span>
  
 <span data-ttu-id="55ebe-209">**我的组织**</span><span class="sxs-lookup"><span data-stu-id="55ebe-209">**my organization**</span></span>  
 <span data-ttu-id="55ebe-210">在贸易合作伙伴协议表示你的组织。</span><span class="sxs-lookup"><span data-stu-id="55ebe-210">Represents your organization in a trading partner agreement.</span></span>   
  
 <span data-ttu-id="55ebe-211">**多用途 Internet 邮件扩展 (MIME)**</span><span class="sxs-lookup"><span data-stu-id="55ebe-211">**Multi-Purpose Internet Mail Extensions (MIME)**</span></span>  
 <span data-ttu-id="55ebe-212">允许你的 Internet 电子邮件协议的扩展使用协议交换不同类型的 Internet 上的数据文件： 音频、 视频、 图像和应用程序。</span><span class="sxs-lookup"><span data-stu-id="55ebe-212">An extension of the Internet e-mail protocol that lets you use the protocol to exchange different kinds of data files on the Internet: audio, video, images, and application programs.</span></span>  
  
## <a name="n"></a><span data-ttu-id="55ebe-213">否</span><span class="sxs-lookup"><span data-stu-id="55ebe-213">N</span></span>  
 <span data-ttu-id="55ebe-214">**不可否认性**</span><span class="sxs-lookup"><span data-stu-id="55ebe-214">**non-repudiation**</span></span>  
 <span data-ttu-id="55ebe-215">若要确保消息的发件人无法更高版本无法识别发件人发送消息和接收方无法拒绝无收到了消息，一种方式。</span><span class="sxs-lookup"><span data-stu-id="55ebe-215">A way to make sure that the sender of a message cannot later refuse to recognize that the sender sent the message and that the recipient cannot deny having received the message.</span></span> <span data-ttu-id="55ebe-216">传入消息的不可否认性要求，则接收方，保存该消息和消息应具有数字签名使用发件人的签名证书以确保其可靠性。</span><span class="sxs-lookup"><span data-stu-id="55ebe-216">Non-repudiation of an incoming message requires that the message be saved by the receiver, and that the message should carry a digital signature using the signing certificate of the sender to ensure its authenticity.</span></span> <span data-ttu-id="55ebe-217">不可否认性传出消息，则需要保存确认消息 （从第一条消息的接收方的传入消息），消息应具有与原始的摘要的数字签名消息和使用的签名接收方的证书。</span><span class="sxs-lookup"><span data-stu-id="55ebe-217">Non-repudiation of an outgoing message requires saving the acknowledgement message (incoming message from the recipient of the first message), and that the message should carry the digital signature of the digest of the original message using the signing certificate of the recipient.</span></span>   
  
 <span data-ttu-id="55ebe-218">**通知**</span><span class="sxs-lookup"><span data-stu-id="55ebe-218">**notification**</span></span>  
 <span data-ttu-id="55ebe-219">其中发起方通知与单个消息响应方 RNIF 1.1 进程类型。</span><span class="sxs-lookup"><span data-stu-id="55ebe-219">An RNIF 1.1 process type where the initiator notifies the responder with a single message.</span></span> <span data-ttu-id="55ebe-220">响应方应使用业务信号作为确认答复。</span><span class="sxs-lookup"><span data-stu-id="55ebe-220">The responder is expected to reply with a business signal as an acknowledgement.</span></span>  
  
 <span data-ttu-id="55ebe-221">**失败 (PIP 0A1) 的通知**</span><span class="sxs-lookup"><span data-stu-id="55ebe-221">**Notification of Failure (PIP 0A1)**</span></span>  
 <span data-ttu-id="55ebe-222">特殊 PIP，该值指示进程意外的失败。</span><span class="sxs-lookup"><span data-stu-id="55ebe-222">A special PIP that indicates unexpected process failures.</span></span> <span data-ttu-id="55ebe-223">发起方还是对响应方可以启动故障通知。</span><span class="sxs-lookup"><span data-stu-id="55ebe-223">The initiator or the responder can initiate a Notification of Failure.</span></span> <span data-ttu-id="55ebe-224">它将引用为现有的或以前交换过程。</span><span class="sxs-lookup"><span data-stu-id="55ebe-224">It refers to an existing or previously exchanged process.</span></span> <span data-ttu-id="55ebe-225">收到 0A1，接收方可以确保，引用的过程被视为不有效。</span><span class="sxs-lookup"><span data-stu-id="55ebe-225">Upon receipt of a 0A1, the receiving party makes sure that the referenced process is considered not valid.</span></span>  
  
## <a name="o"></a><span data-ttu-id="55ebe-226">O</span><span class="sxs-lookup"><span data-stu-id="55ebe-226">O</span></span>  
 <span data-ttu-id="55ebe-227">**组织**</span><span class="sxs-lookup"><span data-stu-id="55ebe-227">**organization**</span></span>  
 <span data-ttu-id="55ebe-228">贸易合作伙伴或业务单位，可以执行业务事务。</span><span class="sxs-lookup"><span data-stu-id="55ebe-228">A trading partner or a business unit that can conduct business transactions.</span></span>  
  
## <a name="p"></a><span data-ttu-id="55ebe-229">P</span><span class="sxs-lookup"><span data-stu-id="55ebe-229">P</span></span>  
 <span data-ttu-id="55ebe-230">**打包**</span><span class="sxs-lookup"><span data-stu-id="55ebe-230">**packaging**</span></span>  
 <span data-ttu-id="55ebe-231">将转换其 XML 表示形式中，反之亦然 RosettaNet 消息的过程。</span><span class="sxs-lookup"><span data-stu-id="55ebe-231">The process of converting a RosettaNet message in its XML representation and vice versa.</span></span>  
  
 <span data-ttu-id="55ebe-232">**合作伙伴接口过程 (PIP)**</span><span class="sxs-lookup"><span data-stu-id="55ebe-232">**Partner Interface Process (PIP)**</span></span>  
 <span data-ttu-id="55ebe-233">PIP 描述一组的业务文档和协议详细信息，包括文档内容的详细信息。</span><span class="sxs-lookup"><span data-stu-id="55ebe-233">A PIP describes a set of business documents and agreement details, including document content details.</span></span>  
  
 <span data-ttu-id="55ebe-234">**PIP 规范文档**</span><span class="sxs-lookup"><span data-stu-id="55ebe-234">**PIP Specification document**</span></span>  
 <span data-ttu-id="55ebe-235">包含有关要使用当你在 BTARN 管理控制台中创建过程配置的设置指南的文档。</span><span class="sxs-lookup"><span data-stu-id="55ebe-235">A document that contains guidance about the settings to use when you create a process configuration in the BTARN Management Console.</span></span> <span data-ttu-id="55ebe-236">你从 RosettaNet 组织，RosettaNet.org 下载 PIP 规范文档和 PIP。包含有关要使用当你在 BTARN 管理控制台中创建过程配置的设置指南的文档。</span><span class="sxs-lookup"><span data-stu-id="55ebe-236">You download the PIP Specification document and the PIP from the RosettaNet organization, from RosettaNet.org. A document that contains guidance about the settings to use when you create a process configuration in the BTARN Management Console.</span></span> <span data-ttu-id="55ebe-237">你从 RosettaNet 组织，RosettaNet.org 下载 PIP 规范文档和 PIP。</span><span class="sxs-lookup"><span data-stu-id="55ebe-237">You download the PIP Specification document and the PIP from the RosettaNet organization, from RosettaNet.org.</span></span>  
  
 <span data-ttu-id="55ebe-238">**前导码标头**</span><span class="sxs-lookup"><span data-stu-id="55ebe-238">**preamble header**</span></span>  
 <span data-ttu-id="55ebe-239">标识的名称和版本的业务消息与之符合标准的 XML 节点。</span><span class="sxs-lookup"><span data-stu-id="55ebe-239">An XML node that identifies the name and version of the standard with which a business message is compliant.</span></span> <span data-ttu-id="55ebe-240">它与其他标头，以形成完整的 RosettaNet 消息一起打包。</span><span class="sxs-lookup"><span data-stu-id="55ebe-240">It is packaged together with other headers to form a complete RosettaNet Message.</span></span> <span data-ttu-id="55ebe-241">也称为前导码。</span><span class="sxs-lookup"><span data-stu-id="55ebe-241">Also named preamble.</span></span>  
  
 <span data-ttu-id="55ebe-242">**专用流程** </span><span class="sxs-lookup"><span data-stu-id="55ebe-242">**private process** </span></span>  
 <span data-ttu-id="55ebe-243">属于组织内部的业务流程。</span><span class="sxs-lookup"><span data-stu-id="55ebe-243">Business processes that are internal to an organization.</span></span> <span data-ttu-id="55ebe-244">BTARN 实现私有进程作为长时间运行 BizTalk 业务流程。</span><span class="sxs-lookup"><span data-stu-id="55ebe-244">BTARN implements private processes as long-running BizTalk orchestrations.</span></span>  
  
 <span data-ttu-id="55ebe-245">**进程配置设置 (PC) 配置文件**</span><span class="sxs-lookup"><span data-stu-id="55ebe-245">**Process Configuration Setting (PCS) profile**</span></span>  
 <span data-ttu-id="55ebe-246">确定合作伙伴协议的运行方式。</span><span class="sxs-lookup"><span data-stu-id="55ebe-246">Determines how a partner agreement runs.</span></span> <span data-ttu-id="55ebe-247">使用电脑配置文件输入配置详细信息的 RosettaNet 合作伙伴接口过程 (PIP)。</span><span class="sxs-lookup"><span data-stu-id="55ebe-247">You use the PCS profile to enter the configuration details of a RosettaNet Partner Interface Process (PIP).</span></span> <span data-ttu-id="55ebe-248">RosettaNet PIP 规范映射到的电脑配置文件中的一个元素中指定的所有配置值。</span><span class="sxs-lookup"><span data-stu-id="55ebe-248">All configuration values specified in a RosettaNet PIP specification map to one element in the PCS profile.</span></span> <span data-ttu-id="55ebe-249">一个电脑配置文件可用于多个合作伙伴协议。</span><span class="sxs-lookup"><span data-stu-id="55ebe-249">You can use one PCS profile for multiple partner agreements.</span></span>  
  
 <span data-ttu-id="55ebe-250">**port**</span><span class="sxs-lookup"><span data-stu-id="55ebe-250">**port**</span></span>  
 <span data-ttu-id="55ebe-251">命名的位置使用的特定实现。</span><span class="sxs-lookup"><span data-stu-id="55ebe-251">A named location that uses a specific implementation.</span></span> <span data-ttu-id="55ebe-252">在 BizTalk 业务流程设计器中，端口的定义方法的位置向其发送消息或从中接收消息，以及用于实现通信操作的技术。</span><span class="sxs-lookup"><span data-stu-id="55ebe-252">In BizTalk Orchestration Designer, a port is defined by the location to which messages are sent or from which messages are received, and the technology that is used to implement the communication action.</span></span> <span data-ttu-id="55ebe-253">该位置由端口名称唯一标识。</span><span class="sxs-lookup"><span data-stu-id="55ebe-253">The location is uniquely identified by the name of the port.</span></span>  
  
 <span data-ttu-id="55ebe-254">**公共过程** </span><span class="sxs-lookup"><span data-stu-id="55ebe-254">**public process** </span></span>  
 <span data-ttu-id="55ebe-255">包含与贸易合作伙伴作为公共进程的集成的业务流程。</span><span class="sxs-lookup"><span data-stu-id="55ebe-255">Business processes that involve integration with trading partners as public processes.</span></span> <span data-ttu-id="55ebe-256">BTARN 实现公共进程作为长时间运行 BizTalk 业务流程。</span><span class="sxs-lookup"><span data-stu-id="55ebe-256">BTARN implements public processes as long-running BizTalk orchestrations.</span></span> <span data-ttu-id="55ebe-257">在发起方和响应方各会运行一个公用业务流程。</span><span class="sxs-lookup"><span data-stu-id="55ebe-257">One public-process orchestration runs on the initiator side and one on the responder side.</span></span> <span data-ttu-id="55ebe-258">BTARN 安装程序将提供发起方和响应方公共进程业务流程 RNIF 1.1 和 RNIF 2.01 的版本。</span><span class="sxs-lookup"><span data-stu-id="55ebe-258">The BTARN Setup program provides versions of the initiator and responder public-process orchestrations for both RNIF 1.1 and RNIF 2.01.</span></span> <span data-ttu-id="55ebe-259">这些公用业务流程实现了所有的 RNIF 流程。</span><span class="sxs-lookup"><span data-stu-id="55ebe-259">These public-process orchestrations implement all RNIF processes.</span></span> <span data-ttu-id="55ebe-260">公用流程使 RNIF 对于其他组件来说变得相对简单了。</span><span class="sxs-lookup"><span data-stu-id="55ebe-260">Public processes hide the complexity of RNIF from the rest of the components.</span></span> <span data-ttu-id="55ebe-261">除了强制实施 RNIF 符合消息流时，公共过程还确定默认跟踪设置，并提供在运行时的处理状态信息。</span><span class="sxs-lookup"><span data-stu-id="55ebe-261">Besides enforcing the RNIF-compliant message flow, the public process also determines default-tracking settings and provides process state information at runtime.</span></span>  
  
## <a name="r"></a><span data-ttu-id="55ebe-262">R</span><span class="sxs-lookup"><span data-stu-id="55ebe-262">R</span></span>  
 <span data-ttu-id="55ebe-263">**响应方**</span><span class="sxs-lookup"><span data-stu-id="55ebe-263">**responder**</span></span>  
 <span data-ttu-id="55ebe-264">贸易合作伙伴的请求响应的事务或通知过程中组织的角色。</span><span class="sxs-lookup"><span data-stu-id="55ebe-264">The role of an organization in a transaction or notification process that responds to a request by a trading partner.</span></span>  
  
 <span data-ttu-id="55ebe-265">**RosettaNet 实现框架 (RNIF)**</span><span class="sxs-lookup"><span data-stu-id="55ebe-265">**RosettaNet Implementation Framework (RNIF)**</span></span>  
 <span data-ttu-id="55ebe-266">一种标准框架，为想要创建可互操作的软件应用程序组件的运行 Pip 这些公司提供实施准则。</span><span class="sxs-lookup"><span data-stu-id="55ebe-266">A standards framework that provides implementation guidelines for those companies that want to create interoperable software application components that run PIPs.</span></span>  
  
 <span data-ttu-id="55ebe-267">**RosettaNet 消息**</span><span class="sxs-lookup"><span data-stu-id="55ebe-267">**RosettaNet message**</span></span>  
 <span data-ttu-id="55ebe-268">前导码标头、 传递标头 （如果 RNIF 2.0)、 服务标头和服务内容的逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="55ebe-268">The logical grouping of the preamble header, delivery header (in the case of RNIF 2.0), service header, and service content.</span></span>  
  
 <span data-ttu-id="55ebe-269">**RosettaNet 对象**</span><span class="sxs-lookup"><span data-stu-id="55ebe-269">**RosettaNet object**</span></span>  
 <span data-ttu-id="55ebe-270">封装对 RosettaNet 实现 Framework 1.1 版中的交付 RosettaNet 消息。</span><span class="sxs-lookup"><span data-stu-id="55ebe-270">A RosettaNet message enveloped for delivery in RosettaNet Implementation Framework version 1.1.</span></span>  
  
## <a name="s"></a><span data-ttu-id="55ebe-271">S</span><span class="sxs-lookup"><span data-stu-id="55ebe-271">S</span></span>  
 <span data-ttu-id="55ebe-272">**schema**</span><span class="sxs-lookup"><span data-stu-id="55ebe-272">**schema**</span></span>  
 <span data-ttu-id="55ebe-273">XML 文件的结构的定义。</span><span class="sxs-lookup"><span data-stu-id="55ebe-273">The definition of the structure of an XML file.</span></span> <span data-ttu-id="55ebe-274">架构包含属性信息，因为它涉及到的记录和结构中的字段。</span><span class="sxs-lookup"><span data-stu-id="55ebe-274">A schema contains property information as it pertains to the records and fields in the structure.</span></span>  
  
 <span data-ttu-id="55ebe-275">**服务的内容**</span><span class="sxs-lookup"><span data-stu-id="55ebe-275">**service content**</span></span>  
 <span data-ttu-id="55ebe-276">RosettaNet 消息主要组件。</span><span class="sxs-lookup"><span data-stu-id="55ebe-276">The primary component of the RosettaNet message.</span></span> <span data-ttu-id="55ebe-277">它是表示业务内容由特定 PIP 指定的 XML 节点。</span><span class="sxs-lookup"><span data-stu-id="55ebe-277">It is an XML node that represents the business content specified by a particular PIP.</span></span>  
  
 <span data-ttu-id="55ebe-278">**服务标头**</span><span class="sxs-lookup"><span data-stu-id="55ebe-278">**service header**</span></span>  
 <span data-ttu-id="55ebe-279">XML 文档可标识与业务消息，包括 PIP、 业务活动和操作，发送和接收服务、 贸易合作伙伴和角色关联的部分。</span><span class="sxs-lookup"><span data-stu-id="55ebe-279">An XML document that identifies the parts associated with a business message, including the PIP, business activity and action, sending and receiving services, trading partners, and roles.</span></span>  
  
 <span data-ttu-id="55ebe-280">**信号 URL**</span><span class="sxs-lookup"><span data-stu-id="55ebe-280">**signal URL**</span></span>  
 <span data-ttu-id="55ebe-281">本组织将信号消息传输的 URL。</span><span class="sxs-lookup"><span data-stu-id="55ebe-281">The URL to which the home organization transmits a signal message.</span></span> <span data-ttu-id="55ebe-282">例如， http://FabrikamServer/BTARNApp/RNIFReceive.aspx。</span><span class="sxs-lookup"><span data-stu-id="55ebe-282">For example, http://FabrikamServer/BTARNApp/RNIFReceive.aspx.</span></span>  
  
 <span data-ttu-id="55ebe-283">**单个操作通知**</span><span class="sxs-lookup"><span data-stu-id="55ebe-283">**single action notification**</span></span>  
 <span data-ttu-id="55ebe-284">发起方将单个操作消息和响应方发送的进程使用消息进行回复。</span><span class="sxs-lookup"><span data-stu-id="55ebe-284">A process where the initiator sends a single action message and the responder replies with a message.</span></span>  
  
 <span data-ttu-id="55ebe-285">**规范**</span><span class="sxs-lookup"><span data-stu-id="55ebe-285">**specification**</span></span>  
 <span data-ttu-id="55ebe-286">特定于 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="55ebe-286">A [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]-specific XML schema.</span></span> <span data-ttu-id="55ebe-287">创建 BizTalk 编辑器中的规范，并可以基于行业标准，如 EDIFACT、 X12 和 XML，或在平面文件，例如分隔，位置，或分隔和位置。</span><span class="sxs-lookup"><span data-stu-id="55ebe-287">You create specifications in BizTalk Editor and can be based on industry standards, such as EDIFACT, X12, and XML, or on flat files, such as delimited, positional, or delimited and positional.</span></span> <span data-ttu-id="55ebe-288">BizTalk 映射程序使用规范，作为源规范和目标规范，打开创建地图。</span><span class="sxs-lookup"><span data-stu-id="55ebe-288">BizTalk Mapper uses specifications, opened as source specifications and destination specifications, to create maps.</span></span>  
  
 <span data-ttu-id="55ebe-289">**同步 URL**</span><span class="sxs-lookup"><span data-stu-id="55ebe-289">**sync URL**</span></span>  
 <span data-ttu-id="55ebe-290">本组织用于建立与伙伴，例如，同步事务的 URL http://FabikamServer/BTARNApp/RNIFReceive.aspx。</span><span class="sxs-lookup"><span data-stu-id="55ebe-290">The URL that the home organization uses to establish synchronous transactions with the partner, for example, http://FabikamServer/BTARNApp/RNIFReceive.aspx.</span></span>  
  
 <span data-ttu-id="55ebe-291">**同步事务**</span><span class="sxs-lookup"><span data-stu-id="55ebe-291">**synchronous transaction**</span></span>  
 <span data-ttu-id="55ebe-292">过程，其中发起方返回响应 （双操作） 或信号 （单次操作） 的相同的 HTTP 状态而无需关闭连接。</span><span class="sxs-lookup"><span data-stu-id="55ebe-292">A process where the initiator returns a response (double-action) or signal (single-action) on the same HTTP state without closing the connection.</span></span>  
  
## <a name="t"></a><span data-ttu-id="55ebe-293">T</span><span class="sxs-lookup"><span data-stu-id="55ebe-293">T</span></span>  
 <span data-ttu-id="55ebe-294">**贸易合作伙伴**</span><span class="sxs-lookup"><span data-stu-id="55ebe-294">**trading partner**</span></span>  
 <span data-ttu-id="55ebe-295">外部组织你的组织与其交换电子数据。</span><span class="sxs-lookup"><span data-stu-id="55ebe-295">An external organization with which your organization exchanges electronic data.</span></span>  
  
 <span data-ttu-id="55ebe-296">**贸易合作伙伴协议**</span><span class="sxs-lookup"><span data-stu-id="55ebe-296">**trading partner agreement**</span></span>  
 <span data-ttu-id="55ebe-297">你的组织和贸易合作伙伴之间的协议。</span><span class="sxs-lookup"><span data-stu-id="55ebe-297">An agreement between your organization and your trading partner.</span></span> <span data-ttu-id="55ebe-298">贸易合作伙伴协议引用过程配置设置配置文件、 组织、 合作伙伴，并包含协议特定的配置设置。</span><span class="sxs-lookup"><span data-stu-id="55ebe-298">A trading partner agreement references a Process Configuration Setting profile, home organization, partner, and contains agreement specific configuration settings.</span></span>  
  
 <span data-ttu-id="55ebe-299">**事务**</span><span class="sxs-lookup"><span data-stu-id="55ebe-299">**transaction**</span></span>  
 <span data-ttu-id="55ebe-300">其中发起方发送 RosettaNet 消息时，一个 RNIF 1.1 过程收到信号，接收 RosettaNet 消息为答案，然后发送确认的信号。</span><span class="sxs-lookup"><span data-stu-id="55ebe-300">An RNIF 1.1 process where the initiator sends a RosettaNet message, receives a signal, receives a RosettaNet message as an answer, and sends a signal for acknowledgement.</span></span>  
  
## <a name="v"></a><span data-ttu-id="55ebe-301">V</span><span class="sxs-lookup"><span data-stu-id="55ebe-301">V</span></span>  
 <span data-ttu-id="55ebe-302">**验证适配器**</span><span class="sxs-lookup"><span data-stu-id="55ebe-302">**validation adapter**</span></span>  
 <span data-ttu-id="55ebe-303">实现的应用程序验证适配器接口。</span><span class="sxs-lookup"><span data-stu-id="55ebe-303">An application that implements the Validation Adapter interface.</span></span> <span data-ttu-id="55ebe-304">在接收操作消息 （请求或响应） 时，公共响应方调用验证适配器。</span><span class="sxs-lookup"><span data-stu-id="55ebe-304">The public responder invokes the Validation Adapter when it receives an action message (request or response).</span></span> <span data-ttu-id="55ebe-305">它可以包括任何组的业务可能需要再接受传入消息的验证规则。</span><span class="sxs-lookup"><span data-stu-id="55ebe-305">It can include any set of validation rules that a business may require before accepting an incoming message.</span></span> <span data-ttu-id="55ebe-306">BTARN 本机执行验证，接收管道中和在公共业务流程中。</span><span class="sxs-lookup"><span data-stu-id="55ebe-306">BTARN natively performs validation in the receive pipeline, and in public orchestrations.</span></span>  
  
## <a name="x"></a><span data-ttu-id="55ebe-307">X</span><span class="sxs-lookup"><span data-stu-id="55ebe-307">X</span></span>  
 <span data-ttu-id="55ebe-308">**XLANG 计划**</span><span class="sxs-lookup"><span data-stu-id="55ebe-308">**XLANG schedule**</span></span>  
 <span data-ttu-id="55ebe-309">一种特定的 XML 语言，描述业务流程和后端的集成。</span><span class="sxs-lookup"><span data-stu-id="55ebe-309">A specific XML language that describes business processes and back-end integration.</span></span> <span data-ttu-id="55ebe-310">XLANG 语言来表述 BTARN 中的特定业务流程。</span><span class="sxs-lookup"><span data-stu-id="55ebe-310">Specific business processes in BTARN are expressed in the XLANG language.</span></span> <span data-ttu-id="55ebe-311">文件名称扩展.skx 保存 XLANG 计划。</span><span class="sxs-lookup"><span data-stu-id="55ebe-311">An XLANG schedule is saved with the file name extension .skx.</span></span>  
  
