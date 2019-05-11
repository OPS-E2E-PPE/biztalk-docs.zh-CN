---
title: 如何将参数添加到业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, parameters
ms.assetid: 35c731ed-6327-4de7-8d2e-4d14024bda77
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d68fc3491f8bdb55ad8e41a43144b0cb2f8f8cf8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387267"
---
# <a name="how-to-add-parameters-to-orchestrations"></a><span data-ttu-id="473f2-102">如何将参数添加到业务流程</span><span class="sxs-lookup"><span data-stu-id="473f2-102">How to Add Parameters to Orchestrations</span></span>
<span data-ttu-id="473f2-103">可以指定您的业务流程应在业务流程视图窗口中的参数。</span><span class="sxs-lookup"><span data-stu-id="473f2-103">You can specify what parameters your orchestration should take in the Orchestration View window.</span></span> <span data-ttu-id="473f2-104">业务流程可以将以下项作为参数：</span><span class="sxs-lookup"><span data-stu-id="473f2-104">An orchestration can take the following items as parameters:</span></span>  
  
- <span data-ttu-id="473f2-105">消息</span><span class="sxs-lookup"><span data-stu-id="473f2-105">Messages</span></span>  
  
- <span data-ttu-id="473f2-106">变量 （包括对象）</span><span class="sxs-lookup"><span data-stu-id="473f2-106">Variables (including objects)</span></span>  
  
- <span data-ttu-id="473f2-107">相关集</span><span class="sxs-lookup"><span data-stu-id="473f2-107">Correlation sets</span></span>  
  
- <span data-ttu-id="473f2-108">角色链接</span><span class="sxs-lookup"><span data-stu-id="473f2-108">Role links</span></span>  
  
- <span data-ttu-id="473f2-109">端口</span><span class="sxs-lookup"><span data-stu-id="473f2-109">Ports</span></span>  
  
  <span data-ttu-id="473f2-110">可以作为 in 参数或 out 参数的业务流程之间传递参数。</span><span class="sxs-lookup"><span data-stu-id="473f2-110">Parameters can be passed between orchestrations as in parameters or out parameters.</span></span> <span data-ttu-id="473f2-111">在参数可以传递按值或按引用。</span><span class="sxs-lookup"><span data-stu-id="473f2-111">In parameters can be passed by value or by reference.</span></span> <span data-ttu-id="473f2-112">Out 参数可以仅通过引用传递。</span><span class="sxs-lookup"><span data-stu-id="473f2-112">Out parameters can only be passed by reference.</span></span> <span data-ttu-id="473f2-113">参数可以包括变量、 消息、 相关集、 角色链接和端口。</span><span class="sxs-lookup"><span data-stu-id="473f2-113">Parameters can include variables, messages, correlation sets, role links, and ports.</span></span>  
  
### <a name="to-set-orchestration-parameters"></a><span data-ttu-id="473f2-114">若要设置业务流程参数</span><span class="sxs-lookup"><span data-stu-id="473f2-114">To set orchestration parameters</span></span>  
  
1.  <span data-ttu-id="473f2-115">在业务流程视图窗口中，使用**业务流程参数**文件夹添加变量、 消息和端口。</span><span class="sxs-lookup"><span data-stu-id="473f2-115">In the Orchestration View window, use the **Orchestration Parameters** folder to add variables, messages, and ports.</span></span>  
  
2.  <span data-ttu-id="473f2-116">每个项添加到**业务流程参数**文件夹中，使用属性窗口来指定**方向**属性：</span><span class="sxs-lookup"><span data-stu-id="473f2-116">For each item added to the **Orchestration Parameters** folder, use the Properties window to specify the **Direction** property:</span></span>  
  
    -   <span data-ttu-id="473f2-117">在中，通过值传入的参数。</span><span class="sxs-lookup"><span data-stu-id="473f2-117">In—A parameter passed in by value.</span></span>  
  
    -   <span data-ttu-id="473f2-118">Ref-通过引用传入的参数。</span><span class="sxs-lookup"><span data-stu-id="473f2-118">Ref—A parameter passed in by reference.</span></span>  
  
    -   <span data-ttu-id="473f2-119">Out-，通过引用传递的参数。</span><span class="sxs-lookup"><span data-stu-id="473f2-119">Out—A parameter passed out by reference.</span></span>  
  
### <a name="to-add-a-parameter-to-an-orchestration"></a><span data-ttu-id="473f2-120">若要向业务流程添加参数</span><span class="sxs-lookup"><span data-stu-id="473f2-120">To add a parameter to an orchestration</span></span>  
  
1. <span data-ttu-id="473f2-121">在业务流程视图窗口中，右键单击**业务流程参数**文件夹，再单击所需的参数的种类。</span><span class="sxs-lookup"><span data-stu-id="473f2-121">In the Orchestration View window, right-click the **Orchestration Parameters** folder and then click the kind of parameter you want.</span></span>  
  
