---
title: "如何使用角色链接向导 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- links [roles]
- Role Link Wizard [Orchestration Designer]
- roles, links
- Orchestration Designer, Role Link Wizard
- role links, Role Link Wizard [Orchestration Designer]
- links [roles], about links
ms.assetid: ddc33d87-c08d-4193-9483-4644ef302853
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d31abcc8fcc2bfaf1ebd641e1e52ad08d1c9c9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-role-link-wizard"></a><span data-ttu-id="89400-102">如何使用角色链接向导</span><span class="sxs-lookup"><span data-stu-id="89400-102">How to Use the Role Link Wizard</span></span>
<span data-ttu-id="89400-103">使用角色链接向导，您可以创建新的角色链接或修改现有的角色链接。</span><span class="sxs-lookup"><span data-stu-id="89400-103">The Role Link Wizard enables you to create a new role link or modify an existing one.</span></span> <span data-ttu-id="89400-104">您可以使用该向导设置或查看角色链接的名称、类型和访问限制，以及组成该角色链接类型的实现角色和使用角色。</span><span class="sxs-lookup"><span data-stu-id="89400-104">You can use it to set or view the name, type, and access restriction of the role link, as well as the implements role and the uses role that compose the role link type.</span></span> <span data-ttu-id="89400-105">若要了解如何角色链接工作，请参阅[在业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="89400-105">To understand how role links work, see [Using Role Links in Orchestrations](../core/using-role-links-in-orchestrations.md).</span></span>  
  
 <span data-ttu-id="89400-106">**角色链接名称**： 角色链接名称为您填写和为你进行配置，现有角色链接的当前名称或自动生成的名称，如果要创建新的角色链接。</span><span class="sxs-lookup"><span data-stu-id="89400-106">**Role link name**: The role link name is filled in for you and is either the current name of an existing role link that you are configuring, or an automatically generated name if you are creating a new role link.</span></span> <span data-ttu-id="89400-107">在上述两种情况下，您都可以修改名称。</span><span class="sxs-lookup"><span data-stu-id="89400-107">In either case you can modify the name.</span></span>  
  
 <span data-ttu-id="89400-108">**角色链接类型**： 你可以选择现有角色链接类型，或创建一个新。</span><span class="sxs-lookup"><span data-stu-id="89400-108">**Role link type**: You can select an existing role link type, or create a new one.</span></span> <span data-ttu-id="89400-109">无论您是配置新的角色链接类型还是选择现有角色链接类型，都可以指定业务流程参与服务的方式。</span><span class="sxs-lookup"><span data-stu-id="89400-109">Whether you are configuring a new or existing role link type, you can specify how your orchestration participates in the service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89400-110">建议您在创建角色链接前，先创建角色链接类型和相关端口类型，以便可以使用现有角色链接类型来定义角色链接。</span><span class="sxs-lookup"><span data-stu-id="89400-110">We recommend that you create the role link type and associated port type prior to create the role link so that you can use an existing role link type for defining your role link.</span></span> <span data-ttu-id="89400-111">有关详细信息，请参阅[如何创建用户角色在业务流程中的链接](../core/how-to-create-role-links-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="89400-111">For more information, see [How to Create Role Links in Orchestrations](../core/how-to-create-role-links-in-orchestrations.md).</span></span>  
  
 <span data-ttu-id="89400-112">**角色链接用法**： 如果你创建新的角色链接类型，这两个实现和使用角色会自动为您创建。</span><span class="sxs-lookup"><span data-stu-id="89400-112">**Role link usage**: If you create a new role link type, both the implements and uses roles are automatically created for you.</span></span> <span data-ttu-id="89400-113">您可以选择反映您的业务流程参与服务的方式的角色。</span><span class="sxs-lookup"><span data-stu-id="89400-113">You can select the role that reflects how your orchestration participates in the service.</span></span> <span data-ttu-id="89400-114">在您完成向导中的各步骤之后，可以重命名角色标识符或删除角色以更好地匹配您的实现。</span><span class="sxs-lookup"><span data-stu-id="89400-114">After you have completed the steps in the wizard, you can rename the role identifiers or remove a role to better match your implementation.</span></span> <span data-ttu-id="89400-115">角色链接类型必须包含两个角色类型之一，或者每个角色类型各包含一个。</span><span class="sxs-lookup"><span data-stu-id="89400-115">A role link type must contain one of either role type or one of each role type.</span></span> <span data-ttu-id="89400-116">当你单击**确定**，未配置的角色创建与每个名称对应。</span><span class="sxs-lookup"><span data-stu-id="89400-116">When you click **OK**, unconfigured roles are created corresponding to each name.</span></span> <span data-ttu-id="89400-117">您还可以在“类型”窗口中为角色选择端口类型。</span><span class="sxs-lookup"><span data-stu-id="89400-117">You can also select port types for the roles in the Types window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89400-118">如果您调用端口配置向导来为您的角色链接类型创建端口类型，并且要选择以前定义的端口类型，则请确保该端口类型的访问限制与角色链接类型的访问限制不冲突。</span><span class="sxs-lookup"><span data-stu-id="89400-118">If you invoke the Port Configuration Wizard to create a port type for your role link type, and want to select a previously defined port type, ensure that the access restrictions of the port type do not conflict with the access restrictions of the role link type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89400-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89400-119">See Also</span></span>  
 [<span data-ttu-id="89400-120">在业务流程中使用角色链接</span><span class="sxs-lookup"><span data-stu-id="89400-120">Using Role Links in Orchestrations</span></span>](../core/using-role-links-in-orchestrations.md)