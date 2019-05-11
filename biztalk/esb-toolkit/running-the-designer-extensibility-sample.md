---
title: 运行设计器扩展性示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 05ac3b50-5bf2-4566-8654-472391476d1f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdfaf1ca75d480e219b0c99fb903b1997859a18f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292493"
---
# <a name="running-the-designer-extensibility-sample"></a><span data-ttu-id="d058b-102">运行设计器扩展性示例</span><span class="sxs-lookup"><span data-stu-id="d058b-102">Running the Designer Extensibility Sample</span></span>
<span data-ttu-id="d058b-103">设计器扩展性示例使用两个示例扩展程序来演示如何为自定义冲突解决程序和路线服务提供设计时配置选项。</span><span class="sxs-lookup"><span data-stu-id="d058b-103">The Designer Extensibility sample uses two sample extenders to demonstrate how you can provide design-time configuration options for custom resolvers and for itinerary services.</span></span>  
  
 <span data-ttu-id="d058b-104">**若要运行设计器扩展性示例**</span><span class="sxs-lookup"><span data-stu-id="d058b-104">**To run the Designer Extensibility sample**</span></span>  
  
1.  <span data-ttu-id="d058b-105">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="d058b-105">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="d058b-106">在 Visual Studio 中，指向**新建**上**文件**菜单，并单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="d058b-106">In Visual Studio, point to **New** on the **File** menu, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="d058b-107">选择C#类库模板中，键入**ItineraryLibrary**中**名称**框中，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="d058b-107">Select the C# Class Library template, type **ItineraryLibrary** in the **Name** box, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="d058b-108">在解决方案资源管理器，右键单击 ItineraryLibrary 项目，指向**外**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="d058b-108">In Solution Explorer, right-click the ItineraryLibrary project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
5.  <span data-ttu-id="d058b-109">在中**名称**框中，键入**TestItinerary**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="d058b-109">In the **Name** box, type **TestItinerary**, and then press ENTER.</span></span>  
  
6.  <span data-ttu-id="d058b-110">在工具箱中，单击 On 接入点模型元素，并将它拖动到设计图面。</span><span class="sxs-lookup"><span data-stu-id="d058b-110">In the Toolbox, click an On-Ramp model element, and then drag it to the design surface.</span></span>  
  
7.  <span data-ttu-id="d058b-111">在工具箱中，单击路线服务模型元素，并将它拖动到设计图面。</span><span class="sxs-lookup"><span data-stu-id="d058b-111">In the Toolbox, click an Itinerary Service model element, and then drag it to the design surface.</span></span>  
  
8.  <span data-ttu-id="d058b-112">在工具箱中，单击另一个路线服务模型元素，并将它拖动到设计图面。</span><span class="sxs-lookup"><span data-stu-id="d058b-112">In the Toolbox, click another Itinerary Service model element, and then drag it to the design surface.</span></span>  
  
9. <span data-ttu-id="d058b-113">在工具箱中，单击 Off 接入点模型元素，并将它拖动到设计图面。</span><span class="sxs-lookup"><span data-stu-id="d058b-113">In the Toolbox, click an Off-Ramp model element, and then drag it to the design surface.</span></span>  
  
10. <span data-ttu-id="d058b-114">在工具箱中，单击连接器工具，然后拖动之间的连接**OnRamp1**模型元素和**ItineraryService1**模型元素。</span><span class="sxs-lookup"><span data-stu-id="d058b-114">In the Toolbox, click the Connector tool, and then drag a connection between the **OnRamp1** model element and the **ItineraryService1** model element.</span></span>  
  
11. <span data-ttu-id="d058b-115">在工具箱中，单击连接器工具，然后拖动之间的连接**ItineraryService1**模型元素和**ItineraryService2**模型元素。</span><span class="sxs-lookup"><span data-stu-id="d058b-115">In the Toolbox, click the Connector tool, and then drag a connection between the **ItineraryService1** model element and the **ItineraryService2** model element.</span></span>  
  
12. <span data-ttu-id="d058b-116">在工具箱中，单击连接器工具，然后拖动之间的连接**ItineraryService2**模型元素和**OffRamp1**模型元素。</span><span class="sxs-lookup"><span data-stu-id="d058b-116">In the Toolbox, click the Connector tool, and then drag a connection between the **ItineraryService2** model element and the **OffRamp1** model element.</span></span>  
  
13. <span data-ttu-id="d058b-117">单击**OnRamp1**模型元素，，然后在属性窗口中，将扩展程序属性设置为**接入点 ESB 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="d058b-117">Click the **OnRamp1** model element, and then in the Properties window, set the Extender property to **On-Ramp ESB Service Extension**.</span></span>  
  
14. <span data-ttu-id="d058b-118">设置**BizTalk 应用程序**属性设置为**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="d058b-118">Set the **BizTalk Application** property to **Microsoft.Practices.ESB**.</span></span>  
  
