---
title: "如何使用端口类型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e3b4307cb9d48679ae1b90f7e02dd0288ec2957
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-work-with-port-types"></a><span data-ttu-id="5e50f-102">如何使用端口类型</span><span class="sxs-lookup"><span data-stu-id="5e50f-102">How to Work with Port Types</span></span>
<span data-ttu-id="5e50f-103">端口类型由通信模式、一组操作（请求或响应）和这些操作可处理的消息类型组成。</span><span class="sxs-lookup"><span data-stu-id="5e50f-103">A port type consists of a communication pattern, a set of operations (requests or responses), and the message types that those operations can work on.</span></span> <span data-ttu-id="5e50f-104">通信模式可以为单向通信或请求响应（双向）通信，在该端口类型上定义的所有操作都必须使用相同的模式。</span><span class="sxs-lookup"><span data-stu-id="5e50f-104">The pattern can be either one-way or request-response (two-way), and all operations defined on that port type must use the same pattern.</span></span> <span data-ttu-id="5e50f-105">请注意，端口类型与方向无关：方向是在各端口上指定的。</span><span class="sxs-lookup"><span data-stu-id="5e50f-105">Note that port types are direction-agnostic: direction is specified on individual ports.</span></span>  
  
 <span data-ttu-id="5e50f-106">端口类型的作用域定义通过**类型修饰符**属性。</span><span class="sxs-lookup"><span data-stu-id="5e50f-106">The scope of a port type is defined by the **Type Modifier** property.</span></span> <span data-ttu-id="5e50f-107">端口类型可以为公有、私有或内部。</span><span class="sxs-lookup"><span data-stu-id="5e50f-107">A port type can be public, private, or internal.</span></span> <span data-ttu-id="5e50f-108">如果端口类型为公有，则该端口类型对于与业务流程交互的所有用户均可见。</span><span class="sxs-lookup"><span data-stu-id="5e50f-108">If it is public, it is visible to anyone interacting with the orchestration.</span></span> <span data-ttu-id="5e50f-109">如果端口类型为私有，则该端口类型只对在同一个项目和命名空间中的其他业务流程可见。</span><span class="sxs-lookup"><span data-stu-id="5e50f-109">If it is private, it is visible to other orchestrations within the same project and namespace.</span></span> <span data-ttu-id="5e50f-110">如果端口类型为内部，则该端口类型只在项目内可见。</span><span class="sxs-lookup"><span data-stu-id="5e50f-110">If it is internal, the port type is visible only within the project.</span></span> <span data-ttu-id="5e50f-111">由于端口类型定义包括消息类型，因此消息类型作用域必须包含使用该消息类型的所有端口类型的作用域。</span><span class="sxs-lookup"><span data-stu-id="5e50f-111">Since a port type definition includes message types, the scope of the message type must encompass that of any port type that uses it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e50f-112">端口类型可应用到的端口数不限。</span><span class="sxs-lookup"><span data-stu-id="5e50f-112">A port type can be applied to any number of ports.</span></span> <span data-ttu-id="5e50f-113">您可以将端口视为端口类型的实例。</span><span class="sxs-lookup"><span data-stu-id="5e50f-113">You can think of a port as an instance of a port type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e50f-114">端口类型本身并没有通信方向，您只能对各个端口设置方向。</span><span class="sxs-lookup"><span data-stu-id="5e50f-114">A port type does not inherently have a communication direction; you set direction on individual ports.</span></span>  
  
### <a name="to-add-a-request-response-port-type"></a><span data-ttu-id="5e50f-115">添加请求响应端口类型</span><span class="sxs-lookup"><span data-stu-id="5e50f-115">To add a request-response port type</span></span>  
  
1.  <span data-ttu-id="5e50f-116">在业务流程视图窗口中，右键单击**端口类型**，然后单击**新建请求-响应端口类型**。</span><span class="sxs-lookup"><span data-stu-id="5e50f-116">In the Orchestration View window, right-click **Port Types** and then click **New Request-response Port Type**.</span></span>  
  
     <span data-ttu-id="5e50f-117">**端口类型**节点会展开，如果折叠状态，且与一个默认操作增加了新的请求-响应端口类型。</span><span class="sxs-lookup"><span data-stu-id="5e50f-117">The **Port Types** node expands, if collapsed, and a new request-response port type is added with one default operation.</span></span>  
  
2.  <span data-ttu-id="5e50f-118">指定端口类型的名称。</span><span class="sxs-lookup"><span data-stu-id="5e50f-118">Specify a name for the port type.</span></span>  
  
3.  <span data-ttu-id="5e50f-119">定义一个或多个端口操作。</span><span class="sxs-lookup"><span data-stu-id="5e50f-119">Define one or more port operations.</span></span>  
  
     <span data-ttu-id="5e50f-120">您可以对端口操作进行命名，但是当从其他项目选择这些端口操作时，这些端口操作只显示为“请求”和“响应”。</span><span class="sxs-lookup"><span data-stu-id="5e50f-120">You can name your port operations, but when you are selecting them from another project, you will see them only as "Request" and "Response."</span></span> <span data-ttu-id="5e50f-121">如果从其他项目选择端口操作，请验证该端口操作具有正确的消息类型。</span><span class="sxs-lookup"><span data-stu-id="5e50f-121">If you select a port operation from another project, verify that it has the correct message type.</span></span>  
  
