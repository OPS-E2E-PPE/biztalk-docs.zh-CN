---
title: 在业务流程中使用角色链接 |Microsoft Docs
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
ms.openlocfilehash: 3508252cd77f002d635958f0f2bdc0202ace2d56
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396558"
---
# <a name="using-role-links-in-orchestrations"></a><span data-ttu-id="d25e5-102">在业务流程中使用角色链接</span><span class="sxs-lookup"><span data-stu-id="d25e5-102">Using Role Links in Orchestrations</span></span>
<span data-ttu-id="d25e5-103">角色链接是抽象的一种形式以用于在您的业务流程与贸易合作伙伴之间的交互。</span><span class="sxs-lookup"><span data-stu-id="d25e5-103">Role links are a form of abstraction for the interactions between your orchestration and your trading partners.</span></span> <span data-ttu-id="d25e5-104">角色链接，可以动态地选择要与之交互的贸易合作伙伴基于贸易合作伙伴解析、 消息内容或数据库查询结果，同时保持整体业务流程保持不变。</span><span class="sxs-lookup"><span data-stu-id="d25e5-104">Role links enable you to dynamically choose which trading partner to interact with based on trading partner resolution, message content, or the results of a database lookup while maintaining your overall business process intact.</span></span>  
  
 <span data-ttu-id="d25e5-105">例如，在企业到企业方案中，有多个买方，一个供应商和供应商的多个发货机构。</span><span class="sxs-lookup"><span data-stu-id="d25e5-105">For example, in a business-to-business scenario, there are multiple buyers, a single supplier, and multiple shipping agencies for the supplier.</span></span> <span data-ttu-id="d25e5-106">当购买者向供应商发送采购订单时，供应商知道通过参与方解析哪个买方发送采购订单，并且可以采用相应的折扣。</span><span class="sxs-lookup"><span data-stu-id="d25e5-106">When a buyer sends a purchase order to the supplier, the supplier knows through party resolution which buyer is sending the purchase order and can apply the appropriate discount.</span></span> <span data-ttu-id="d25e5-107">供应商基于订购的商品，此外，确定在运行时的发货机构将负责交付。</span><span class="sxs-lookup"><span data-stu-id="d25e5-107">Moreover, based on the goods ordered, the supplier determines at run time which shipping agency will be in charge of the delivery.</span></span> <span data-ttu-id="d25e5-108">尽管每个发货机构可能有其自己的传输协议，但供应商可以使用同一个业务流程在运行时来处理所有发货机构并确定哪个机构与进行交互。</span><span class="sxs-lookup"><span data-stu-id="d25e5-108">Although each shipping agency may have its own transport protocol, the supplier can use the same business process at run time to handle all the shipping agencies and determine which agency to interact with.</span></span> <span data-ttu-id="d25e5-109">在后面的阶段，如果发货机构更新其传输协议 — 例如，从 HTTP 到 FTP-供应商只需使用 BizTalk 浏览器或 BizTalk Server 管理控制台来更新与该特定发货机构相关联的发送端口。</span><span class="sxs-lookup"><span data-stu-id="d25e5-109">At a later stage, if a shipping agency updates its transport protocol—for example, from FTP to HTTP—the supplier only needs to use BizTalk Explorer or the BizTalk Server Administration console to update the send port associated with that particular shipping agency.</span></span> <span data-ttu-id="d25e5-110">供应商不需要更改其业务流程中，将驻留在业务流程中。</span><span class="sxs-lookup"><span data-stu-id="d25e5-110">The supplier does not need to change its business process, which resides in the orchestration.</span></span>  
  
## <a name="roles"></a><span data-ttu-id="d25e5-111">角色</span><span class="sxs-lookup"><span data-stu-id="d25e5-111">Roles</span></span>  
 <span data-ttu-id="d25e5-112">在业务流程中有两个角色：</span><span class="sxs-lookup"><span data-stu-id="d25e5-112">There are two roles in an orchestration:</span></span>  
  
-   <span data-ttu-id="d25e5-113">"实现"角色来接收和处理消息。</span><span class="sxs-lookup"><span data-stu-id="d25e5-113">An "implements" role to receive and process messages.</span></span> <span data-ttu-id="d25e5-114">此角色也称为是提供程序。</span><span class="sxs-lookup"><span data-stu-id="d25e5-114">This role is also known as the provider.</span></span>  
  
