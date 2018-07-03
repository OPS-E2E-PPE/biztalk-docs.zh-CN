---
title: 关于路线 |Microsoft Docs
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
ms.openlocfilehash: ddd41dcfc1c5b6a090d48411956b19986aa2d676
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001086"
---
# <a name="about-itineraries"></a>关于路线
路线是执行的处理指令基于序列的 ESB 中介策略的表示形式[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]可扩展格式。 路线可以视为一种高级中介语言，用于描述的声明性的路线服务的配置通过与中介组件关联的序列[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]核心引擎。 您可以设计中介流来描述应如何处理消息，并可以组织为 visual 的绘图的整个流。 在运行时，[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]核心引擎执行路线设计器生成的路线。  
  
## <a name="the-itinerary-designer-surface"></a>路线设计器图面  
 路线设计器图面是用于创建可视化设计器[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线并将这些路线导出为运行时间格式。 图 1 中所示，它是到可拖动的项从工具箱中，一个画布。  
  
 ![路线设计器](../esb-toolkit/media/ch5-itinerarydesigner.gif "Ch5-ItineraryDesigner")  
  
 **图 1**  
  
 **路线设计器图面**  
  
 路线设计器和 Microsoft Visual Studio 标题栏中的顶级选项卡上显示路线的名称。 在设计图面本身是单个区域，包含描述路线的实际消息流的模型元素。 ItineraryDSL 可以修改模型元素属性使用 Visual Studio 属性窗口。  
  
## <a name="itinerary-designer-toolbox"></a>路线设计器工具箱  
 Visual Studio 工具箱包含选项卡，表示工具集。 当您打开使用路线设计器的 Visual Studio 项目时，该工具箱中包含两个选项卡：**常规**选项卡和**ItineraryDsl**选项卡。 **ItineraryDsl**选项卡包含以下工具：  
  
-   **路线服务工具**。 此模型元素对应于路线中介服务，表示处理指令。  
  
-   **连接器工具**。 此模型元素定义路线设计器图面上的各个模型元素之间的关系。  
  
-   **关闭负载增加工具**。 此模型元素对应于关闭接入点发送一条消息。 路线设计器允许多个接出点每个模型。  
  
-   **接入点工具**。 此模型元素对应于入口接收消息。 路线设计器，只有一个的途径，每个模型。  
  
-   **路线 Broker 服务工具**。 此模型元素对应于路线中介服务，允许具有多个输入和多个输出定义的消息流。  
  
-   **路线 Broker 输出端口**。 此模型元素对应于路线 Broker 服务的单个输出端口。 路线 Broker 服务模型元素允许多个输出端口。  
  
## <a name="steps-in-itinerary-development"></a>路线开发中的步骤  
 若要开发路线，它表示 ESB 中介流，通常应执行以下操作：  
  
- 添加模型元素来表示的消息处理您的路线的步骤。 路线设计器提供了一个包含用来表示不同的操作或关键抽象形状的工具箱。  
  
- 指定路线模型属性，其中包括 Microsoft BizTalk Server 管理数据库和模型导出程序配置的连接字符串。  
  
- 绑定的途径，并关闭负载增加的模型元素到物理 BizTalk 接收位置和发送端口通过将这些模型元素与相应技术扩展器相关联。  
  
- 使用扩展器将路线服务模型元素和定义所需的扩展程序的特定于技术的属性。 为特定类型的扩展程序; 这些属性可能会有所不同它们可以表示路线的中介服务属性和与运行时组件和项目相关联的特定于 BizTalk 的属性。  
  
- 识别你可能想要作为路线中介服务引用的自定义组件。 例如，可以开发业务流程作为路线服务。  
  
- 验证针对冲突解决程序模型元素设置[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]通过调用从设计器图面解析程序服务的运行时配置。  
  
- 验证并导出路线使用导出程序的运行时策略。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]使用路线设计器提供两个导出程序： 文件导出程序和数据库导出程序。 或者，您可以实现自定义导出程序。  
  
- 测试使用测试客户端应用程序或 BizUnit framework 你路线。  
  
## <a name="security-considerations-for-developing-itineraries"></a>有关开发路线的安全注意事项  
 在设计路线时，应考虑潜在的安全问题：  
  
-   避免指定用户凭据，而无需使用提供的模型属性的证书。  
  
-   并不指 BizTalk 接收端口与接收允许匿名访问的位置。  
  
-   如果路线消息中包含敏感数据，保护的消息或传输通道。  
  
-   如果消息包含必须在传输过程中受到保护的敏感数据，保护与管道组件在消息框中的消息。