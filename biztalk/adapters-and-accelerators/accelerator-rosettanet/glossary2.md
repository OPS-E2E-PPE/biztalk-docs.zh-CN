---
title: 在 BizTalk Server 中的 RosettaNet 加速器的术语表 |Microsoft Docs
description: 通用术语和定义，以了解并了解如何使用 BizTalk Accelerator for RosettaNet
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
ms.openlocfilehash: 9c332c70137f391e2a0d026fa9fe56442ed3fa75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283693"
---
# <a name="glossary"></a><span data-ttu-id="82eba-103">词汇表</span><span class="sxs-lookup"><span data-stu-id="82eba-103">Glossary</span></span>
[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] <span data-ttu-id="82eba-104">使用以下术语表术语和定义。</span><span class="sxs-lookup"><span data-stu-id="82eba-104">uses the following glossary terms and definitions.</span></span>  

  
## <a name="a"></a><span data-ttu-id="82eba-105">A</span><span class="sxs-lookup"><span data-stu-id="82eba-105">A</span></span>  
 <span data-ttu-id="82eba-106">**application adapter**</span><span class="sxs-lookup"><span data-stu-id="82eba-106">**application adapter**</span></span>  
 <span data-ttu-id="82eba-107">实现应用程序适配器接口的应用程序。</span><span class="sxs-lookup"><span data-stu-id="82eba-107">An application that implements the application adapter interface.</span></span> <span data-ttu-id="82eba-108">接受传入操作消息 （请求或响应） 上的通知机制调用应用程序适配器。</span><span class="sxs-lookup"><span data-stu-id="82eba-108">The notification mechanism on the acceptance of an incoming action message (request or response) invokes the application adapter.</span></span> <span data-ttu-id="82eba-109">它实现了两种方法：`BeginNotify`和`EndNotify`。</span><span class="sxs-lookup"><span data-stu-id="82eba-109">It implements two methods: `BeginNotify` and `EndNotify`.</span></span> <span data-ttu-id="82eba-110">公用响应方调用`BeginNotify`方法，而开箱专用响应方调用`EndNotify`方法。</span><span class="sxs-lookup"><span data-stu-id="82eba-110">The public responder invokes the `BeginNotify` method, whereas the out-of-the-box private responder invokes the `EndNotify` method.</span></span> <span data-ttu-id="82eba-111">对调用`Notify`方法意味着该消息已成功保存到 MessagesToLOB 表。</span><span class="sxs-lookup"><span data-stu-id="82eba-111">The call to the `Notify` method means that the message was successfully saved into the MessagesToLOB table.</span></span>  
  
 <span data-ttu-id="82eba-112">**操作 URL**</span><span class="sxs-lookup"><span data-stu-id="82eba-112">**action URL**</span></span>  
 <span data-ttu-id="82eba-113">到本组织操作消息传送在异步过程，例如，合作伙伴 URL http://FabrikamServer/BTARNApp/RNIFReceive.aspx。</span><span class="sxs-lookup"><span data-stu-id="82eba-113">The partner URL to which the home organization transmits an action message during an asynchronous process, for example, http://FabrikamServer/BTARNApp/RNIFReceive.aspx.</span></span>  
  
