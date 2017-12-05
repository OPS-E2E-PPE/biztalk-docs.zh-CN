---
title: "HL7 系统集成 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f66a4fc-186c-415f-a7ed-31f620f0495f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c7189802ea981bd26b717f09bb3de0e445c9314
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="systems-integration-with-biztalk-server"></a><span data-ttu-id="0be0e-102">与 BizTalk Server 的系统集成</span><span class="sxs-lookup"><span data-stu-id="0be0e-102">Systems Integration with BizTalk Server</span></span>
<span data-ttu-id="0be0e-103">Microsoft BizTalk Server 是为电子商务应用程序设计的集成服务器。</span><span class="sxs-lookup"><span data-stu-id="0be0e-103">Microsoft BizTalk Server is an integration server designed for eBusiness applications.</span></span> <span data-ttu-id="0be0e-104">它基于 Windows Server、 SQL Server 和 SharePoint，并可利用 Visual Studio 的功能。</span><span class="sxs-lookup"><span data-stu-id="0be0e-104">It is built on the  Windows Server, SQL Server, and SharePoint, and leverages the functionality of  Visual Studio.</span></span> <span data-ttu-id="0be0e-105">这种多层次的技术为开发、实现、操作和维护你的解决方案提供了丰富的功能。</span><span class="sxs-lookup"><span data-stu-id="0be0e-105">This technology stack provides a range of functionality and features for developing, implementing, operating, and maintaining your solution.</span></span>  
  
 <span data-ttu-id="0be0e-106">BizTalk Server 提供以下可用于结合使用 BizTalk Accelerator HL7 的集成服务 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="0be0e-106">BizTalk Server provides the following integration services that you can use in conjunction with BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]).</span></span>  
  
## <a name="message-integration"></a><span data-ttu-id="0be0e-107">消息集成</span><span class="sxs-lookup"><span data-stu-id="0be0e-107">Message Integration</span></span>  
 <span data-ttu-id="0be0e-108">BizTalk Server 集成通过自动执行消息交换的不同实体 （部门、 业务合作伙伴、 供应商，等）。</span><span class="sxs-lookup"><span data-stu-id="0be0e-108">BizTalk Server integrates different entities (departments, business partners, vendors, and so on) by automating message exchange.</span></span> <span data-ttu-id="0be0e-109">它使用可扩展标记语言 (XML) 作为一种常见通信协议。</span><span class="sxs-lookup"><span data-stu-id="0be0e-109">It uses Extensible Markup Language (XML) as a common communication protocol.</span></span> <span data-ttu-id="0be0e-110">它使用 XML 架构定义 (XSD) 架构来描述和验证消息，同时使用 XSL 转换 (XSLT) 在一条消息与另一条消息间转换数据。</span><span class="sxs-lookup"><span data-stu-id="0be0e-110">It uses XML Schema Definition (XSD) schemas to describe and validate messages, and XSL Transformations (XSLT) to transform data from one message to another.</span></span>  
  
 <span data-ttu-id="0be0e-111">BizTalk Server 集成引擎将从一个位置的消息路由到另一个。</span><span class="sxs-lookup"><span data-stu-id="0be0e-111">The BizTalk Server integration engine routes messages from one location to another.</span></span> <span data-ttu-id="0be0e-112">采用发布方/订阅方模型（某一部门发布文档，另一部门订阅此文档）是它的一大特色。</span><span class="sxs-lookup"><span data-stu-id="0be0e-112">It features a publisher/subscriber model that enables one department to publish a document, and another to subscribe to it.</span></span> <span data-ttu-id="0be0e-113">订阅部门可以在发布部门不知情的情况下订阅消息。</span><span class="sxs-lookup"><span data-stu-id="0be0e-113">The subscribing department can subscribe to the message without the publishing department knowing about it.</span></span> <span data-ttu-id="0be0e-114">这就启用了高效的合作伙伴组织处理功能，使用灵活的中心-分支方式替代了点对点的通信。</span><span class="sxs-lookup"><span data-stu-id="0be0e-114">This enables efficient handling of partner organizations, replacing point-to-point communications with a flexible hub-spoke arrangement.</span></span>  
  
