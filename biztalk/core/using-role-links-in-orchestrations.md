---
title: 在业务流程中使用角色链接 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- role links
- roles, links
- roles
- roles, about roles
- role links, about role links
- role links, properties
- role links, initializing
ms.assetid: 0cf85544-12c9-4541-8925-61a6e946cce0
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e3c4e4a4c3a99fb6e1962299d440717eaa8d51b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288461"
---
# <a name="using-role-links-in-orchestrations"></a><span data-ttu-id="3fd42-102">在业务流程中使用角色链接</span><span class="sxs-lookup"><span data-stu-id="3fd42-102">Using Role Links in Orchestrations</span></span>
<span data-ttu-id="3fd42-103">角色链接将业务流程与贸易合作伙伴之间的交互活动以抽象的形式表现出来。</span><span class="sxs-lookup"><span data-stu-id="3fd42-103">Role links are a form of abstraction for the interactions between your orchestration and your trading partners.</span></span> <span data-ttu-id="3fd42-104">借助角色链接，您就可以在不改变整体业务流程的前提下，依据贸易合作伙伴解析、消息内容或数据库查询结果，动态地选择要交互的贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="3fd42-104">Role links enable you to dynamically choose which trading partner to interact with based on trading partner resolution, message content, or the results of a database lookup while maintaining your overall business process intact.</span></span>  
  
 <span data-ttu-id="3fd42-105">例如在企业对企业方案中，有多个买方，一个供应商，同时该供应商还有多个发货机构。</span><span class="sxs-lookup"><span data-stu-id="3fd42-105">For example, in a business-to-business scenario, there are multiple buyers, a single supplier, and multiple shipping agencies for the supplier.</span></span> <span data-ttu-id="3fd42-106">如果一个买方向供应商发送采购订单，供应商通过参与方解析，就可以知道该采购订单是哪个买方发送的，从而采用相应的折扣。</span><span class="sxs-lookup"><span data-stu-id="3fd42-106">When a buyer sends a purchase order to the supplier, the supplier knows through party resolution which buyer is sending the purchase order and can apply the appropriate discount.</span></span> <span data-ttu-id="3fd42-107">而且，供应商还可依据所订购的商品，在运行时确定由哪个发货机构负责送货。</span><span class="sxs-lookup"><span data-stu-id="3fd42-107">Moreover, based on the goods ordered, the supplier determines at run time which shipping agency will be in charge of the delivery.</span></span> <span data-ttu-id="3fd42-108">尽管每个发货机构都可能有自己的传输协议，但供应商仍可在运行时使用同一业务流程来应对所有发货机构，并确定要联系哪个发货机构。</span><span class="sxs-lookup"><span data-stu-id="3fd42-108">Although each shipping agency may have its own transport protocol, the supplier can use the same business process at run time to handle all the shipping agencies and determine which agency to interact with.</span></span> <span data-ttu-id="3fd42-109">在后面的阶段，如果传送代理更新其传输协议 — 例如，从 FTP 改为 HTTP-供应商仅需要使用 BizTalk 资源管理器或 BizTalk Server 管理控制台来更新与该特定传送代理关联的发送端口。</span><span class="sxs-lookup"><span data-stu-id="3fd42-109">At a later stage, if a shipping agency updates its transport protocol—for example, from FTP to HTTP—the supplier only needs to use BizTalk Explorer or the BizTalk Server Administration console to update the send port associated with that particular shipping agency.</span></span> <span data-ttu-id="3fd42-110">供应商不需要更改业务流程中的业务程序。</span><span class="sxs-lookup"><span data-stu-id="3fd42-110">The supplier does not need to change its business process, which resides in the orchestration.</span></span>  
  
## <a name="roles"></a><span data-ttu-id="3fd42-111">角色</span><span class="sxs-lookup"><span data-stu-id="3fd42-111">Roles</span></span>  
 <span data-ttu-id="3fd42-112">业务流程中有两个角色：</span><span class="sxs-lookup"><span data-stu-id="3fd42-112">There are two roles in an orchestration:</span></span>  
  
-   <span data-ttu-id="3fd42-113">一个是“实现”角色，负责接收和处理消息。</span><span class="sxs-lookup"><span data-stu-id="3fd42-113">An "implements" role to receive and process messages.</span></span> <span data-ttu-id="3fd42-114">该角色也称为提供者。</span><span class="sxs-lookup"><span data-stu-id="3fd42-114">This role is also known as the provider.</span></span>  
  
