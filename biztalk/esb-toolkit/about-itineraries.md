---
title: 有关路线 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d34632f-8652-49dd-97b7-2513aacc1bd7
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66a9a759a6afdd55c3c1646d02c480aa193261aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290605"
---
# <a name="about-itineraries"></a>有关路线
一条路线是的表示形式执行的处理指令基于序列的 ESB 中介策略[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]可扩展格式。 一条路线可被视为描述一系列由配置是与中介组件关联的声明性路线服务的高级中介语言[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]核心引擎。 你可以设计中介流来描述应如何处理消息，而且您可以组织 visual 绘制整个流中。 在运行时，[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]核心引擎执行路线设计器生成的路线。  
  
## <a name="the-itinerary-designer-surface"></a>路线设计器图面  
 路线设计器图面是可视化设计器中用于创建[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线并将这些路线导出到运行时间格式。 它是指可拖动的项从工具箱中，一个画布，如图 1 中所示。  
  
 ![路线设计器](../esb-toolkit/media/ch5-itinerarydesigner.gif "Ch5 ItineraryDesigner")  
  
 **图 1**  
  
 **路线设计器图面**  
  
 路线的名称显示在路线设计器和 Microsoft Visual Studio 标题栏中，顶部选项卡。 设计图面本身是单个区域，包含描述的路线实际的消息流的模型元素。 ItineraryDSL 使您可以修改使用 Visual Studio 属性窗口的模型元素属性。  
  
## <a name="itinerary-designer-toolbox"></a>路线设计器工具箱  
 Visual Studio 工具箱中包含表示的工具集的选项卡。 当你打开使用路线设计器的 Visual Studio 项目时，该工具箱中包含两个选项卡：**常规**选项卡和**ItineraryDsl**选项卡。 **ItineraryDsl**选项卡包含以下工具：  
  
-   **路线服务工具**。 此模型元素对应于路线中介服务，而表示一条处理指令。  
  
-   **连接器工具**。 此模型元素定义在路线设计器图面上的单个模型元素之间的关系。  
  
-   **关闭负载增加工具**。 此模型元素对应于出口发送消息。 路线设计器允许多个关闭的渐变每个模型。  
  
-   **在负载增加工具**。 此模型元素对应于入口接收消息。 路线设计器，只有一个上的负载增加每个模型。  
  
-   **路线 Broker 服务工具**。 此模型元素对应于路线中介服务，允许具有多个输入和多个输出的定义的消息流。  
  
-   **路线 Broker 输出端口**。 此模型元素对应于路线 Broker 服务的单个输出端口。 路线 Broker 服务模型元素允许多个输出端口。  
  
## <a name="steps-in-itinerary-development"></a>路线开发中的步骤  
 若要开发路线，它表示 ESB 中介流，通常应执行以下操作：  
  
-   添加模型元素来表示的消息处理您的路线的步骤。 路线设计器提供包含用来表示不同的操作或关键抽象形状的工具箱。  
  
-   指定路线模型属性，其中包括 Microsoft BizTalk Server 管理数据库和模型导出程序配置的连接字符串。  
  
-   绑定入口和出口模型元素到物理 BizTalk 接收位置和发送端口通过使用相应技术扩展器将这些模型元素相关联。  
  
-   扩展程序相关联路线服务模型元素和定义所需的扩展程序的特定于技术的属性。 为特定类型的扩展程序; 这些属性可能会有所不同它们可以表示路线中介服务属性和其运行时组件和项目与关联的 BizTalk 特定属性。  
  
-   标识你可能想要作为路线中介服务引用的自定义组件。 例如，你可以开发作为路线服务业务流程。  
  
-   验证冲突解决程序针对的模型元素设置[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]通过调用设计器图面中的解析程序服务的运行时配置。  
  
-   验证和导出路线使用导出程序的运行时策略。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]与路线设计器提供两个导出程序： 文件导出程序和数据库导出程序。 或者，你可以实现自定义的导出程序。  
  
-   测试使用测试客户端应用程序或 BizUnit framework 你路线。  
  
## <a name="security-considerations-for-developing-itineraries"></a>有关开发路线的安全注意事项  
 当您设计路线时，应考虑潜在的安全问题：  
  
-   避免在不使用来自模型属性的证书的情况下指定用户凭据。  
  
-   不引用 BizTalk 接收端口与接收允许匿名访问的位置。  
  
-   如果路线消息包含敏感数据，请保护消息或传输通道。  
  
-   如果消息包含需要在传输过程中保护的敏感数据，请保护带管道组件的消息框中的消息。