## <a name="business-process-automation"></a><span data-ttu-id="0be0e-115">业务流程自动化</span><span class="sxs-lookup"><span data-stu-id="0be0e-115">Business Process Automation</span></span>  
 <span data-ttu-id="0be0e-116">BizTalk Server 自动执行，并通过使用调用业务流程的流程图链接在单个进程的不同，相关操作的一组集成业务流程。</span><span class="sxs-lookup"><span data-stu-id="0be0e-116">BizTalk Server automates and integrates business processes by using a process map called an orchestration to link a set of distinct, related actions in a single process.</span></span> <span data-ttu-id="0be0e-117">通过创建业务流程，你可以将基于数据交换和分析的步骤（如消息接收、消息发送、决策、循环和其他操作）连接起来。</span><span class="sxs-lookup"><span data-stu-id="0be0e-117">By creating an orchestration, you can link steps based on data exchange and analysis, such as message receiving, message sending, decisions, loops, and other operations.</span></span> <span data-ttu-id="0be0e-118">业务流程可用于创建将在事件发生时自动运行的业务流程。</span><span class="sxs-lookup"><span data-stu-id="0be0e-118">An orchestration enables you to create a business process that will run automatically when an event occurs.</span></span>  
  
 <span data-ttu-id="0be0e-119">使用 BizTalk Server，您可以动态更改业务规则所基于的进程。</span><span class="sxs-lookup"><span data-stu-id="0be0e-119">Using BizTalk Server, you can dynamically change a process based on business rules.</span></span> <span data-ttu-id="0be0e-120">这就可以让你根据业务需要灵活地更改业务流程中采取的操作。</span><span class="sxs-lookup"><span data-stu-id="0be0e-120">This gives you the flexibility to change the actions taken in an orchestrated process according to business considerations.</span></span> <span data-ttu-id="0be0e-121">限制只对超过特定阈值以上的订单进行订单开票审批流程就是一个例子。</span><span class="sxs-lookup"><span data-stu-id="0be0e-121">An example is restricting the approval process for billing orders to those orders over a certain threshold.</span></span>  
  
 <span data-ttu-id="0be0e-122">BizTalk Server 还可包括自动业务流程，通过工作流服务内的人工操作。</span><span class="sxs-lookup"><span data-stu-id="0be0e-122">BizTalk Server also enables you to include human actions within automated orchestrations, through Human Workflow Services.</span></span>  
  
## <a name="integration-of-heterogeneous-systems"></a><span data-ttu-id="0be0e-123">异构系统的集成</span><span class="sxs-lookup"><span data-stu-id="0be0e-123">Integration of Heterogeneous Systems</span></span>  
 <span data-ttu-id="0be0e-124">BizTalk Server 可以将在其中系统传输不同通信协议中的数据对异类环境中的 IT 系统集成。</span><span class="sxs-lookup"><span data-stu-id="0be0e-124">BizTalk Server can integrate IT systems in a heterogeneous environment in which systems transmit data in different communications protocols.</span></span> <span data-ttu-id="0be0e-125">这是通过使用适配器连接使用不同协议的系统而实现的。</span><span class="sxs-lookup"><span data-stu-id="0be0e-125">It does so by using adapters to connect to systems using different protocols.</span></span> <span data-ttu-id="0be0e-126">它支持使用的文件、 FTP、 HTTP、 SMTP、 SOAP 和 SQL 适配器。</span><span class="sxs-lookup"><span data-stu-id="0be0e-126">It supports the use of File, FTP, HTTP, SMTP, SOAP, and SQL adapters.</span></span> <span data-ttu-id="0be0e-127">你可以使用 BizTalk 适配器框架来创建自定义的适配器。</span><span class="sxs-lookup"><span data-stu-id="0be0e-127">You can create custom adapters by using the BizTalk Adapter Framework.</span></span>  
  
## <a name="role-based-tools"></a><span data-ttu-id="0be0e-128">基于角色的工具</span><span class="sxs-lookup"><span data-stu-id="0be0e-128">Role-based Tools</span></span>  
 <span data-ttu-id="0be0e-129">BizTalk Server 是在其中开发人员、 IT 专业人员和业务专业人员协作创建、 实现、 操作、 维护和自定义系统开发和执行环境。</span><span class="sxs-lookup"><span data-stu-id="0be0e-129">BizTalk Server is a development and execution environment in which developers, IT professionals, and business professionals collaborate to create, implement, operate, maintain, and customize the system.</span></span> <span data-ttu-id="0be0e-130">BizTalk Server 提供的每个这些角色定制其使用的工具。</span><span class="sxs-lookup"><span data-stu-id="0be0e-130">BizTalk Server provides each of these roles with tools tailored to their use.</span></span>  
  
 <span data-ttu-id="0be0e-131">有关详细信息，请参阅[基于角色的产品](../../adapters-and-accelerators/accelerator-hl7/a-role-based-product1.md)。</span><span class="sxs-lookup"><span data-stu-id="0be0e-131">For more information, see [A Role-based Product](../../adapters-and-accelerators/accelerator-hl7/a-role-based-product1.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0be0e-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0be0e-132">See Also</span></span>  
 [<span data-ttu-id="0be0e-133">BizTalk Accelerator for HL7 向 BizTalk Server 添加的功能</span><span class="sxs-lookup"><span data-stu-id="0be0e-133">What BizTalk Accelerator for HL7 Adds to BizTalk Server</span></span>](../../adapters-and-accelerators/accelerator-hl7/what-biztalk-accelerator-for-hl7-adds-to-biztalk-server.md)