-   <span data-ttu-id="d25e5-115">若要将消息发送"使用"角色。</span><span class="sxs-lookup"><span data-stu-id="d25e5-115">A "uses" role to send messages.</span></span> <span data-ttu-id="d25e5-116">此角色是也称为使用者。</span><span class="sxs-lookup"><span data-stu-id="d25e5-116">This role is also known as the consumer.</span></span>  
  
## <a name="role-links"></a><span data-ttu-id="d25e5-117">角色链接</span><span class="sxs-lookup"><span data-stu-id="d25e5-117">Role Links</span></span>  
 <span data-ttu-id="d25e5-118">角色链接可以包含使用者或提供者角色或每个的一个。</span><span class="sxs-lookup"><span data-stu-id="d25e5-118">A role link can include either a consumer or a provider role, or one of each.</span></span> <span data-ttu-id="d25e5-119">使用者角色享受提供者角色提供的服务。</span><span class="sxs-lookup"><span data-stu-id="d25e5-119">A consumer role consumes the services provided by the provider role.</span></span> <span data-ttu-id="d25e5-120">在定义的角色链接具有一个或两个这些角色时，假定要与之链接的合作伙伴，要满足了互补角色。</span><span class="sxs-lookup"><span data-stu-id="d25e5-120">When you define a role link with one or both of these roles, it is assumed that the complementary role is being fulfilled by the partner with whom you are linking.</span></span>  
  
 <span data-ttu-id="d25e5-121">角色链接具有**SourceParty**属性， **DestinationParty**属性，以及初始化角色。</span><span class="sxs-lookup"><span data-stu-id="d25e5-121">A role link has a **SourceParty** property, a **DestinationParty** property, and an initiating role.</span></span> <span data-ttu-id="d25e5-122">初始化角色是在首次通信出现，这种情况，和用于因此启动角色链接的值设置角色**DestinationParty**属性。</span><span class="sxs-lookup"><span data-stu-id="d25e5-122">An initiating role is the role on which the first communication occurs, and which therefore initiates the role link by setting the value of the **DestinationParty** property.</span></span>  
  
 <span data-ttu-id="d25e5-123">如果初始化角色是一个使用者发送消息，则显式设置**DestinationParty**属性 （仅一次） 在业务流程中的。</span><span class="sxs-lookup"><span data-stu-id="d25e5-123">If the initiating role is a consumer for sending messages, you explicitly set the **DestinationParty** property (once and only once) in your orchestration.</span></span> <span data-ttu-id="d25e5-124">若要执行此操作，你设置的值**DestinationParty**中**表达式**形状，如下面的示例，其中，ConfirmOrder 是角色链接的名称，PartnerName 和 OrganizationName 是中所示参与方的参数：</span><span class="sxs-lookup"><span data-stu-id="d25e5-124">To do so, you set the value of the **DestinationParty** in the **Expression** shape, as in the following example, where ConfirmOrder is the name of a role link, and PartnerName and OrganizationName are parameters of a party:</span></span>  
  
```  
ConfirmOrder(Microsoft.XLANGs.BaseTypes.DestinationParty) = new Microsoft.XLANGs.BaseTypes.Party("PartnerName", "OrganizationName");  
```  
  
 <span data-ttu-id="d25e5-125">如果初始化角色是用于接收消息，提供商**DestinationParty**接收方会自动初始化属性。</span><span class="sxs-lookup"><span data-stu-id="d25e5-125">If the initiating role is a provider for receiving messages, the **DestinationParty** property is initialized automatically by the receiver.</span></span> <span data-ttu-id="d25e5-126">**DestinationParty**设置为提供程序本身。</span><span class="sxs-lookup"><span data-stu-id="d25e5-126">The **DestinationParty** is set to the provider itself.</span></span> <span data-ttu-id="d25e5-127">**SourceParty**属性是只读的并且提供通过受信任的管道组件以解析参与方名称基于安全标识符 (SID) 发件人或与该参与方相关联的证书。</span><span class="sxs-lookup"><span data-stu-id="d25e5-127">The **SourceParty** property is read-only, and is supplied through a trusted pipeline component to resolve the party name based on the security identifier (SID) of the sender or on a certificate associated with the party.</span></span> <span data-ttu-id="d25e5-128">运行该管道组件的主机必须标记为**受信任验证**。</span><span class="sxs-lookup"><span data-stu-id="d25e5-128">The host running the pipeline component must be marked as **Authentication Trusted**.</span></span> <span data-ttu-id="d25e5-129">你可以获取的值**SourceParty**中**表达式**形状使用下面的示例代码：</span><span class="sxs-lookup"><span data-stu-id="d25e5-129">You can get the value of the **SourceParty** in the **Expression** shape by using the following sample code:</span></span>  
  
 `PartyName = Buyer_Supplier(Microsoft.XLANGs.BaseTypes.SourceParty);`  
  