2. <span data-ttu-id="473f2-122">有关配置的端口和角色链接，使用向导来配置参数。</span><span class="sxs-lookup"><span data-stu-id="473f2-122">For configured ports and role links, use the wizard to configure the parameter.</span></span>  
  
    <span data-ttu-id="473f2-123">-或-</span><span class="sxs-lookup"><span data-stu-id="473f2-123">—Or—</span></span>  
  
    <span data-ttu-id="473f2-124">对于其他参数类型，使用属性页来配置参数。</span><span class="sxs-lookup"><span data-stu-id="473f2-124">For other parameter types, use the properties page to configure the parameter.</span></span>  
  
   <span data-ttu-id="473f2-125">**参数类型**</span><span class="sxs-lookup"><span data-stu-id="473f2-125">**Parameter types**</span></span>  
  
   <span data-ttu-id="473f2-126">参数可以作为引用参数传递的值，或作为 out 参数。</span><span class="sxs-lookup"><span data-stu-id="473f2-126">Parameters can be passed by value, as reference parameters, and as out parameters.</span></span> <span data-ttu-id="473f2-127">当一个参数通过值传递到业务流程时，创建并业务流程使用的数据的副本。</span><span class="sxs-lookup"><span data-stu-id="473f2-127">When a parameter is passed by value to an orchestration, a copy of the data is made and used by the orchestration.</span></span>  
  
   <span data-ttu-id="473f2-128">当您使用引用参数时，会不创建任何副本。</span><span class="sxs-lookup"><span data-stu-id="473f2-128">When you use a reference parameter, no copy is made.</span></span> <span data-ttu-id="473f2-129">调用程序和业务流程，之间共享的内存位置包含的数据和业务流程可以修改此内存位置的内容。</span><span class="sxs-lookup"><span data-stu-id="473f2-129">The memory location that contains the data is shared between the calling program and the orchestration, and the contents of this memory location can be modified by the orchestration.</span></span> <span data-ttu-id="473f2-130">这种修改意味着不仅在业务流程，而且还调用程序中，更改参数的值。</span><span class="sxs-lookup"><span data-stu-id="473f2-130">Such a modification means that the value of the parameter is changed not only in the orchestration, but also in the calling program.</span></span>  
  
   <span data-ttu-id="473f2-131">Out 参数类似于引用参数，但业务流程不能假定它包含有效的数据时传入;而是调用程序则要求业务流程，以将值分配给此参数。</span><span class="sxs-lookup"><span data-stu-id="473f2-131">An out parameter is similar to a reference parameter, but the orchestration cannot assume that it contains valid data when passed in; rather, the calling program expects the orchestration to assign a value to this parameter.</span></span>  
  
   <span data-ttu-id="473f2-132">**业务流程参数的规则**</span><span class="sxs-lookup"><span data-stu-id="473f2-132">**Rules for orchestration parameters**</span></span>  
  
-   <span data-ttu-id="473f2-133">可以传递唯一消息和变量 （包括对象） 作为 out 或引用参数。</span><span class="sxs-lookup"><span data-stu-id="473f2-133">You can pass only messages and variables (including objects) as out or reference parameters.</span></span>  
  
-   <span data-ttu-id="473f2-134">不能传出或引用参数中的业务流程**启动业务流程**形状。</span><span class="sxs-lookup"><span data-stu-id="473f2-134">You cannot pass out or reference parameters to an orchestration in a **Start Orchestration** shape.</span></span>  
  
-   <span data-ttu-id="473f2-135">在参数中，包括任何角色链接和动态端口，必须明确赋值前被传递到业务流程。</span><span class="sxs-lookup"><span data-stu-id="473f2-135">In parameters, including any role links and dynamic ports, must be definitely assigned before being passed to an orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="473f2-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="473f2-136">See Also</span></span>  
 <span data-ttu-id="473f2-137">[业务流程形状](../core/orchestration-shapes.md) </span><span class="sxs-lookup"><span data-stu-id="473f2-137">[Orchestration Shapes](../core/orchestration-shapes.md) </span></span>  
 <span data-ttu-id="473f2-138">[如何向业务流程添加形状](../core/how-to-add-shapes-to-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="473f2-138">[How to Add Shapes to Orchestrations](../core/how-to-add-shapes-to-orchestrations.md) </span></span>  
 [<span data-ttu-id="473f2-139">如何使用选择项目类型对话框</span><span class="sxs-lookup"><span data-stu-id="473f2-139">How to Use the Select Artifact Type Dialog Box</span></span>](../core/how-to-use-the-select-artifact-type-dialog-box.md)