-   <span data-ttu-id="3fd42-115">一个是“使用”角色，负责发送消息。</span><span class="sxs-lookup"><span data-stu-id="3fd42-115">A "uses" role to send messages.</span></span> <span data-ttu-id="3fd42-116">该角色也称为使用者。</span><span class="sxs-lookup"><span data-stu-id="3fd42-116">This role is also known as the consumer.</span></span>  
  
## <a name="role-links"></a><span data-ttu-id="3fd42-117">角色链接</span><span class="sxs-lookup"><span data-stu-id="3fd42-117">Role Links</span></span>  
 <span data-ttu-id="3fd42-118">一个角色链接可包含一个使用者角色或一个提供者角色，也可各含一个。</span><span class="sxs-lookup"><span data-stu-id="3fd42-118">A role link can include either a consumer or a provider role, or one of each.</span></span> <span data-ttu-id="3fd42-119">使用者角色享受提供者角色提供的服务。</span><span class="sxs-lookup"><span data-stu-id="3fd42-119">A consumer role consumes the services provided by the provider role.</span></span> <span data-ttu-id="3fd42-120">如果您所定义的角色链接具有一种或两种这样的角色，则将假定与您链接的合作伙伴充当了互补角色。</span><span class="sxs-lookup"><span data-stu-id="3fd42-120">When you define a role link with one or both of these roles, it is assumed that the complementary role is being fulfilled by the partner with whom you are linking.</span></span>  
  
 <span data-ttu-id="3fd42-121">角色链接具有**SourceParty**属性， **DestinationParty**属性，且启动角色。</span><span class="sxs-lookup"><span data-stu-id="3fd42-121">A role link has a **SourceParty** property, a **DestinationParty** property, and an initiating role.</span></span> <span data-ttu-id="3fd42-122">启动角色是在首次通信发生，并且这将因此启动角色链接通过设置的值的角色**DestinationParty**属性。</span><span class="sxs-lookup"><span data-stu-id="3fd42-122">An initiating role is the role on which the first communication occurs, and which therefore initiates the role link by setting the value of the **DestinationParty** property.</span></span>  
  
 <span data-ttu-id="3fd42-123">如果启动的角色仅适用于发送消息的使用者，则显式设置**DestinationParty**业务流程中的属性 （一次，并且一次）。</span><span class="sxs-lookup"><span data-stu-id="3fd42-123">If the initiating role is a consumer for sending messages, you explicitly set the **DestinationParty** property (once and only once) in your orchestration.</span></span> <span data-ttu-id="3fd42-124">若要执行此操作，你设置的值**DestinationParty**中**表达式**形状，如以下示例，其中 ConfirmOrder 是相应角色的名称，使用省略号和单位名称是所示方的参数：</span><span class="sxs-lookup"><span data-stu-id="3fd42-124">To do so, you set the value of the **DestinationParty** in the **Expression** shape, as in the following example, where ConfirmOrder is the name of a role link, and PartnerName and OrganizationName are parameters of a party:</span></span>  
  
```  
ConfirmOrder(Microsoft.XLANGs.BaseTypes.DestinationParty) = new Microsoft.XLANGs.BaseTypes.Party("PartnerName", "OrganizationName");  
```  
  
 <span data-ttu-id="3fd42-125">如果启动角色是提供用于接收消息， **DestinationParty**接收方自动初始化属性。</span><span class="sxs-lookup"><span data-stu-id="3fd42-125">If the initiating role is a provider for receiving messages, the **DestinationParty** property is initialized automatically by the receiver.</span></span> <span data-ttu-id="3fd42-126">**DestinationParty**设置为提供程序本身。</span><span class="sxs-lookup"><span data-stu-id="3fd42-126">The **DestinationParty** is set to the provider itself.</span></span> <span data-ttu-id="3fd42-127">**SourceParty**属性是只读的并且要为基于或与方相关联的证书上的安全标识符 (SID) 发件人的方名称解析的受信任的管道组件通过提供。</span><span class="sxs-lookup"><span data-stu-id="3fd42-127">The **SourceParty** property is read-only, and is supplied through a trusted pipeline component to resolve the party name based on the security identifier (SID) of the sender or on a certificate associated with the party.</span></span> <span data-ttu-id="3fd42-128">运行管道组件的主机必须标记为**受信任的身份验证**。</span><span class="sxs-lookup"><span data-stu-id="3fd42-128">The host running the pipeline component must be marked as **Authentication Trusted**.</span></span> <span data-ttu-id="3fd42-129">你可以获取的值**SourceParty**中**表达式**通过使用下面的示例代码的形状：</span><span class="sxs-lookup"><span data-stu-id="3fd42-129">You can get the value of the **SourceParty** in the **Expression** shape by using the following sample code:</span></span>  
  
 `PartyName = Buyer_Supplier(Microsoft.XLANGs.BaseTypes.SourceParty);`  
  
