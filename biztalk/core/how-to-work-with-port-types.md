---
title: 如何使用端口类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, port types
- port types, deleting
- port types, Web
- port types, request-response
- orchestrations, ports
- port types, modifier
- port types
- ports, port types
- port types, one-way
ms.assetid: 78ac731e-c330-4888-a9ee-10523fef8ed0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ace5ba21f0e7615e2db9ecc192e696b229a0f3ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332883"
---
# <a name="how-to-work-with-port-types"></a><span data-ttu-id="82b0e-102">如何使用端口类型</span><span class="sxs-lookup"><span data-stu-id="82b0e-102">How to Work with Port Types</span></span>
<span data-ttu-id="82b0e-103">端口类型由通信模式、 一系列操作 （请求或响应），以及这些操作可处理的消息类型组成。</span><span class="sxs-lookup"><span data-stu-id="82b0e-103">A port type consists of a communication pattern, a set of operations (requests or responses), and the message types that those operations can work on.</span></span> <span data-ttu-id="82b0e-104">该模式可以是单向或请求-响应 （双向），并且该端口类型上定义的所有操作必须使用相同的模式。</span><span class="sxs-lookup"><span data-stu-id="82b0e-104">The pattern can be either one-way or request-response (two-way), and all operations defined on that port type must use the same pattern.</span></span> <span data-ttu-id="82b0e-105">请注意，端口类型与方向无关： 方向在各端口上指定。</span><span class="sxs-lookup"><span data-stu-id="82b0e-105">Note that port types are direction-agnostic: direction is specified on individual ports.</span></span>  
  
 <span data-ttu-id="82b0e-106">定义端口类型的作用域**的类型修饰符**属性。</span><span class="sxs-lookup"><span data-stu-id="82b0e-106">The scope of a port type is defined by the **Type Modifier** property.</span></span> <span data-ttu-id="82b0e-107">端口类型可以是公共、 私有或内部。</span><span class="sxs-lookup"><span data-stu-id="82b0e-107">A port type can be public, private, or internal.</span></span> <span data-ttu-id="82b0e-108">如果是公共的则对与该业务流程进行交互的任何人都可见。</span><span class="sxs-lookup"><span data-stu-id="82b0e-108">If it is public, it is visible to anyone interacting with the orchestration.</span></span> <span data-ttu-id="82b0e-109">如果它是私有的则在同一个项目和命名空间中的其他业务流程可见。</span><span class="sxs-lookup"><span data-stu-id="82b0e-109">If it is private, it is visible to other orchestrations within the same project and namespace.</span></span> <span data-ttu-id="82b0e-110">如果它在内部，端口类型为仅在项目内可见。</span><span class="sxs-lookup"><span data-stu-id="82b0e-110">If it is internal, the port type is visible only within the project.</span></span> <span data-ttu-id="82b0e-111">由于端口类型定义包括消息类型，消息类型的作用域必须包含的任何端口类型的使用它。</span><span class="sxs-lookup"><span data-stu-id="82b0e-111">Since a port type definition includes message types, the scope of the message type must encompass that of any port type that uses it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82b0e-112">端口类型可以应用到任意数量的端口。</span><span class="sxs-lookup"><span data-stu-id="82b0e-112">A port type can be applied to any number of ports.</span></span> <span data-ttu-id="82b0e-113">您可以将端口视为端口类型的实例。</span><span class="sxs-lookup"><span data-stu-id="82b0e-113">You can think of a port as an instance of a port type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82b0e-114">端口类型本身并没有通信方向;在各端口上设置方向。</span><span class="sxs-lookup"><span data-stu-id="82b0e-114">A port type does not inherently have a communication direction; you set direction on individual ports.</span></span>  
  
### <a name="to-add-a-request-response-port-type"></a><span data-ttu-id="82b0e-115">若要添加请求-响应端口类型</span><span class="sxs-lookup"><span data-stu-id="82b0e-115">To add a request-response port type</span></span>  
  
1.  <span data-ttu-id="82b0e-116">在业务流程视图窗口中，右键单击**端口类型**，然后单击**新建请求响应端口类型**。</span><span class="sxs-lookup"><span data-stu-id="82b0e-116">In the Orchestration View window, right-click **Port Types** and then click **New Request-response Port Type**.</span></span>  
  
     <span data-ttu-id="82b0e-117">**端口类型**节点会展开，如果处于折叠状态，且新的请求-响应端口类型添加一个带有一个默认操作。</span><span class="sxs-lookup"><span data-stu-id="82b0e-117">The **Port Types** node expands, if collapsed, and a new request-response port type is added with one default operation.</span></span>  
  
2.  <span data-ttu-id="82b0e-118">指定端口类型的名称。</span><span class="sxs-lookup"><span data-stu-id="82b0e-118">Specify a name for the port type.</span></span>  
  
3.  <span data-ttu-id="82b0e-119">定义一个或多个端口操作。</span><span class="sxs-lookup"><span data-stu-id="82b0e-119">Define one or more port operations.</span></span>  
  
     <span data-ttu-id="82b0e-120">可以命名你的端口操作，但在其选择从另一个项目，你将看到它们仅作为"请求"和"响应。</span><span class="sxs-lookup"><span data-stu-id="82b0e-120">You can name your port operations, but when you are selecting them from another project, you will see them only as "Request" and "Response."</span></span> <span data-ttu-id="82b0e-121">如果从另一个项目中选择端口操作，请验证它具有正确的消息类型。</span><span class="sxs-lookup"><span data-stu-id="82b0e-121">If you select a port operation from another project, verify that it has the correct message type.</span></span>  
  
