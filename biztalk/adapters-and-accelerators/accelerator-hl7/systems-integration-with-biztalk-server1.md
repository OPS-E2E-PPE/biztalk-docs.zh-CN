---
title: HL7 系统集成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f66a4fc-186c-415f-a7ed-31f620f0495f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b44f31b20785effb88728e63255c23245fe7051
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286546"
---
# <a name="systems-integration-with-biztalk-server"></a><span data-ttu-id="2e73a-102">与 BizTalk Server 的系统集成</span><span class="sxs-lookup"><span data-stu-id="2e73a-102">Systems Integration with BizTalk Server</span></span>
<span data-ttu-id="2e73a-103">Microsoft BizTalk Server 是为 eBusiness 应用程序设计的集成服务器。</span><span class="sxs-lookup"><span data-stu-id="2e73a-103">Microsoft BizTalk Server is an integration server designed for eBusiness applications.</span></span> <span data-ttu-id="2e73a-104">它基于 Windows Server、 SQL Server 和 SharePoint，并使用 Visual Studio 的功能。</span><span class="sxs-lookup"><span data-stu-id="2e73a-104">It is built on the  Windows Server, SQL Server, and SharePoint, and leverages the functionality of  Visual Studio.</span></span> <span data-ttu-id="2e73a-105">此技术堆栈提供了一系列功能和用于开发、 实现、 操作和维护您的解决方案的功能。</span><span class="sxs-lookup"><span data-stu-id="2e73a-105">This technology stack provides a range of functionality and features for developing, implementing, operating, and maintaining your solution.</span></span>  
  
 <span data-ttu-id="2e73a-106">BizTalk Server 提供以下集成服务，可结合使用 BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="2e73a-106">BizTalk Server provides the following integration services that you can use in conjunction with BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]).</span></span>  
  
## <a name="message-integration"></a><span data-ttu-id="2e73a-107">消息集成</span><span class="sxs-lookup"><span data-stu-id="2e73a-107">Message Integration</span></span>  
 <span data-ttu-id="2e73a-108">BizTalk Server 通过自动交换消息集成不同的实体 （部门、 业务合作伙伴、 供应商等）。</span><span class="sxs-lookup"><span data-stu-id="2e73a-108">BizTalk Server integrates different entities (departments, business partners, vendors, and so on) by automating message exchange.</span></span> <span data-ttu-id="2e73a-109">它使用可扩展标记语言 (XML) 作为一种常见通信协议。</span><span class="sxs-lookup"><span data-stu-id="2e73a-109">It uses Extensible Markup Language (XML) as a common communication protocol.</span></span> <span data-ttu-id="2e73a-110">它使用 XML 架构定义 (XSD) 架构来描述和验证消息和 XSL 转换 (XSLT) 转换到另一个消息中的数据。</span><span class="sxs-lookup"><span data-stu-id="2e73a-110">It uses XML Schema Definition (XSD) schemas to describe and validate messages, and XSL Transformations (XSLT) to transform data from one message to another.</span></span>  
  
 <span data-ttu-id="2e73a-111">BizTalk Server 集成引擎将从一个位置的消息路由到另一个。</span><span class="sxs-lookup"><span data-stu-id="2e73a-111">The BizTalk Server integration engine routes messages from one location to another.</span></span> <span data-ttu-id="2e73a-112">其特点允许一个部门发布文档，和另一个订阅的发布服务器/订阅模型。</span><span class="sxs-lookup"><span data-stu-id="2e73a-112">It features a publisher/subscriber model that enables one department to publish a document, and another to subscribe to it.</span></span> <span data-ttu-id="2e73a-113">不发布部门不知情的情况下，订阅部门可以订阅该消息。</span><span class="sxs-lookup"><span data-stu-id="2e73a-113">The subscribing department can subscribe to the message without the publishing department knowing about it.</span></span> <span data-ttu-id="2e73a-114">这样合作伙伴组织，替换为灵活的中心辐射型排列为点到点通信的高效的处理。</span><span class="sxs-lookup"><span data-stu-id="2e73a-114">This enables efficient handling of partner organizations, replacing point-to-point communications with a flexible hub-spoke arrangement.</span></span>  
  