## <a name="role-link-types"></a><span data-ttu-id="3fd42-130">角色链接类型</span><span class="sxs-lookup"><span data-stu-id="3fd42-130">Role Link Types</span></span>  
 <span data-ttu-id="3fd42-131">角色链接是由一个或两个角色组成的角色链接类型的实例。</span><span class="sxs-lookup"><span data-stu-id="3fd42-131">A role link is an instance of a role link type, which consists of either one or two roles.</span></span> <span data-ttu-id="3fd42-132">使用角色链接类型时，请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="3fd42-132">When working with a role link type, consider the following:</span></span>  
  
-   <span data-ttu-id="3fd42-133">对于任何给定的端口类型，只能在单个角色链接类型中对其引用一次。</span><span class="sxs-lookup"><span data-stu-id="3fd42-133">You can refer only once to any given port type within a single role link type.</span></span>  
  
-   <span data-ttu-id="3fd42-134">由于角色链接类型定义中包括端口类型，因此端口类型的作用域必须包含使用它的所有角色链接类型的作用域。</span><span class="sxs-lookup"><span data-stu-id="3fd42-134">Because a role link type definition includes port types, the scope of a port type must encompass that of any role link type that uses it.</span></span>  
  
-   <span data-ttu-id="3fd42-135">使用业务活动服务 (BAS) 时，必须在同一 BizTalk 程序集中定义结构化的参数架构和与其相关联的角色链接类型。</span><span class="sxs-lookup"><span data-stu-id="3fd42-135">When working with Business Activity Services (BAS), the structured parameter schema must be defined in the same BizTalk assembly as the role link type it is associated with.</span></span> <span data-ttu-id="3fd42-136">由于与架构相关联的是角色链接类型，而不是组成该角色链接类型的各个角色，因此如果扮演不同角色的参与方共享包含该角色类型的程序集，则双方会看到相同的结构化参数架构。</span><span class="sxs-lookup"><span data-stu-id="3fd42-136">Because the schema is associated with the role link type and not with the individual roles that make up that role link type, if the parties that play the different roles share the assembly containing the role link type, both parties will see the same structured parameter schemas.</span></span> <span data-ttu-id="3fd42-137">如果双方使用相同的角色链接类型，但必须拥有不同的参数架构，则应创建不同的程序集。</span><span class="sxs-lookup"><span data-stu-id="3fd42-137">If the two parties use the same role link type but must have different parameter schemas, a different assembly should be created for each party.</span></span> <span data-ttu-id="3fd42-138">各自程序集中的角色链接类型应完全相同。</span><span class="sxs-lookup"><span data-stu-id="3fd42-138">The role link type should be duplicated in each assembly.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3fd42-139">本节内容</span><span class="sxs-lookup"><span data-stu-id="3fd42-139">In This Section</span></span>  
  
-   [<span data-ttu-id="3fd42-140">如何在业务流程中创建角色链接</span><span class="sxs-lookup"><span data-stu-id="3fd42-140">How to Create Role Links in Orchestrations</span></span>](../core/how-to-create-role-links-in-orchestrations.md)  
  
-   [<span data-ttu-id="3fd42-141">如何使用角色链接形状</span><span class="sxs-lookup"><span data-stu-id="3fd42-141">How to Use the Role Link Shape</span></span>](../core/how-to-use-the-role-link-shape.md)  
  
-   [<span data-ttu-id="3fd42-142">如何使用角色链接向导</span><span class="sxs-lookup"><span data-stu-id="3fd42-142">How to Use the Role Link Wizard</span></span>](../core/how-to-use-the-role-link-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="3fd42-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3fd42-143">See Also</span></span>  
 <span data-ttu-id="3fd42-144">[如何配置参与方解析管道组件](../core/how-to-configure-the-party-resolution-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="3fd42-144">[How to Configure the Party Resolution Pipeline Component](../core/how-to-configure-the-party-resolution-pipeline-component.md) </span></span>  
 [<span data-ttu-id="3fd42-145">使用在业务流程中的端口</span><span class="sxs-lookup"><span data-stu-id="3fd42-145">Using Ports in Orchestrations</span></span>](../core/using-ports-in-orchestrations.md)