## <a name="b"></a><span data-ttu-id="82eba-114">B</span><span class="sxs-lookup"><span data-stu-id="82eba-114">B</span></span>  
 <span data-ttu-id="82eba-115">**BizTalk Accelerator for RosettaNet**</span><span class="sxs-lookup"><span data-stu-id="82eba-115">**BizTalk Accelerator for RosettaNet**</span></span>  
 <span data-ttu-id="82eba-116">BizTalk Server 可帮助组织构建 RosettaNet 实现框架 (RNIF) 的一个附加产品-符合解决方案。</span><span class="sxs-lookup"><span data-stu-id="82eba-116">An add-on product to BizTalk Server that helps organizations to build RosettaNet Implementation Framework (RNIF)-compliant solutions.</span></span>  
  
 <span data-ttu-id="82eba-117">**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] 管理**</span><span class="sxs-lookup"><span data-stu-id="82eba-117">**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] Administration**</span></span>  
 <span data-ttu-id="82eba-118">Microsoft [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] ，可以描述流程模板和管理合作伙伴协议的应用程序。</span><span class="sxs-lookup"><span data-stu-id="82eba-118">A Microsoft [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] application that lets you describe process templates and manage partner agreements.</span></span>  
  
 <span data-ttu-id="82eba-119">**BizTalk Editor**</span><span class="sxs-lookup"><span data-stu-id="82eba-119">**BizTalk Editor**</span></span>  
 <span data-ttu-id="82eba-120">这可以用于创建、 编辑和管理规范工具。</span><span class="sxs-lookup"><span data-stu-id="82eba-120">A tool with which you can create, edit, and manage specifications.</span></span> <span data-ttu-id="82eba-121">使用 BizTalk 编辑器可以创建基于规范模板、 现有架构、 文档实例的某些类型的规范或空白的规范。</span><span class="sxs-lookup"><span data-stu-id="82eba-121">With BizTalk Editor you can create a specification based on a specification template, an existing schema, certain types of document instances, or a blank specification.</span></span>  
  
 <span data-ttu-id="82eba-122">**BizTalk 业务流程设计器**</span><span class="sxs-lookup"><span data-stu-id="82eba-122">**BizTalk Orchestration Designer**</span></span>  
 <span data-ttu-id="82eba-123">可用于创建描述长时间运行的图形设计工具松散耦合的可执行业务流程。</span><span class="sxs-lookup"><span data-stu-id="82eba-123">A design tool you can use to create drawings that describe long running, loosely coupled, executable business processes.</span></span> <span data-ttu-id="82eba-124">绘制的 XLANG 计划用于运行的自动化的业务程序 XLANG 计划中编译。</span><span class="sxs-lookup"><span data-stu-id="82eba-124">The XLANG schedule drawing is compiled in an XLANG schedule that you use to run the automated business process.</span></span>  
  
 <span data-ttu-id="82eba-125">**BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="82eba-125">**BizTalk Server**</span></span>  
 <span data-ttu-id="82eba-126">获取该 Microsoft 产品的业务流程自动化和应用程序集成中和企业间。</span><span class="sxs-lookup"><span data-stu-id="82eba-126">A Microsoft product for business-process automation and application integration both in and between businesses.</span></span> <span data-ttu-id="82eba-127">BizTalk Server 提供了功能强大的基于 Web 的开发和执行环境，它集成松散耦合，长时间运行业务流程，在和企业间。</span><span class="sxs-lookup"><span data-stu-id="82eba-127">BizTalk Server provides a powerful Web-based development and execution environment that integrates loosely coupled, long-running business processes, both in and between businesses.</span></span>  
  
 <span data-ttu-id="82eba-128">BizTalk Server 功能包括新的和现有 XLANG 调度; 的组合在现有应用程序; 之间的集成文档规范和规范转换的定义监视和运行时活动的日志记录。</span><span class="sxs-lookup"><span data-stu-id="82eba-128">BizTalk Server features include the composition of new and existing XLANG schedules; integration among existing applications; the definition of document specifications and specification transformations; and the monitoring and logging of run-time activity.</span></span>  
  
 <span data-ttu-id="82eba-129">服务器用于发送和接收文档在 Internet 上提供一个标准网关，并提供一系列可帮助确保数据完整性、 传送、 安全性和支持 BizTalk Framework 和其他密钥文档格式的服务。</span><span class="sxs-lookup"><span data-stu-id="82eba-129">The server provides a standard gateway for sending and receiving documents across the Internet, and provides a range of services that help to ensure data integrity, delivery, security, and support for the BizTalk Framework and other key document formats.</span></span>  
  
 <span data-ttu-id="82eba-130">**BtarnClean**</span><span class="sxs-lookup"><span data-stu-id="82eba-130">**BtarnClean**</span></span>  
 <span data-ttu-id="82eba-131">关闭计算机的干净 BTARN 项目到实用工具。</span><span class="sxs-lookup"><span data-stu-id="82eba-131">A utility to clean BTARN artifacts off a computer.</span></span>  
  
 <span data-ttu-id="82eba-132">**业务操作**</span><span class="sxs-lookup"><span data-stu-id="82eba-132">**business action**</span></span>  
 <span data-ttu-id="82eba-133">包含业务内容，如采购订单请求或引号的请求的 RosettaNet 消息。</span><span class="sxs-lookup"><span data-stu-id="82eba-133">A RosettaNet message that contains business content such as a purchase order request or a request for a quote.</span></span> <span data-ttu-id="82eba-134">业务信号，以及这些操作构成了所需的元素以完成业务活动指定的特定合作伙伴接口流程 (PIP)。</span><span class="sxs-lookup"><span data-stu-id="82eba-134">Together with business signals, these actions make up the necessary elements to complete the business activity specified by a particular Partner Interface Process (PIP).</span></span>  
  
 <span data-ttu-id="82eba-135">**业务活动监视 (BAM)**</span><span class="sxs-lookup"><span data-stu-id="82eba-135">**Business Activity Monitoring (BAM)**</span></span>  
 <span data-ttu-id="82eba-136">一个[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]为业务用户提供其异构业务流程的实时视图的功能。</span><span class="sxs-lookup"><span data-stu-id="82eba-136">A [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] feature that gives business users a real-time view of their heterogeneous business processes.</span></span> <span data-ttu-id="82eba-137">这使他们能够做出重要业务决策。</span><span class="sxs-lookup"><span data-stu-id="82eba-137">This enables them to make important business decisions.</span></span>  
  
 <span data-ttu-id="82eba-138">**业务信号**</span><span class="sxs-lookup"><span data-stu-id="82eba-138">**business signal**</span></span>  
 <span data-ttu-id="82eba-139">RosettaNet 消息，如 ReceiptAcknowledgement 或两个 RosettaNet 网络应用程序进行通信的 PIP 实例执行过程中的某些事件之间交换的异常。</span><span class="sxs-lookup"><span data-stu-id="82eba-139">A RosettaNet message, such as a ReceiptAcknowledgement or Exception, exchanged between two RosettaNet network applications to communicate certain events in the execution of a PIP instance.</span></span> <span data-ttu-id="82eba-140">业务操作，以及这些信号构成了所需的元素以完成指定特定 PIP 的业务活动。</span><span class="sxs-lookup"><span data-stu-id="82eba-140">Together with business actions, these signals make up the necessary elements to complete the business activity specified by a particular PIP.</span></span>  
 
  
## <a name="c"></a><span data-ttu-id="82eba-141">C</span><span class="sxs-lookup"><span data-stu-id="82eba-141">C</span></span>  
 <span data-ttu-id="82eba-142">**CertWizard**</span><span class="sxs-lookup"><span data-stu-id="82eba-142">**CertWizard**</span></span>  
 <span data-ttu-id="82eba-143">用于签名或加密证书 (.p12).pfx 或.cer (.der) 文件中导入用于 BTARN 专用或公用存储区的实用工具。</span><span class="sxs-lookup"><span data-stu-id="82eba-143">A utility to import a signing or encryption certificate from a .pfx (.p12) or .cer (.der) file into a private or public store for use with BTARN.</span></span> <span data-ttu-id="82eba-144">.Pfx 文件，也称为个人信息交换-PKCS #12，通常受密码，它包含用于解密或签名的私钥。</span><span class="sxs-lookup"><span data-stu-id="82eba-144">A .pfx file, also known as Personal Information Exchange–PKCS #12, is typically protected by a password as it holds a private key that is used for decryption or signing.</span></span> <span data-ttu-id="82eba-145">.Cer 文件 （证书文件） 包含用于加密和验证签名的公钥。</span><span class="sxs-lookup"><span data-stu-id="82eba-145">A .cer file (certificate file) holds the public key for encryption and validation of the signature.</span></span>  
  
 <span data-ttu-id="82eba-146">**化工数据交换 (CIDX) Chem eStandards**</span><span class="sxs-lookup"><span data-stu-id="82eba-146">**Chemical Data Exchange (CIDX) Chem eStandards**</span></span>  
 <span data-ttu-id="82eba-147">专门为购买、 销售和交付的化学物开发统一的数据交换标准。</span><span class="sxs-lookup"><span data-stu-id="82eba-147">Uniform standards of data exchange developed specifically for the buying, selling, and delivery of chemicals.</span></span> <span data-ttu-id="82eba-148">这些标准基于电子数据交换的公认标准 — XML。</span><span class="sxs-lookup"><span data-stu-id="82eba-148">These standards are based on the universally recognized standards for electronic data exchange—XML.</span></span> <span data-ttu-id="82eba-149">BTARN 支持 CIDX Chem eStandards。</span><span class="sxs-lookup"><span data-stu-id="82eba-149">BTARN supports CIDX Chem eStandards.</span></span>  
  
 <span data-ttu-id="82eba-150">**cluster**</span><span class="sxs-lookup"><span data-stu-id="82eba-150">**cluster**</span></span>  
 <span data-ttu-id="82eba-151">高级业务流程，例如订单管理、 库存管理或服务和支持的组。</span><span class="sxs-lookup"><span data-stu-id="82eba-151">A group of high-level business processes, such as order management, inventory management, or service and support.</span></span> <span data-ttu-id="82eba-152">所处理的 RosettaNet 群集表示供应链行业的核心业务流程。</span><span class="sxs-lookup"><span data-stu-id="82eba-152">The clusters addressed by RosettaNet represent core business processes for the supply chain industry.</span></span>  
  
