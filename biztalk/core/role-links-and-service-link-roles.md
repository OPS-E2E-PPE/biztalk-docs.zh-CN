---
title: 角色链接和服务链接角色 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, orchestrations
- service link roles
- role links
- roles, orchestrations
- roles
- roles, about roles
- service link roles, about service link roles
- orchestrations, roles
- role links, about role links
- orchestrations, deleting
ms.assetid: 23b4ca34-a1a5-44d4-a50d-661277681c72
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7b52a13878363e79b9b2ffa3e600de16aeacd3c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254712"
---
# <a name="role-links-and-service-link-roles"></a><span data-ttu-id="18377-102">角色链接和服务链接角色</span><span class="sxs-lookup"><span data-stu-id="18377-102">Role Links and Service Link Roles</span></span>
<span data-ttu-id="18377-103">一个*角色*是使用一项服务或实现服务的端口类型集合。</span><span class="sxs-lookup"><span data-stu-id="18377-103">A *role* is a collection of port types that either uses a service or implements a service.</span></span> <span data-ttu-id="18377-104">角色表示参与方可以与一个或多个业务流程的交互的类型。</span><span class="sxs-lookup"><span data-stu-id="18377-104">A role represents the type of interaction that a party can have with one or many orchestrations.</span></span> <span data-ttu-id="18377-105">角色提供灵活性和易于管理的参与方增加数。</span><span class="sxs-lookup"><span data-stu-id="18377-105">Roles provide flexibility and ease of management as the number of parties increase.</span></span> <span data-ttu-id="18377-106">例如，业务流程可能使用发运方角色。</span><span class="sxs-lookup"><span data-stu-id="18377-106">For example, an orchestration might use the role of a Shipper.</span></span> <span data-ttu-id="18377-107">发运方具有与其关联的一个或两个参与方。</span><span class="sxs-lookup"><span data-stu-id="18377-107">The Shipper would have one or two parties associated with it.</span></span> <span data-ttu-id="18377-108">当业务流程确定哪家送货公司来发运货物的使用时，它会比较发运方角色中各个参与方的价格。</span><span class="sxs-lookup"><span data-stu-id="18377-108">When the orchestration decides which shipping company to use to ship an item, it compares the prices of the parties in the Shipper role.</span></span>  
  
 <span data-ttu-id="18377-109">一个*角色链接类型*是两个服务或业务流程之间的关系的属性。</span><span class="sxs-lookup"><span data-stu-id="18377-109">A *role link type* is a property that characterizes the relationship between two services or orchestrations.</span></span> <span data-ttu-id="18377-110">它定义每个关系中服务的作用，并指定每个角色提供的端口类型。</span><span class="sxs-lookup"><span data-stu-id="18377-110">It defines the part played by each of the services in the relationship and specifies the port types provided by each role.</span></span>  
  
 <span data-ttu-id="18377-111">参与方或组织单位，表示位于与业务流程交互的 BizTalk Server 之外的实体。</span><span class="sxs-lookup"><span data-stu-id="18377-111">A party, or organizational unit, represents an entity outside of BizTalk Server that interacts with an orchestration.</span></span> <span data-ttu-id="18377-112">在 BizTalk Server 中，与之交换消息每个组织都以参与方表示。</span><span class="sxs-lookup"><span data-stu-id="18377-112">In BizTalk Server, each organization with which you exchange messages is represented by a party.</span></span> <span data-ttu-id="18377-113">您可以定义通过在角色中登记参与方的交互方式。</span><span class="sxs-lookup"><span data-stu-id="18377-113">You can define how the party interacts by enlisting it in a role.</span></span>  
  
 <span data-ttu-id="18377-114">你可以部署或与业务流程关联后删除角色链接类型。</span><span class="sxs-lookup"><span data-stu-id="18377-114">You can deploy or remove a role link type when it is associated with an orchestration.</span></span>  
  
## <a name="orchestrations-and-roles"></a><span data-ttu-id="18377-115">业务流程和角色</span><span class="sxs-lookup"><span data-stu-id="18377-115">Orchestrations and Roles</span></span>  
 <span data-ttu-id="18377-116">在部署使用角色链接类型的业务流程时，配置数据库将保存该角色。</span><span class="sxs-lookup"><span data-stu-id="18377-116">When you deploy an orchestration that uses a role link type, the Configuration database saves the role.</span></span> <span data-ttu-id="18377-117">由于一个角色可以由多个业务流程，管理数据库将保存角色链接类型只有一个的副本。</span><span class="sxs-lookup"><span data-stu-id="18377-117">Because a role can be used by more than one orchestration, the Management database saves only one copy of the role link type.</span></span>  
  
 <span data-ttu-id="18377-118">如果您的 BizTalk 项目包含两个单独的业务流程 (.odx) 文件中具有相同名称和命名空间中的角色链接类型，不会进行编译您的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="18377-118">If your BizTalk project contains two role link types in separate orchestration (.odx) files that have the same name and namespace, your BizTalk project does not compile.</span></span>  
  
### <a name="orchestration-removals-that-use-roles"></a><span data-ttu-id="18377-119">使用角色的业务流程删除</span><span class="sxs-lookup"><span data-stu-id="18377-119">Orchestration Removals that use Roles</span></span>  
 <span data-ttu-id="18377-120">由于角色链接类型可以使用多个业务流程，取消部署包含使用角色的业务流程的程序集时，管理数据库中删除角色，仅当没有其他业务流程使用该角色。</span><span class="sxs-lookup"><span data-stu-id="18377-120">Because a role link type can be used by more than one orchestration, when you undeploy an assembly that contains an orchestration that uses a role, the Management database removes the role only if no other orchestrations are using the role.</span></span>  
  
 <span data-ttu-id="18377-121">此外，管理数据库中删除角色仅在没有任何与其已登记的参与方。</span><span class="sxs-lookup"><span data-stu-id="18377-121">Additionally, the Management database removes a role only if there are no parties enlisted with it.</span></span> <span data-ttu-id="18377-122">正如您无法覆盖具有已登记的参与方的角色，则无法删除具有与其已登记参与方的角色。</span><span class="sxs-lookup"><span data-stu-id="18377-122">Just as you cannot overwrite a role that has parties enlisted with it, you cannot remove a role that has parties enlisted with it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18377-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="18377-123">See Also</span></span>  
 <span data-ttu-id="18377-124">[在业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="18377-124">[Using Role Links in Orchestrations](../core/using-role-links-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="18377-125">项目</span><span class="sxs-lookup"><span data-stu-id="18377-125">Artifacts</span></span>](../core/artifacts.md)