15. <span data-ttu-id="d058b-119">设置**接收端口**属性设置为**OnRamp.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="d058b-119">Set the **Receive Port** property to **OnRamp.Itinerary**.</span></span>  
  
16. <span data-ttu-id="d058b-120">单击**ItinearyService1**模型元素，并在属性窗口中设置**Extender**属性设置为**示例业务流程路线服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="d058b-120">Click the **ItinearyService1** model element, and then in the Properties window, set the **Extender** property to **Sample Orchestration Itinerary Service Extension**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d058b-121">这是设计器扩展性示例的一部分安装的自定义扩展。</span><span class="sxs-lookup"><span data-stu-id="d058b-121">This is the custom extension installed as part of the Designer Extensibility sample.</span></span> <span data-ttu-id="d058b-122">它允许您将属性添加到传递给业务流程基于路线服务的属性包。</span><span class="sxs-lookup"><span data-stu-id="d058b-122">It allows you to add properties to the property bag passed to an orchestration-based itinerary service.</span></span>  
  
17. <span data-ttu-id="d058b-123">设置**OtherValue**属性设置为**1**。</span><span class="sxs-lookup"><span data-stu-id="d058b-123">Set the **OtherValue** property to **1**.</span></span>  
  
18. <span data-ttu-id="d058b-124">设置**ServiceName**属性设置为**Microsoft.Practices.ESB.Services.Routing**。</span><span class="sxs-lookup"><span data-stu-id="d058b-124">Set the **ServiceName** property to **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
19. <span data-ttu-id="d058b-125">设置**SomeValue**属性设置为**2**。</span><span class="sxs-lookup"><span data-stu-id="d058b-125">Set the **SomeValue** property to **2**.</span></span>  
  
20. <span data-ttu-id="d058b-126">右键单击**冲突解决程序**系列**ItineraryService1**，然后单击**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="d058b-126">Right-click the **Resolver** collection of **ItineraryService1**, and then click **Add new Resolver**.</span></span>  
  
21. <span data-ttu-id="d058b-127">单击**Resolver1**，然后在属性窗口中设置**解析程序实现**属性设置为**解析程序扩展插件示例**。</span><span class="sxs-lookup"><span data-stu-id="d058b-127">Click **Resolver1**, and then in the Properties window, set the **Resolver Implementation** property to **Sample Resolver Extension**.</span></span>  
  
22. <span data-ttu-id="d058b-128">设置**SomeResolverValue**属性设置为**测试**，然后将版本属性设置为**1.0**。</span><span class="sxs-lookup"><span data-stu-id="d058b-128">Set the **SomeResolverValue** property to **test**, and then set the version property to **1.0**.</span></span>  
  
23. <span data-ttu-id="d058b-129">单击**ItineraryService2**模型元素，并在属性窗口中设置**路线服务扩展器**属性设置为**关闭接入点路线服务扩展**.</span><span class="sxs-lookup"><span data-stu-id="d058b-129">Click the **ItineraryService2** model element, and then in the Properties window, set the **Itinerary Service Extender** property to **Off-Ramp Itinerary Service Extension**.</span></span>  
  
24. <span data-ttu-id="d058b-130">设置**关闭负载增加**属性设置为**OffRamp1 > 发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="d058b-130">Set the **Off-Ramp** property to **OffRamp1 > Send Handlers**.</span></span>  
  
25. <span data-ttu-id="d058b-131">单击**OffRamp1**模型元素，并在属性窗口中设置**Extender**属性设置为**关闭负载增加 ESB 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="d058b-131">Click the **OffRamp1** model element, and then in the Properties window, set the **Extender** property to **Off-Ramp ESB Service Extension**.</span></span>  
  
26. <span data-ttu-id="d058b-132">设置**BizTalk 应用程序**属性设置为**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="d058b-132">Set the **BizTalk Application** property to **GlobalBank.ESB**.</span></span>  
  
27. <span data-ttu-id="d058b-133">设置**发送端口**属性设置为**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="d058b-133">Set the **Send Port** property to **DynamicResolutionOneWay**.</span></span>  
  
28. <span data-ttu-id="d058b-134">右键单击设计图面上，然后依次**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="d058b-134">Right-click the design surface, and then click **Export Model**.</span></span>  
  
29. <span data-ttu-id="d058b-135">检查生成的 XML。</span><span class="sxs-lookup"><span data-stu-id="d058b-135">Examine the generated XML.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d058b-136">请注意**PropertyBag**元素和它包含的属性。</span><span class="sxs-lookup"><span data-stu-id="d058b-136">Notice the **PropertyBag** element and the properties it contains.</span></span> <span data-ttu-id="d058b-137">此外请注意示例冲突解决程序连接字符串和配置方式基于输入的属性。</span><span class="sxs-lookup"><span data-stu-id="d058b-137">Also notice the Sample resolver connection string and how it was configured based on the properties entered.</span></span>