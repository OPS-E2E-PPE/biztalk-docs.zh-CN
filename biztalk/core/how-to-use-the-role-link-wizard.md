---
title: 如何使用角色链接向导 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- links [roles]
- Role Link Wizard [Orchestration Designer]
- roles, links
- Orchestration Designer, Role Link Wizard
- role links, Role Link Wizard [Orchestration Designer]
- links [roles], about links
ms.assetid: ddc33d87-c08d-4193-9483-4644ef302853
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5336dcbb129b01be8fc03c43756bb1fc1ac53063
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333202"
---
# <a name="how-to-use-the-role-link-wizard"></a><span data-ttu-id="045dd-102">如何使用角色链接向导</span><span class="sxs-lookup"><span data-stu-id="045dd-102">How to Use the Role Link Wizard</span></span>
<span data-ttu-id="045dd-103">角色链接向导，可创建新的角色链接或修改一个现有。</span><span class="sxs-lookup"><span data-stu-id="045dd-103">The Role Link Wizard enables you to create a new role link or modify an existing one.</span></span> <span data-ttu-id="045dd-104">可以使用它来设置或查看名称、 类型和角色链接，以及实现角色和撰写的角色链接类型使用角色的访问限制。</span><span class="sxs-lookup"><span data-stu-id="045dd-104">You can use it to set or view the name, type, and access restriction of the role link, as well as the implements role and the uses role that compose the role link type.</span></span> <span data-ttu-id="045dd-105">若要了解如何角色链接的工作，请参阅[业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="045dd-105">To understand how role links work, see [Using Role Links in Orchestrations](../core/using-role-links-in-orchestrations.md).</span></span>  
  
 <span data-ttu-id="045dd-106">**角色链接名称**:角色链接名称为您填充，并为要配置的现有角色链接的当前名称或自动生成的名称，如果要创建新的角色链接。</span><span class="sxs-lookup"><span data-stu-id="045dd-106">**Role link name**: The role link name is filled in for you and is either the current name of an existing role link that you are configuring, or an automatically generated name if you are creating a new role link.</span></span> <span data-ttu-id="045dd-107">在任一情况下可以修改名称。</span><span class="sxs-lookup"><span data-stu-id="045dd-107">In either case you can modify the name.</span></span>  
  
 <span data-ttu-id="045dd-108">**角色链接类型**:可以选择现有角色链接类型，也可以创建一个新。</span><span class="sxs-lookup"><span data-stu-id="045dd-108">**Role link type**: You can select an existing role link type, or create a new one.</span></span> <span data-ttu-id="045dd-109">是否要配置新的或现有角色链接类型，您可以指定您的业务流程参与服务的方式。</span><span class="sxs-lookup"><span data-stu-id="045dd-109">Whether you are configuring a new or existing role link type, you can specify how your orchestration participates in the service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="045dd-110">我们建议你创建的角色链接类型和关联的端口类型之前，若要创建角色链接，以便您可以使用现有角色链接类型用于定义角色链接。</span><span class="sxs-lookup"><span data-stu-id="045dd-110">We recommend that you create the role link type and associated port type prior to create the role link so that you can use an existing role link type for defining your role link.</span></span> <span data-ttu-id="045dd-111">有关详细信息，请参阅[如何在业务流程中创建角色链接](../core/how-to-create-role-links-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="045dd-111">For more information, see [How to Create Role Links in Orchestrations](../core/how-to-create-role-links-in-orchestrations.md).</span></span>  
  
 <span data-ttu-id="045dd-112">**角色链接用法**:如果创建新的角色链接类型，会自动为您创建实现和使用角色。</span><span class="sxs-lookup"><span data-stu-id="045dd-112">**Role link usage**: If you create a new role link type, both the implements and uses roles are automatically created for you.</span></span> <span data-ttu-id="045dd-113">可以选择反映了您的业务流程参与服务的方式的角色。</span><span class="sxs-lookup"><span data-stu-id="045dd-113">You can select the role that reflects how your orchestration participates in the service.</span></span> <span data-ttu-id="045dd-114">完成向导中的步骤后，可以重命名角色标识符或删除角色以更好地匹配您的实现。</span><span class="sxs-lookup"><span data-stu-id="045dd-114">After you have completed the steps in the wizard, you can rename the role identifiers or remove a role to better match your implementation.</span></span> <span data-ttu-id="045dd-115">角色链接类型必须包含一个是角色类型或每个角色类型之一。</span><span class="sxs-lookup"><span data-stu-id="045dd-115">A role link type must contain one of either role type or one of each role type.</span></span> <span data-ttu-id="045dd-116">当您单击**确定**，未配置的角色创建与每个名称相对应。</span><span class="sxs-lookup"><span data-stu-id="045dd-116">When you click **OK**, unconfigured roles are created corresponding to each name.</span></span> <span data-ttu-id="045dd-117">此外可以在类型窗口中选择端口类型的角色。</span><span class="sxs-lookup"><span data-stu-id="045dd-117">You can also select port types for the roles in the Types window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="045dd-118">如果您调用端口配置向导以创建端口类型为角色链接类型，并且想要选择以前定义的端口类型，请确保端口类型的访问限制与角色链接类型的访问限制不冲突。</span><span class="sxs-lookup"><span data-stu-id="045dd-118">If you invoke the Port Configuration Wizard to create a port type for your role link type, and want to select a previously defined port type, ensure that the access restrictions of the port type do not conflict with the access restrictions of the role link type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="045dd-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="045dd-119">See Also</span></span>  
 [<span data-ttu-id="045dd-120">在业务流程中使用角色链接</span><span class="sxs-lookup"><span data-stu-id="045dd-120">Using Role Links in Orchestrations</span></span>](../core/using-role-links-in-orchestrations.md)