## <a name="d"></a><span data-ttu-id="82eba-153">D</span><span class="sxs-lookup"><span data-stu-id="82eba-153">D</span></span>  
 <span data-ttu-id="82eba-154">**数据统一编码系统 (D-U-N-S) 数量**</span><span class="sxs-lookup"><span data-stu-id="82eba-154">**Data Universal Numbering System (D-U-N-S) number**</span></span>  
 <span data-ttu-id="82eba-155">按顺序生成的九位数字，用于唯一标识业务位置，并为全局作用域中。</span><span class="sxs-lookup"><span data-stu-id="82eba-155">A sequentially generated nine-digit number that uniquely identifies business locations, and is global in scope.</span></span>  
  
 <span data-ttu-id="82eba-156">**传递头**</span><span class="sxs-lookup"><span data-stu-id="82eba-156">**delivery header**</span></span>  
 <span data-ttu-id="82eba-157">RosettaNet 消息的一部分。</span><span class="sxs-lookup"><span data-stu-id="82eba-157">A part of a RosettaNet message.</span></span> <span data-ttu-id="82eba-158">传递头是一个标识邮件发件人、 收件人和消息实例信息的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="82eba-158">The delivery header is an XML document that identifies the message sender, the recipient, and message instance information.</span></span>  
  
 <span data-ttu-id="82eba-159">**目标组织**</span><span class="sxs-lookup"><span data-stu-id="82eba-159">**destination organization**</span></span>  
 <span data-ttu-id="82eba-160">已被指定为消息传送端口中为文档的目标组织。</span><span class="sxs-lookup"><span data-stu-id="82eba-160">An organization that has been designated in a messaging port as the destination for documents.</span></span>  
  
 <span data-ttu-id="82eba-161">**数字算法**</span><span class="sxs-lookup"><span data-stu-id="82eba-161">**digital algorithms**</span></span>  
 <span data-ttu-id="82eba-162">将消息作为输入，并生成哈希或它的一些非常复杂的方式取决于消息内容的位数一固定长度组的摘要算法。</span><span class="sxs-lookup"><span data-stu-id="82eba-162">An algorithm that takes a message as input and produces a hash or digest of it, a fixed-length set of bits that depend on the message contents in some highly complex manner.</span></span> <span data-ttu-id="82eba-163">设计条件包括非常难以伪造摘要或更改一条消息，而无需更改其摘要的任何人。</span><span class="sxs-lookup"><span data-stu-id="82eba-163">Design criteria include making it extremely difficult for anyone to counterfeit a digest or to change a message without changing its digest.</span></span> <span data-ttu-id="82eba-164">通常情况下使用摘要算法的应用程序是在消息身份验证和数字签名方案。</span><span class="sxs-lookup"><span data-stu-id="82eba-164">Applications that typically use digest algorithms are in message authentication and digital signature schemes.</span></span> <span data-ttu-id="82eba-165">广泛使用的算法包括 MD5 和 SHA1。</span><span class="sxs-lookup"><span data-stu-id="82eba-165">Widely used algorithms include MD5 and SHA1.</span></span> <span data-ttu-id="82eba-166">BTARN 支持 MD5 和 SHA1 为传入消息，并仅 SHA1 为传出消息。</span><span class="sxs-lookup"><span data-stu-id="82eba-166">BTARN supports both MD5 and SHA1 for incoming messages, and only SHA1 for outgoing messages.</span></span>  
  
 <span data-ttu-id="82eba-167">**文档定义**</span><span class="sxs-lookup"><span data-stu-id="82eba-167">**document definition**</span></span>  
 <span data-ttu-id="82eba-168">表示特定文档的属性集。</span><span class="sxs-lookup"><span data-stu-id="82eba-168">A set of properties that represents a specific document.</span></span> <span data-ttu-id="82eba-169">文档定义属性包含一个指向文档规范和可以包括全局跟踪字段和选择条件。</span><span class="sxs-lookup"><span data-stu-id="82eba-169">Document definition properties include a pointer to a document specification and can include global tracking fields and selection criteria.</span></span>  
  
 <span data-ttu-id="82eba-170">**文档实例**</span><span class="sxs-lookup"><span data-stu-id="82eba-170">**document instance**</span></span>  
 <span data-ttu-id="82eba-171">发送到的实际数据的表示形式[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="82eba-171">A representation of the actual data that is sent to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="82eba-172">文档实例与从文档规范的规范定义的数据结构，而文档实例是一种结构中包含的特定数据的表示形式。</span><span class="sxs-lookup"><span data-stu-id="82eba-172">A document instance differs from a document specification in that the specification defines the structure of the data, while a document instance is a representation of the specific data that is contained in a structure.</span></span>  
  
 <span data-ttu-id="82eba-173">**文档类型定义 (DTD)**</span><span class="sxs-lookup"><span data-stu-id="82eba-173">**document type definition (DTD)**</span></span>  
 <span data-ttu-id="82eba-174">指定的元素和属性的标准定义可能会出现在其他元素和属性并指定其排序、 频率和内容的任何约束。</span><span class="sxs-lookup"><span data-stu-id="82eba-174">A standard definition that specifies which elements and attributes might be present in other elements and attributes and that specifies any constraints on their ordering, frequency, and content.</span></span>  
  
 <span data-ttu-id="82eba-175">**双操作事务** </span><span class="sxs-lookup"><span data-stu-id="82eba-175">**double action transaction** </span></span>  
 <span data-ttu-id="82eba-176">其中发起方发送的请求操作，一个进程收到信号，同时从响应方跟响应操作。</span><span class="sxs-lookup"><span data-stu-id="82eba-176">A process where an initiator sends a request action, receives a signal, followed by a response action from the responder.</span></span> <span data-ttu-id="82eba-177">发起方通过将信号发送到响应操作完成过程。</span><span class="sxs-lookup"><span data-stu-id="82eba-177">The initiator finishes the process by sending a signal to the response action.</span></span>  
  
## <a name="e"></a><span data-ttu-id="82eba-178">E</span><span class="sxs-lookup"><span data-stu-id="82eba-178">E</span></span>  
 <span data-ttu-id="82eba-179">**可扩展标记语言 (XML)**</span><span class="sxs-lookup"><span data-stu-id="82eba-179">**Extensible Markup Language (XML)**</span></span>  
 <span data-ttu-id="82eba-180">由 World Wide Web 联合会 (W3C) 开发的规范，使设计人员可以创建超出标准 HTML 功能的自定义的标记。</span><span class="sxs-lookup"><span data-stu-id="82eba-180">A specification developed by the World Wide Web Consortium (W3C) that enables designers to create customized tags beyond the capabilities of standard HTML.</span></span> <span data-ttu-id="82eba-181">HTML 使用预定义的标签来描述页面中的元素，而利用 XML 标记来定义由页面开发人员。</span><span class="sxs-lookup"><span data-stu-id="82eba-181">While HTML uses only predefined tags to describe elements in the page, XML enables tags to be defined by the developer of the page.</span></span> <span data-ttu-id="82eba-182">几乎任何数据项，例如产品或金额，由于标记可以用于特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="82eba-182">Tags for virtually any data item, such as a product or an amount due, can be used for specific applications.</span></span> <span data-ttu-id="82eba-183">这使网页能够作为数据库记录。</span><span class="sxs-lookup"><span data-stu-id="82eba-183">This enables Web pages to function as database records.</span></span>  
  
 <span data-ttu-id="82eba-184">**可扩展样式表语言 (XSL)**</span><span class="sxs-lookup"><span data-stu-id="82eba-184">**Extensible Stylesheet Language (XSL)**</span></span>  
 <span data-ttu-id="82eba-185">样式表的格式为 XML 文档的。</span><span class="sxs-lookup"><span data-stu-id="82eba-185">A style sheet format for XML documents.</span></span> <span data-ttu-id="82eba-186">XSL 用于定义 XML 的显示，就像级联样式表 (CSS) 用于定义显示的 HTML。</span><span class="sxs-lookup"><span data-stu-id="82eba-186">XSL is used to define the display of XML just like cascading style sheets (CSS) are used to define the display of HTML.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="82eba-187">使用 XSL 作为两个规范之间的转换语言。</span><span class="sxs-lookup"><span data-stu-id="82eba-187">uses XSL as the translation language between two specifications.</span></span>  
  
## <a name="g"></a><span data-ttu-id="82eba-188">G</span><span class="sxs-lookup"><span data-stu-id="82eba-188">G</span></span>  
 <span data-ttu-id="82eba-189">**全球业务标识 (GBI)**</span><span class="sxs-lookup"><span data-stu-id="82eba-189">**Global Business Identification (GBI)**</span></span>  
 <span data-ttu-id="82eba-190">若要标识贸易参与方的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="82eba-190">A unique identifier to identify trading parties.</span></span> <span data-ttu-id="82eba-191">RosettaNet 使用 9 位数字 Dun 和 Bradstreet 编码系统 (DUNS) 作为 GBI。</span><span class="sxs-lookup"><span data-stu-id="82eba-191">RosettaNet uses the nine-digit Dun and Bradstreet Numbering System (DUNS) as the GBI.</span></span>  
  
## <a name="h"></a><span data-ttu-id="82eba-192">H</span><span class="sxs-lookup"><span data-stu-id="82eba-192">H</span></span>  
 <span data-ttu-id="82eba-193">**本组织** </span><span class="sxs-lookup"><span data-stu-id="82eba-193">**home organization** </span></span>  
 <span data-ttu-id="82eba-194">若要确定你的组织别名。</span><span class="sxs-lookup"><span data-stu-id="82eba-194">An alias to identify your organization.</span></span>  
  
## <a name="i"></a><span data-ttu-id="82eba-195">I</span><span class="sxs-lookup"><span data-stu-id="82eba-195">I</span></span>  
 <span data-ttu-id="82eba-196">**initiator**</span><span class="sxs-lookup"><span data-stu-id="82eba-196">**initiator**</span></span>  
 <span data-ttu-id="82eba-197">启动一个过程，向贸易合作伙伴的通知或事务过程中组织的角色。</span><span class="sxs-lookup"><span data-stu-id="82eba-197">The role of an organization in a transaction or notification process that initiates a process to a trading partner.</span></span>  
  
## <a name="l"></a><span data-ttu-id="82eba-198">L</span><span class="sxs-lookup"><span data-stu-id="82eba-198">L</span></span>  
 <span data-ttu-id="82eba-199">**业务线 (LOB) 应用程序的行**</span><span class="sxs-lookup"><span data-stu-id="82eba-199">**Line of Business (LOB) Application**</span></span>  
 <span data-ttu-id="82eba-200">应用程序与 BTARN 作为后端系统进行通信。</span><span class="sxs-lookup"><span data-stu-id="82eba-200">The application that communicates with BTARN as the backend system.</span></span>  
  
 <span data-ttu-id="82eba-201">**Loopback 实用工具**</span><span class="sxs-lookup"><span data-stu-id="82eba-201">**Loopback utility**</span></span>  
 <span data-ttu-id="82eba-202">用于开发人员能够自动生成环回协议，它是本组织到合作伙伴协议的镜像副本的实用程序。</span><span class="sxs-lookup"><span data-stu-id="82eba-202">A utility for developers to automatically generate a loopback agreement that is a mirror copy of a home-to-partner agreement.</span></span> <span data-ttu-id="82eba-203">这允许您在单台计算机上执行本组织合作伙伴和合作伙伴主页消息交换。</span><span class="sxs-lookup"><span data-stu-id="82eba-203">This lets you perform home-to-partner and partner-to-home message exchanges on a single computer.</span></span>  
  
## <a name="m"></a><span data-ttu-id="82eba-204">M</span><span class="sxs-lookup"><span data-stu-id="82eba-204">M</span></span>  
 <span data-ttu-id="82eba-205">**map**</span><span class="sxs-lookup"><span data-stu-id="82eba-205">**map**</span></span>  
 <span data-ttu-id="82eba-206">XML 文件的另一个规范中定义的记录和一个规范中的字段和记录和字段之间的对应关系。</span><span class="sxs-lookup"><span data-stu-id="82eba-206">An XML file that defines the correspondence between the records and fields in one specification and the records and fields in another specification.</span></span> <span data-ttu-id="82eba-207">映射中包含一个 XSL 样式表[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于执行在映射中所描述的转换。</span><span class="sxs-lookup"><span data-stu-id="82eba-207">A map contains an XSL style sheet that [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] uses to perform the transformation described in the map.</span></span> <span data-ttu-id="82eba-208">在 BizTalk 映射器创建映射。</span><span class="sxs-lookup"><span data-stu-id="82eba-208">Maps are created in BizTalk Mapper.</span></span>
  
 <span data-ttu-id="82eba-209">**我的组织**</span><span class="sxs-lookup"><span data-stu-id="82eba-209">**my organization**</span></span>  
 <span data-ttu-id="82eba-210">贸易合作伙伴协议中表示你的组织。</span><span class="sxs-lookup"><span data-stu-id="82eba-210">Represents your organization in a trading partner agreement.</span></span>   
  
 <span data-ttu-id="82eba-211">**多用途 Internet 邮件扩展 (MIME)**</span><span class="sxs-lookup"><span data-stu-id="82eba-211">**Multi-Purpose Internet Mail Extensions (MIME)**</span></span>  
 <span data-ttu-id="82eba-212">可让你的 Internet 电子邮件协议的扩展使用的协议来交换不同类型的数据文件在 Internet 上： 音频、 视频、 图像和应用程序的程序。</span><span class="sxs-lookup"><span data-stu-id="82eba-212">An extension of the Internet e-mail protocol that lets you use the protocol to exchange different kinds of data files on the Internet: audio, video, images, and application programs.</span></span>  
  
## <a name="n"></a><span data-ttu-id="82eba-213">N</span><span class="sxs-lookup"><span data-stu-id="82eba-213">N</span></span>  
 <span data-ttu-id="82eba-214">**non-repudiation**</span><span class="sxs-lookup"><span data-stu-id="82eba-214">**non-repudiation**</span></span>  
 <span data-ttu-id="82eba-215">若要确保消息的发件人不能更高版本无法识别发件人发送消息和接收方收到消息，不能拒绝一种方法。</span><span class="sxs-lookup"><span data-stu-id="82eba-215">A way to make sure that the sender of a message cannot later refuse to recognize that the sender sent the message and that the recipient cannot deny having received the message.</span></span> <span data-ttu-id="82eba-216">传入消息的不可否认性要求消息由接收方，保存，并且该消息应执行数字签名使用发件人的签名证书以确保它的真实性。</span><span class="sxs-lookup"><span data-stu-id="82eba-216">Non-repudiation of an incoming message requires that the message be saved by the receiver, and that the message should carry a digital signature using the signing certificate of the sender to ensure its authenticity.</span></span> <span data-ttu-id="82eba-217">传出的消息的不可否认，则需要保存确认消息 （从第一条消息的接收方的传入消息），并且该消息应包含原始摘要的数字签名消息使用签名收件人的证书。</span><span class="sxs-lookup"><span data-stu-id="82eba-217">Non-repudiation of an outgoing message requires saving the acknowledgement message (incoming message from the recipient of the first message), and that the message should carry the digital signature of the digest of the original message using the signing certificate of the recipient.</span></span>   
  
 <span data-ttu-id="82eba-218">**notification**</span><span class="sxs-lookup"><span data-stu-id="82eba-218">**notification**</span></span>  
 <span data-ttu-id="82eba-219">发起方通知响应方使用一条消息的其中一个 RNIF 1.1 进程类型。</span><span class="sxs-lookup"><span data-stu-id="82eba-219">An RNIF 1.1 process type where the initiator notifies the responder with a single message.</span></span> <span data-ttu-id="82eba-220">响应方应使用业务信号，表示确认答复。</span><span class="sxs-lookup"><span data-stu-id="82eba-220">The responder is expected to reply with a business signal as an acknowledgement.</span></span>  
  
 <span data-ttu-id="82eba-221">**失败 (的 PIP 0A1) 的通知**</span><span class="sxs-lookup"><span data-stu-id="82eba-221">**Notification of Failure (PIP 0A1)**</span></span>  
 <span data-ttu-id="82eba-222">特殊的 PIP，该值指示进程意外的失败。</span><span class="sxs-lookup"><span data-stu-id="82eba-222">A special PIP that indicates unexpected process failures.</span></span> <span data-ttu-id="82eba-223">发起方或响应方可以启动失败通知。</span><span class="sxs-lookup"><span data-stu-id="82eba-223">The initiator or the responder can initiate a Notification of Failure.</span></span> <span data-ttu-id="82eba-224">它引用一个现有的或以前交换的过程。</span><span class="sxs-lookup"><span data-stu-id="82eba-224">It refers to an existing or previously exchanged process.</span></span> <span data-ttu-id="82eba-225">收到的 0A1，接收方可以确保，所引用的进程被视为不有效。</span><span class="sxs-lookup"><span data-stu-id="82eba-225">Upon receipt of a 0A1, the receiving party makes sure that the referenced process is considered not valid.</span></span>  
  
## <a name="o"></a><span data-ttu-id="82eba-226">O</span><span class="sxs-lookup"><span data-stu-id="82eba-226">O</span></span>  
 <span data-ttu-id="82eba-227">**organization**</span><span class="sxs-lookup"><span data-stu-id="82eba-227">**organization**</span></span>  
 <span data-ttu-id="82eba-228">贸易合作伙伴或可执行业务交易某个业务部门。</span><span class="sxs-lookup"><span data-stu-id="82eba-228">A trading partner or a business unit that can conduct business transactions.</span></span>  
  
## <a name="p"></a><span data-ttu-id="82eba-229">P</span><span class="sxs-lookup"><span data-stu-id="82eba-229">P</span></span>  
 <span data-ttu-id="82eba-230">**packaging**</span><span class="sxs-lookup"><span data-stu-id="82eba-230">**packaging**</span></span>  
 <span data-ttu-id="82eba-231">转换其 XML 表示形式中，反之亦然 RosettaNet 消息的过程。</span><span class="sxs-lookup"><span data-stu-id="82eba-231">The process of converting a RosettaNet message in its XML representation and vice versa.</span></span>  
  
 <span data-ttu-id="82eba-232">**合作伙伴接口流程 (PIP)**</span><span class="sxs-lookup"><span data-stu-id="82eba-232">**Partner Interface Process (PIP)**</span></span>  
 <span data-ttu-id="82eba-233">PIP 描述一组业务文档和协议详细信息，包括文档内容的详细信息。</span><span class="sxs-lookup"><span data-stu-id="82eba-233">A PIP describes a set of business documents and agreement details, including document content details.</span></span>  
  
 <span data-ttu-id="82eba-234">**PIP 规范文档**</span><span class="sxs-lookup"><span data-stu-id="82eba-234">**PIP Specification document**</span></span>  
 <span data-ttu-id="82eba-235">包含有关要在 BTARN 管理控制台创建流程配置时使用的设置指南的文档。</span><span class="sxs-lookup"><span data-stu-id="82eba-235">A document that contains guidance about the settings to use when you create a process configuration in the BTARN Management Console.</span></span> <span data-ttu-id="82eba-236">从 RosettaNet 组织，从 RosettaNet.org 下载 PIP 规范文档和 PIP。包含有关要在 BTARN 管理控制台创建流程配置时使用的设置指南的文档。</span><span class="sxs-lookup"><span data-stu-id="82eba-236">You download the PIP Specification document and the PIP from the RosettaNet organization, from RosettaNet.org. A document that contains guidance about the settings to use when you create a process configuration in the BTARN Management Console.</span></span> <span data-ttu-id="82eba-237">从 RosettaNet 组织，从 RosettaNet.org 下载 PIP 规范文档和 PIP。</span><span class="sxs-lookup"><span data-stu-id="82eba-237">You download the PIP Specification document and the PIP from the RosettaNet organization, from RosettaNet.org.</span></span>  
  
 <span data-ttu-id="82eba-238">**前导头**</span><span class="sxs-lookup"><span data-stu-id="82eba-238">**preamble header**</span></span>  
 <span data-ttu-id="82eba-239">标识的名称和版本的业务消息与符合标准的 XML 节点。</span><span class="sxs-lookup"><span data-stu-id="82eba-239">An XML node that identifies the name and version of the standard with which a business message is compliant.</span></span> <span data-ttu-id="82eba-240">它与其他标头，以形成完整的 RosettaNet 消息一起打包。</span><span class="sxs-lookup"><span data-stu-id="82eba-240">It is packaged together with other headers to form a complete RosettaNet Message.</span></span> <span data-ttu-id="82eba-241">也名为前导码。</span><span class="sxs-lookup"><span data-stu-id="82eba-241">Also named preamble.</span></span>  
  
 <span data-ttu-id="82eba-242">**专用流程** </span><span class="sxs-lookup"><span data-stu-id="82eba-242">**private process** </span></span>  
 <span data-ttu-id="82eba-243">将组织内部的业务流程。</span><span class="sxs-lookup"><span data-stu-id="82eba-243">Business processes that are internal to an organization.</span></span> <span data-ttu-id="82eba-244">BTARN 专用流程作为长期 BizTalk 业务流程来实现。</span><span class="sxs-lookup"><span data-stu-id="82eba-244">BTARN implements private processes as long-running BizTalk orchestrations.</span></span>  
  
 <span data-ttu-id="82eba-245">**进程配置设置 (PC) 配置文件**</span><span class="sxs-lookup"><span data-stu-id="82eba-245">**Process Configuration Setting (PCS) profile**</span></span>  
 <span data-ttu-id="82eba-246">确定合作伙伴协议的运行方式。</span><span class="sxs-lookup"><span data-stu-id="82eba-246">Determines how a partner agreement runs.</span></span> <span data-ttu-id="82eba-247">PC 配置文件用于输入的配置详细信息的 RosettaNet 合作伙伴接口流程 (PIP)。</span><span class="sxs-lookup"><span data-stu-id="82eba-247">You use the PCS profile to enter the configuration details of a RosettaNet Partner Interface Process (PIP).</span></span> <span data-ttu-id="82eba-248">RosettaNet PIP 规范映射到 PC 配置文件中的一个元素中指定的所有配置值。</span><span class="sxs-lookup"><span data-stu-id="82eba-248">All configuration values specified in a RosettaNet PIP specification map to one element in the PCS profile.</span></span> <span data-ttu-id="82eba-249">一个 PC 配置文件可用于多个合作伙伴协议。</span><span class="sxs-lookup"><span data-stu-id="82eba-249">You can use one PCS profile for multiple partner agreements.</span></span>  
  
 <span data-ttu-id="82eba-250">**port**</span><span class="sxs-lookup"><span data-stu-id="82eba-250">**port**</span></span>  
 <span data-ttu-id="82eba-251">使用的特定实现的命名的位置。</span><span class="sxs-lookup"><span data-stu-id="82eba-251">A named location that uses a specific implementation.</span></span> <span data-ttu-id="82eba-252">在 BizTalk 业务流程设计器中的位置向其发送消息或从其接收消息，以及用于实现通信操作的技术通过定义端口。</span><span class="sxs-lookup"><span data-stu-id="82eba-252">In BizTalk Orchestration Designer, a port is defined by the location to which messages are sent or from which messages are received, and the technology that is used to implement the communication action.</span></span> <span data-ttu-id="82eba-253">由该端口的名称唯一标识该位置。</span><span class="sxs-lookup"><span data-stu-id="82eba-253">The location is uniquely identified by the name of the port.</span></span>  
  
 <span data-ttu-id="82eba-254">**公用流程** </span><span class="sxs-lookup"><span data-stu-id="82eba-254">**public process** </span></span>  
 <span data-ttu-id="82eba-255">涉及与贸易合作伙伴作为公用过程集成的业务流程。</span><span class="sxs-lookup"><span data-stu-id="82eba-255">Business processes that involve integration with trading partners as public processes.</span></span> <span data-ttu-id="82eba-256">BTARN 公用流程作为长期 BizTalk 业务流程来实现。</span><span class="sxs-lookup"><span data-stu-id="82eba-256">BTARN implements public processes as long-running BizTalk orchestrations.</span></span> <span data-ttu-id="82eba-257">一个公用业务流程在发起方和响应方各上运行。</span><span class="sxs-lookup"><span data-stu-id="82eba-257">One public-process orchestration runs on the initiator side and one on the responder side.</span></span> <span data-ttu-id="82eba-258">BTARN 安装程序提供了在发起方和响应方公用流程，用于 RNIF 1.1 和 RNIF 2.01 的版本。</span><span class="sxs-lookup"><span data-stu-id="82eba-258">The BTARN Setup program provides versions of the initiator and responder public-process orchestrations for both RNIF 1.1 and RNIF 2.01.</span></span> <span data-ttu-id="82eba-259">这些公用业务流程实现所有的 RNIF 流程。</span><span class="sxs-lookup"><span data-stu-id="82eba-259">These public-process orchestrations implement all RNIF processes.</span></span> <span data-ttu-id="82eba-260">公用流程使 RNIF 从其他组件的复杂性。</span><span class="sxs-lookup"><span data-stu-id="82eba-260">Public processes hide the complexity of RNIF from the rest of the components.</span></span> <span data-ttu-id="82eba-261">除了强制实施符合 RNIF 消息流，则公用流程还确定默认跟踪设置，并提供在运行时进程状态信息。</span><span class="sxs-lookup"><span data-stu-id="82eba-261">Besides enforcing the RNIF-compliant message flow, the public process also determines default-tracking settings and provides process state information at runtime.</span></span>  
  
## <a name="r"></a><span data-ttu-id="82eba-262">R</span><span class="sxs-lookup"><span data-stu-id="82eba-262">R</span></span>  
 <span data-ttu-id="82eba-263">**responder**</span><span class="sxs-lookup"><span data-stu-id="82eba-263">**responder**</span></span>  
 <span data-ttu-id="82eba-264">对贸易合作伙伴请求做出响应的通知或事务过程中组织的角色。</span><span class="sxs-lookup"><span data-stu-id="82eba-264">The role of an organization in a transaction or notification process that responds to a request by a trading partner.</span></span>  
  
 <span data-ttu-id="82eba-265">**RosettaNet Implementation Framework (RNIF)**</span><span class="sxs-lookup"><span data-stu-id="82eba-265">**RosettaNet Implementation Framework (RNIF)**</span></span>  
 <span data-ttu-id="82eba-266">一种标准框架，为想要创建可互操作的软件应用程序组件运行 Pip 的这些公司提供实现指导原则。</span><span class="sxs-lookup"><span data-stu-id="82eba-266">A standards framework that provides implementation guidelines for those companies that want to create interoperable software application components that run PIPs.</span></span>  
  
 <span data-ttu-id="82eba-267">**RosettaNet 消息**</span><span class="sxs-lookup"><span data-stu-id="82eba-267">**RosettaNet message**</span></span>  
 <span data-ttu-id="82eba-268">前导头、 传递头 （对于 RNIF 2.0)、 服务头和服务内容的逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="82eba-268">The logical grouping of the preamble header, delivery header (in the case of RNIF 2.0), service header, and service content.</span></span>  
  
 <span data-ttu-id="82eba-269">**RosettaNet 对象**</span><span class="sxs-lookup"><span data-stu-id="82eba-269">**RosettaNet object**</span></span>  
 <span data-ttu-id="82eba-270">RosettaNet 消息封装为 RosettaNet 实现框架版本 1.1 中的传递。</span><span class="sxs-lookup"><span data-stu-id="82eba-270">A RosettaNet message enveloped for delivery in RosettaNet Implementation Framework version 1.1.</span></span>  
  
## <a name="s"></a><span data-ttu-id="82eba-271">S</span><span class="sxs-lookup"><span data-stu-id="82eba-271">S</span></span>  
 <span data-ttu-id="82eba-272">**schema**</span><span class="sxs-lookup"><span data-stu-id="82eba-272">**schema**</span></span>  
 <span data-ttu-id="82eba-273">XML 文件的结构的定义。</span><span class="sxs-lookup"><span data-stu-id="82eba-273">The definition of the structure of an XML file.</span></span> <span data-ttu-id="82eba-274">架构包含属性的信息，因为它涉及到的记录和字段结构中。</span><span class="sxs-lookup"><span data-stu-id="82eba-274">A schema contains property information as it pertains to the records and fields in the structure.</span></span>  
  
 <span data-ttu-id="82eba-275">**服务内容**</span><span class="sxs-lookup"><span data-stu-id="82eba-275">**service content**</span></span>  
 <span data-ttu-id="82eba-276">RosettaNet 消息的主要组件。</span><span class="sxs-lookup"><span data-stu-id="82eba-276">The primary component of the RosettaNet message.</span></span> <span data-ttu-id="82eba-277">它是一个 XML 节点，表示指定的特定 PIP 的业务内容。</span><span class="sxs-lookup"><span data-stu-id="82eba-277">It is an XML node that represents the business content specified by a particular PIP.</span></span>  
  
 <span data-ttu-id="82eba-278">**service header**</span><span class="sxs-lookup"><span data-stu-id="82eba-278">**service header**</span></span>  
 <span data-ttu-id="82eba-279">标识与业务消息，其中包括 PIP、 业务活动和操作，发送和接收服务、 贸易合作伙伴和角色关联的部分 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="82eba-279">An XML document that identifies the parts associated with a business message, including the PIP, business activity and action, sending and receiving services, trading partners, and roles.</span></span>  
  
 <span data-ttu-id="82eba-280">**信号 URL**</span><span class="sxs-lookup"><span data-stu-id="82eba-280">**signal URL**</span></span>  
 <span data-ttu-id="82eba-281">本组织将信号消息传输到的 URL。</span><span class="sxs-lookup"><span data-stu-id="82eba-281">The URL to which the home organization transmits a signal message.</span></span> <span data-ttu-id="82eba-282">例如， http://FabrikamServer/BTARNApp/RNIFReceive.aspx。</span><span class="sxs-lookup"><span data-stu-id="82eba-282">For example, http://FabrikamServer/BTARNApp/RNIFReceive.aspx.</span></span>  
  
 <span data-ttu-id="82eba-283">**单个操作通知**</span><span class="sxs-lookup"><span data-stu-id="82eba-283">**single action notification**</span></span>  
 <span data-ttu-id="82eba-284">使用一条消息回复发起方将单一操作消息和响应方发送的进程。</span><span class="sxs-lookup"><span data-stu-id="82eba-284">A process where the initiator sends a single action message and the responder replies with a message.</span></span>  
  
 <span data-ttu-id="82eba-285">**specification**</span><span class="sxs-lookup"><span data-stu-id="82eba-285">**specification**</span></span>  
 <span data-ttu-id="82eba-286">一个[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]-特定 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="82eba-286">A [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]-specific XML schema.</span></span> <span data-ttu-id="82eba-287">创建在 BizTalk 编辑器中的规范，并可以基于行业标准，例如 EDIFACT，x12 和 XML，或在平面文件，例如带分隔符、 位置，或分隔和位置。</span><span class="sxs-lookup"><span data-stu-id="82eba-287">You create specifications in BizTalk Editor and can be based on industry standards, such as EDIFACT, X12, and XML, or on flat files, such as delimited, positional, or delimited and positional.</span></span> <span data-ttu-id="82eba-288">BizTalk 映射器使用规范作为源规范和目标规范，打开创建映射。</span><span class="sxs-lookup"><span data-stu-id="82eba-288">BizTalk Mapper uses specifications, opened as source specifications and destination specifications, to create maps.</span></span>  
  
 <span data-ttu-id="82eba-289">**sync URL**</span><span class="sxs-lookup"><span data-stu-id="82eba-289">**sync URL**</span></span>  
 <span data-ttu-id="82eba-290">本组织用于建立与合作伙伴，例如，同步事务的 URL http://FabikamServer/BTARNApp/RNIFReceive.aspx。</span><span class="sxs-lookup"><span data-stu-id="82eba-290">The URL that the home organization uses to establish synchronous transactions with the partner, for example, http://FabikamServer/BTARNApp/RNIFReceive.aspx.</span></span>  
  
 <span data-ttu-id="82eba-291">**同步事务**</span><span class="sxs-lookup"><span data-stu-id="82eba-291">**synchronous transaction**</span></span>  
 <span data-ttu-id="82eba-292">一个过程，其中发起方返回响应 （双操作） 或信号 （单操作） 的相同的 HTTP 状态而不关闭连接。</span><span class="sxs-lookup"><span data-stu-id="82eba-292">A process where the initiator returns a response (double-action) or signal (single-action) on the same HTTP state without closing the connection.</span></span>  
  
## <a name="t"></a><span data-ttu-id="82eba-293">T</span><span class="sxs-lookup"><span data-stu-id="82eba-293">T</span></span>  
 <span data-ttu-id="82eba-294">**贸易合作伙伴**</span><span class="sxs-lookup"><span data-stu-id="82eba-294">**trading partner**</span></span>  
 <span data-ttu-id="82eba-295">外部组织与你的组织交换电子数据。</span><span class="sxs-lookup"><span data-stu-id="82eba-295">An external organization with which your organization exchanges electronic data.</span></span>  
  
 <span data-ttu-id="82eba-296">**贸易合作伙伴协议**</span><span class="sxs-lookup"><span data-stu-id="82eba-296">**trading partner agreement**</span></span>  
 <span data-ttu-id="82eba-297">你的组织和贸易合作伙伴之间的协议。</span><span class="sxs-lookup"><span data-stu-id="82eba-297">An agreement between your organization and your trading partner.</span></span> <span data-ttu-id="82eba-298">贸易合作伙伴协议引用流程配置设置配置文件、 本组织、 合作伙伴，并包含协议特定的配置设置。</span><span class="sxs-lookup"><span data-stu-id="82eba-298">A trading partner agreement references a Process Configuration Setting profile, home organization, partner, and contains agreement specific configuration settings.</span></span>  
  
 <span data-ttu-id="82eba-299">**transaction**</span><span class="sxs-lookup"><span data-stu-id="82eba-299">**transaction**</span></span>  
 <span data-ttu-id="82eba-300">其中发起方发送 RosettaNet 消息，RNIF 1.1 流程收到信号，接收 RosettaNet 消息作为答案，并发送确认的信号。</span><span class="sxs-lookup"><span data-stu-id="82eba-300">An RNIF 1.1 process where the initiator sends a RosettaNet message, receives a signal, receives a RosettaNet message as an answer, and sends a signal for acknowledgement.</span></span>  
  
## <a name="v"></a><span data-ttu-id="82eba-301">V</span><span class="sxs-lookup"><span data-stu-id="82eba-301">V</span></span>  
 <span data-ttu-id="82eba-302">**验证适配器**</span><span class="sxs-lookup"><span data-stu-id="82eba-302">**validation adapter**</span></span>  
 <span data-ttu-id="82eba-303">实现验证适配器接口的应用程序。</span><span class="sxs-lookup"><span data-stu-id="82eba-303">An application that implements the Validation Adapter interface.</span></span> <span data-ttu-id="82eba-304">公用响应方接收操作消息 （请求或响应） 时调用验证适配器。</span><span class="sxs-lookup"><span data-stu-id="82eba-304">The public responder invokes the Validation Adapter when it receives an action message (request or response).</span></span> <span data-ttu-id="82eba-305">它可以包含任何组的企业可能需要再接受传入消息的验证规则。</span><span class="sxs-lookup"><span data-stu-id="82eba-305">It can include any set of validation rules that a business may require before accepting an incoming message.</span></span> <span data-ttu-id="82eba-306">在接收管道中，以及公用业务流程中，BTARN 本机执行验证。</span><span class="sxs-lookup"><span data-stu-id="82eba-306">BTARN natively performs validation in the receive pipeline, and in public orchestrations.</span></span>  
  
## <a name="x"></a><span data-ttu-id="82eba-307">X</span><span class="sxs-lookup"><span data-stu-id="82eba-307">X</span></span>  
 <span data-ttu-id="82eba-308">**XLANG 计划**</span><span class="sxs-lookup"><span data-stu-id="82eba-308">**XLANG schedule**</span></span>  
 <span data-ttu-id="82eba-309">特定的 XML 语言来描述业务流程和后端集成。</span><span class="sxs-lookup"><span data-stu-id="82eba-309">A specific XML language that describes business processes and back-end integration.</span></span> <span data-ttu-id="82eba-310">BTARN 中的特定业务流程表示在 XLANG 语言。</span><span class="sxs-lookup"><span data-stu-id="82eba-310">Specific business processes in BTARN are expressed in the XLANG language.</span></span> <span data-ttu-id="82eba-311">XLANG 计划与文件名称扩展.skx 一起保存。</span><span class="sxs-lookup"><span data-stu-id="82eba-311">An XLANG schedule is saved with the file name extension .skx.</span></span>  
  