## <a name="role-link-types"></a><span data-ttu-id="d25e5-130">角色链接类型</span><span class="sxs-lookup"><span data-stu-id="d25e5-130">Role Link Types</span></span>  
 <span data-ttu-id="d25e5-131">角色链接是角色链接类型，其中包括一个或两个角色的实例。</span><span class="sxs-lookup"><span data-stu-id="d25e5-131">A role link is an instance of a role link type, which consists of either one or two roles.</span></span> <span data-ttu-id="d25e5-132">当使用角色链接类型时，考虑以下方面：</span><span class="sxs-lookup"><span data-stu-id="d25e5-132">When working with a role link type, consider the following:</span></span>  
  
-   <span data-ttu-id="d25e5-133">可以为任何给定的端口类型的单个角色链接类型中只有一次引用。</span><span class="sxs-lookup"><span data-stu-id="d25e5-133">You can refer only once to any given port type within a single role link type.</span></span>  
  
-   <span data-ttu-id="d25e5-134">角色链接类型定义包括端口类型，因为端口类型的作用域必须包含的所有使用它的角色链接类型。</span><span class="sxs-lookup"><span data-stu-id="d25e5-134">Because a role link type definition includes port types, the scope of a port type must encompass that of any role link type that uses it.</span></span>  
  
-   <span data-ttu-id="d25e5-135">使用业务活动服务 (BAS) 时，必须中与之关联的角色链接类型相同的 BizTalk 程序集中定义结构化的参数架构。</span><span class="sxs-lookup"><span data-stu-id="d25e5-135">When working with Business Activity Services (BAS), the structured parameter schema must be defined in the same BizTalk assembly as the role link type it is associated with.</span></span> <span data-ttu-id="d25e5-136">因为架构关联角色链接类型而不是各个角色，组成该角色链接类型，如果扮演不同角色的参与方共享包含角色链接类型的程序集时，会看到相同的结构化的参数架构。</span><span class="sxs-lookup"><span data-stu-id="d25e5-136">Because the schema is associated with the role link type and not with the individual roles that make up that role link type, if the parties that play the different roles share the assembly containing the role link type, both parties will see the same structured parameter schemas.</span></span> <span data-ttu-id="d25e5-137">如果两个参与方使用相同的角色链接类型，但必须具有不同的参数架构，应为每个参与方创建不同的程序集。</span><span class="sxs-lookup"><span data-stu-id="d25e5-137">If the two parties use the same role link type but must have different parameter schemas, a different assembly should be created for each party.</span></span> <span data-ttu-id="d25e5-138">应在每个程序集中重复的角色链接类型。</span><span class="sxs-lookup"><span data-stu-id="d25e5-138">The role link type should be duplicated in each assembly.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d25e5-139">本节内容</span><span class="sxs-lookup"><span data-stu-id="d25e5-139">In This Section</span></span>  
  
-   [<span data-ttu-id="d25e5-140">如何在业务流程中创建角色链接</span><span class="sxs-lookup"><span data-stu-id="d25e5-140">How to Create Role Links in Orchestrations</span></span>](../core/how-to-create-role-links-in-orchestrations.md)  
  
-   [<span data-ttu-id="d25e5-141">如何使用角色链接形状</span><span class="sxs-lookup"><span data-stu-id="d25e5-141">How to Use the Role Link Shape</span></span>](../core/how-to-use-the-role-link-shape.md)  
  
-   [<span data-ttu-id="d25e5-142">如何使用角色链接向导</span><span class="sxs-lookup"><span data-stu-id="d25e5-142">How to Use the Role Link Wizard</span></span>](../core/how-to-use-the-role-link-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="d25e5-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="d25e5-143">See Also</span></span>  
 <span data-ttu-id="d25e5-144">[如何配置参与方解析管道组件](../core/how-to-configure-the-party-resolution-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="d25e5-144">[How to Configure the Party Resolution Pipeline Component](../core/how-to-configure-the-party-resolution-pipeline-component.md) </span></span>  
 [<span data-ttu-id="d25e5-145">在业务流程中使用端口</span><span class="sxs-lookup"><span data-stu-id="d25e5-145">Using Ports in Orchestrations</span></span>](../core/using-ports-in-orchestrations.md)