### <a name="to-add-a-one-way-port-type"></a><span data-ttu-id="82b0e-122">若要添加单向端口类型</span><span class="sxs-lookup"><span data-stu-id="82b0e-122">To add a one-way port type</span></span>  
  
1.  <span data-ttu-id="82b0e-123">在业务流程视图窗口中，右键单击**端口类型**，然后单击**新建单向端口类型**。</span><span class="sxs-lookup"><span data-stu-id="82b0e-123">In the Orchestration View window, right-click **Port Types** and then click **New One-way Port Type**.</span></span>  
  
     <span data-ttu-id="82b0e-124">**端口类型**节点将展开，如果处于折叠状态，并新建单向端口类型添加一个带有一种默认操作。</span><span class="sxs-lookup"><span data-stu-id="82b0e-124">The **Port Types** node expands, if collapsed, and a new one-way port type is added with one default operation.</span></span>  
  
2.  <span data-ttu-id="82b0e-125">指定端口类型的名称。</span><span class="sxs-lookup"><span data-stu-id="82b0e-125">Specify a name for the port type.</span></span>  
  
3.  <span data-ttu-id="82b0e-126">定义一个或多个端口操作。</span><span class="sxs-lookup"><span data-stu-id="82b0e-126">Define one or more port operations.</span></span>  
  
### <a name="to-add-a-web-port-type"></a><span data-ttu-id="82b0e-127">若要添加 Web 端口类型</span><span class="sxs-lookup"><span data-stu-id="82b0e-127">To add a Web port type</span></span>  
  
-   <span data-ttu-id="82b0e-128">添加对包含 Web 服务的代理类的程序集的项目引用。</span><span class="sxs-lookup"><span data-stu-id="82b0e-128">Add a project reference to an assembly containing a proxy class for a Web service.</span></span> <span data-ttu-id="82b0e-129">有关详细信息，请参阅[创建 Web 端口](../core/creating-web-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="82b0e-129">For more information, see [Creating Web Ports](../core/creating-web-ports.md).</span></span>  
  
### <a name="to-remove-a-port-type"></a><span data-ttu-id="82b0e-130">若要删除的端口类型</span><span class="sxs-lookup"><span data-stu-id="82b0e-130">To remove a port type</span></span>  
  
-   <span data-ttu-id="82b0e-131">在业务流程视图窗口中，右键单击要删除，然后单击的端口类型**删除**。</span><span class="sxs-lookup"><span data-stu-id="82b0e-131">In the Orchestration View window, right-click the port type to delete, and then click **Delete**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="82b0e-132">如果端口类型正在使用中，则删除它会影响任何端口的配置为使用该的配置。</span><span class="sxs-lookup"><span data-stu-id="82b0e-132">If the port type is in use, deleting it will impact the configuration of any ports that are configured to use it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="82b0e-133">另一个业务流程中定义了项显示为只读的。</span><span class="sxs-lookup"><span data-stu-id="82b0e-133">Items that appear as read-only are defined in another orchestration.</span></span>  
  
### <a name="to-set-the-type-modifier-for-a-port-type"></a><span data-ttu-id="82b0e-134">若要设置端口类型的类型修饰符</span><span class="sxs-lookup"><span data-stu-id="82b0e-134">To set the type modifier for a port type</span></span>  
  
-   <span data-ttu-id="82b0e-135">在属性窗口中，设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="82b0e-135">In the Properties window, set the following property:</span></span>  
  
    |<span data-ttu-id="82b0e-136">属性</span><span class="sxs-lookup"><span data-stu-id="82b0e-136">Property</span></span>|<span data-ttu-id="82b0e-137">Description</span><span class="sxs-lookup"><span data-stu-id="82b0e-137">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="82b0e-138">类型修饰符</span><span class="sxs-lookup"><span data-stu-id="82b0e-138">Type Modifier</span></span>|<span data-ttu-id="82b0e-139">确定端口类型的作用域：</span><span class="sxs-lookup"><span data-stu-id="82b0e-139">Determines the scope of the port type:</span></span><br /><br /> <span data-ttu-id="82b0e-140">私有 — 对此端口类型的访问仅限于包含模块。</span><span class="sxs-lookup"><span data-stu-id="82b0e-140">Private—Access to this port type is limited to the containing module.</span></span><br /><br /> <span data-ttu-id="82b0e-141">公共 — 对此端口类型的访问没有限制。</span><span class="sxs-lookup"><span data-stu-id="82b0e-141">Public—Access to this port type is not limited.</span></span><br /><br /> <span data-ttu-id="82b0e-142">内部 — 对此端口类型的访问仅限于同一项目中的模块。</span><span class="sxs-lookup"><span data-stu-id="82b0e-142">Internal—Access to this port type is limited to modules within the same project.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="82b0e-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="82b0e-143">See Also</span></span>  
 <span data-ttu-id="82b0e-144">[通信模式](../core/communication-pattern.md) </span><span class="sxs-lookup"><span data-stu-id="82b0e-144">[Communication Pattern](../core/communication-pattern.md) </span></span>  
 <span data-ttu-id="82b0e-145">[如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="82b0e-145">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="82b0e-146">在业务流程中使用端口</span><span class="sxs-lookup"><span data-stu-id="82b0e-146">Using Ports in Orchestrations</span></span>](../core/using-ports-in-orchestrations.md)