### <a name="to-add-a-one-way-port-type"></a><span data-ttu-id="5e50f-122">添加单向端口类型</span><span class="sxs-lookup"><span data-stu-id="5e50f-122">To add a one-way port type</span></span>  
  
1.  <span data-ttu-id="5e50f-123">在业务流程视图窗口中，右键单击**端口类型**，然后单击**新单向端口类型**。</span><span class="sxs-lookup"><span data-stu-id="5e50f-123">In the Orchestration View window, right-click **Port Types** and then click **New One-way Port Type**.</span></span>  
  
     <span data-ttu-id="5e50f-124">**端口类型**节点会展开，如果折叠状态，且与一个默认操作增加了新的单向端口类型。</span><span class="sxs-lookup"><span data-stu-id="5e50f-124">The **Port Types** node expands, if collapsed, and a new one-way port type is added with one default operation.</span></span>  
  
2.  <span data-ttu-id="5e50f-125">指定端口类型的名称。</span><span class="sxs-lookup"><span data-stu-id="5e50f-125">Specify a name for the port type.</span></span>  
  
3.  <span data-ttu-id="5e50f-126">定义一个或多个端口操作。</span><span class="sxs-lookup"><span data-stu-id="5e50f-126">Define one or more port operations.</span></span>  
  
### <a name="to-add-a-web-port-type"></a><span data-ttu-id="5e50f-127">添加 Web 端口类型</span><span class="sxs-lookup"><span data-stu-id="5e50f-127">To add a Web port type</span></span>  
  
-   <span data-ttu-id="5e50f-128">添加对包含 Web Services 代理类的程序集的项目引用。</span><span class="sxs-lookup"><span data-stu-id="5e50f-128">Add a project reference to an assembly containing a proxy class for a Web service.</span></span> <span data-ttu-id="5e50f-129">有关详细信息，请参阅[创建 Web 端口](../core/creating-web-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="5e50f-129">For more information, see [Creating Web Ports](../core/creating-web-ports.md).</span></span>  
  
### <a name="to-remove-a-port-type"></a><span data-ttu-id="5e50f-130">删除端口类型</span><span class="sxs-lookup"><span data-stu-id="5e50f-130">To remove a port type</span></span>  
  
-   <span data-ttu-id="5e50f-131">在业务流程视图窗口中，右键单击要删除，并依次的端口类型**删除**。</span><span class="sxs-lookup"><span data-stu-id="5e50f-131">In the Orchestration View window, right-click the port type to delete, and then click **Delete**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5e50f-132">如果该端口类型正在使用，则删除该端口类型将会影响配置为使用该端口类型的所有端口的配置。</span><span class="sxs-lookup"><span data-stu-id="5e50f-132">If the port type is in use, deleting it will impact the configuration of any ports that are configured to use it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5e50f-133">显示为只读的项目将在其他业务流程中定义。</span><span class="sxs-lookup"><span data-stu-id="5e50f-133">Items that appear as read-only are defined in another orchestration.</span></span>  
  
### <a name="to-set-the-type-modifier-for-a-port-type"></a><span data-ttu-id="5e50f-134">设置端口类型的类型修饰符</span><span class="sxs-lookup"><span data-stu-id="5e50f-134">To set the type modifier for a port type</span></span>  
  
-   <span data-ttu-id="5e50f-135">在“属性”窗口中，设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="5e50f-135">In the Properties window, set the following property:</span></span>  
  
    |<span data-ttu-id="5e50f-136">属性</span><span class="sxs-lookup"><span data-stu-id="5e50f-136">Property</span></span>|<span data-ttu-id="5e50f-137">Description</span><span class="sxs-lookup"><span data-stu-id="5e50f-137">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="5e50f-138">类型修饰符</span><span class="sxs-lookup"><span data-stu-id="5e50f-138">Type Modifier</span></span>|<span data-ttu-id="5e50f-139">确定端口类型的作用域：</span><span class="sxs-lookup"><span data-stu-id="5e50f-139">Determines the scope of the port type:</span></span><br /><br /> <span data-ttu-id="5e50f-140">私有-为此端口类型的访问仅限于包含模块。</span><span class="sxs-lookup"><span data-stu-id="5e50f-140">Private—Access to this port type is limited to the containing module.</span></span><br /><br /> <span data-ttu-id="5e50f-141">公共-访问此端口类型不受限制。</span><span class="sxs-lookup"><span data-stu-id="5e50f-141">Public—Access to this port type is not limited.</span></span><br /><br /> <span data-ttu-id="5e50f-142">内部 — 为此端口类型的访问仅限于同一项目中的模块。</span><span class="sxs-lookup"><span data-stu-id="5e50f-142">Internal—Access to this port type is limited to modules within the same project.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5e50f-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e50f-143">See Also</span></span>  
 <span data-ttu-id="5e50f-144">[通信模式](../core/communication-pattern.md) </span><span class="sxs-lookup"><span data-stu-id="5e50f-144">[Communication Pattern](../core/communication-pattern.md) </span></span>  
 <span data-ttu-id="5e50f-145">[如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="5e50f-145">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="5e50f-146">使用在业务流程中的端口</span><span class="sxs-lookup"><span data-stu-id="5e50f-146">Using Ports in Orchestrations</span></span>](../core/using-ports-in-orchestrations.md)