## <a name="business-process-automation"></a><span data-ttu-id="2e73a-115">业务流程的自动化</span><span class="sxs-lookup"><span data-stu-id="2e73a-115">Business Process Automation</span></span>  
 <span data-ttu-id="2e73a-116">BizTalk Server 自动执行，并通过使用调用业务流程的流程映射以链接的一组不同但相关操作在单个进程中集成的业务流程。</span><span class="sxs-lookup"><span data-stu-id="2e73a-116">BizTalk Server automates and integrates business processes by using a process map called an orchestration to link a set of distinct, related actions in a single process.</span></span> <span data-ttu-id="2e73a-117">通过创建业务流程，你可以链接基于数据交换和分析，如消息接收、 消息发送、 决策、 循环、 步骤和其他操作。</span><span class="sxs-lookup"><span data-stu-id="2e73a-117">By creating an orchestration, you can link steps based on data exchange and analysis, such as message receiving, message sending, decisions, loops, and other operations.</span></span> <span data-ttu-id="2e73a-118">业务流程，可创建将在事件发生时自动运行的业务流程。</span><span class="sxs-lookup"><span data-stu-id="2e73a-118">An orchestration enables you to create a business process that will run automatically when an event occurs.</span></span>  
  
 <span data-ttu-id="2e73a-119">使用 BizTalk Server，你可以动态更改基于业务规则的过程。</span><span class="sxs-lookup"><span data-stu-id="2e73a-119">Using BizTalk Server, you can dynamically change a process based on business rules.</span></span> <span data-ttu-id="2e73a-120">这使你灵活地更改业务流程根据业务需要而执行的操作。</span><span class="sxs-lookup"><span data-stu-id="2e73a-120">This gives you the flexibility to change the actions taken in an orchestrated process according to business considerations.</span></span> <span data-ttu-id="2e73a-121">示例会超过特定阈值以上的订单限制订单开票审批流程。</span><span class="sxs-lookup"><span data-stu-id="2e73a-121">An example is restricting the approval process for billing orders to those orders over a certain threshold.</span></span>  
  
 <span data-ttu-id="2e73a-122">BizTalk Server 还可以包含在自动化业务流程，通过工作流服务中的人工操作。</span><span class="sxs-lookup"><span data-stu-id="2e73a-122">BizTalk Server also enables you to include human actions within automated orchestrations, through Human Workflow Services.</span></span>  
  
## <a name="integration-of-heterogeneous-systems"></a><span data-ttu-id="2e73a-123">异构系统的集成</span><span class="sxs-lookup"><span data-stu-id="2e73a-123">Integration of Heterogeneous Systems</span></span>  
 <span data-ttu-id="2e73a-124">BizTalk Server 可以集成异构环境中不同的通信协议的数据传输中的系统中的 IT 系统。</span><span class="sxs-lookup"><span data-stu-id="2e73a-124">BizTalk Server can integrate IT systems in a heterogeneous environment in which systems transmit data in different communications protocols.</span></span> <span data-ttu-id="2e73a-125">它会通过使用适配器连接到使用不同协议的系统。</span><span class="sxs-lookup"><span data-stu-id="2e73a-125">It does so by using adapters to connect to systems using different protocols.</span></span> <span data-ttu-id="2e73a-126">它支持使用的文件、 FTP、 HTTP、 SMTP、 SOAP 和 SQL 适配器。</span><span class="sxs-lookup"><span data-stu-id="2e73a-126">It supports the use of File, FTP, HTTP, SMTP, SOAP, and SQL adapters.</span></span> <span data-ttu-id="2e73a-127">可以使用 BizTalk 适配器框架来创建自定义适配器。</span><span class="sxs-lookup"><span data-stu-id="2e73a-127">You can create custom adapters by using the BizTalk Adapter Framework.</span></span>  
  
## <a name="role-based-tools"></a><span data-ttu-id="2e73a-128">基于角色的工具</span><span class="sxs-lookup"><span data-stu-id="2e73a-128">Role-based Tools</span></span>  
 <span data-ttu-id="2e73a-129">BizTalk Server 是在其中开发人员、 IT 专业人员和业务专业人员协作来创建、 实现、 操作、 维护和自定义系统的开发和执行环境。</span><span class="sxs-lookup"><span data-stu-id="2e73a-129">BizTalk Server is a development and execution environment in which developers, IT professionals, and business professionals collaborate to create, implement, operate, maintain, and customize the system.</span></span> <span data-ttu-id="2e73a-130">BizTalk Server 为每个角色提供适用于其使用的工具。</span><span class="sxs-lookup"><span data-stu-id="2e73a-130">BizTalk Server provides each of these roles with tools tailored to their use.</span></span>  
  
 <span data-ttu-id="2e73a-131">有关详细信息，请参阅[基于角色的产品](../../adapters-and-accelerators/accelerator-hl7/a-role-based-product1.md)。</span><span class="sxs-lookup"><span data-stu-id="2e73a-131">For more information, see [A Role-based Product](../../adapters-and-accelerators/accelerator-hl7/a-role-based-product1.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2e73a-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e73a-132">See Also</span></span>  
 [<span data-ttu-id="2e73a-133">BizTalk Accelerator for HL7 向 BizTalk Server 添加的功能</span><span class="sxs-lookup"><span data-stu-id="2e73a-133">What BizTalk Accelerator for HL7 Adds to BizTalk Server</span></span>](../../adapters-and-accelerators/accelerator-hl7/what-biztalk-accelerator-for-hl7-adds-to-biztalk-server.md)