---
title: "如何： 动态路由根据消息上下文使用业务规则策略消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d3b68de-6b24-46fe-ae0d-91afb630bc19
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0d36df10b271d83b1e77f4d7f57d357f4b22033
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-dynamically-route-a-message-based-on-message-context-using-a-business-rules-policy"></a>如何： 动态路由基于消息上下文使用业务规则策略在一条消息
## <a name="goal"></a>目的  
 本部分演示如何创建一条路线，并将确定消息终结点，根据消息上下文属性，使用 BizTalk Server 业务规则引擎 (BRE) 策略，然后将路由使用 BizTalk Server 文件适配器的消息。  
  
 在本操作方法主题中，你将完成以下步骤：  
  
-   创建业务规则策略来评估消息类型。  
  
-   创建动态路由使用业务规则策略路线路由滑动。  
  
-   测试路线使用路线测试客户端示例应用程序。  
  
## <a name="prerequisites"></a>先决条件  
 此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。  
  
## <a name="steps"></a>步骤  
 **若要创建使用消息上下文属性将消息路由 BRE 策略**  
  
1.  单击**启动**在任务栏中，指向**所有程序**，指向**BizTalk Server**，然后单击**业务规则编辑器**。  
  
2.  在策略资源管理器中，右键单击**策略**，然后单击**添加新策略**。 命名策略时**RouteBasedOnMessageType**。  
  
 **若要添加的北美订单的路由规则**  
  
1.  在**RouteBasedOnMessageType**策略，右键单击**（不保存） 1.0 版**，然后单击**添加新规则**。 命名规则**SetNAOrderEndpoint**。  
  
2.  在规则窗口中，右键单击**条件**，指向**谓词**，然后单击**相等**。  
  
3.  在事实数据资源管理器中，展开**ESB。ContextInfo**词汇，展开**版本 1.0**，然后拖动**上下文消息类型**事实**argument1**节点下的**条件**。  
  
    > [!NOTE]
    >  [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括可用于创建规则的多个词汇。 其中一些应替换或扩充自己词汇。 例如， **DynamicRunTimeMaptypes**策略拥有中提供的映射用于定义**GlobalBank**示例。  
  
4.  单击**argument2**节点，并键入**http://globalbank.esb.dynamicresolution.com/northamericanservices/#OrderDoc**  
  
5.  在事实数据资源管理器中，展开**ESB。EndPointInfo**词汇，展开**版本 1.0**，然后拖动**设置终结点出站传输位置**定义与**操作**。  
  
6.  单击**\<空字符串\>**，然后键入**C:\HowTos\Out\NorthAmerica%MessageID%.xml**  
  
7.  从事实数据资源管理器拖动**设置终结点出站传输类型**定义与**操作**。  
  
8.  在事实数据资源管理器中，展开**ESB。TansportTypes**词汇，展开**版本 1.0**，然后拖动**适配器提供程序**定义与**\<空字符串\>**.  
  
9. 在操作窗格中，展开**适配器提供程序**下拉列表，然后单击**文件**。  
  
 **若要发布和部署策略**  
  
1.  在策略资源管理器下**RouteBasedOnMessageType**策略中，右击**（不保存） 1.0 版**，然后单击**发布**。  
  
2.  在策略资源管理器下**RouteBasedOnMessageType**策略中，右击**版本 1.0-发布**，然后单击**部署**。  
  
 **若要创建 ESB 路线域特定语言 (DSL) 模型**  
  
1.  在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器，右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。  
  
3.  在**名称**框中，键入**MessageType**，然后单击**添加**。  
  
 **若要配置路线的属性**  
  
1.  在 Visual Studio 中，单击的设计图面**MessageType.itinerary**。 在**MessageType**属性窗口中，配置以下属性：  
  
    1.  在**模型导出程序**下拉列表中，单击**XML 路线导出程序**。  
  
    2.  在**扩展程序设置**部分，旁边**路线 XML 文件**属性，单击省略号按钮 （…）。  
  
    3.  在**选择 XML 文件**对话框中，在**文件名**框中，键入**C:\HowTos\Itineraries\MessageType**，然后单击**保存**。  
  
        > [!NOTE]
        >  此步骤允许您路线作为 XML 导出到本地文件位置。 到路线的数据库，而不导出到本地文件的位置，一条路线使路线使用 ESB 测试客户端应用程序的测试。 你将完成本操作方法主题中后面此过程。  
  
 **若要定义路线的结构**  
  
1.  从工具箱中，拖动**上负载增加**到设计图面上的模型元素。 在**OnRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**ReceiveOrders**。  
  
    2.  在**扩展程序**下拉列表中，单击**上负载增加 ESB 扩展程序**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
    4.  在**接收端口**下拉列表中，单击**OnRamp.Itinerary**。  
  
2.  从工具箱中，拖动**路线服务**模型元素到设计图面，然后将其放到右侧**上负载增加**模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**BreRoute**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**消息传送扩展程序**。  
  
        > [!NOTE]
        >  此属性定义的过程将需要在管道 （消息传送） 中的位置。 或者，如果过程将需要一个业务流程中的位置，则设置**路线服务扩展程序**属性**Orchestration 扩展程序**。  
  
    3.  在**容器**下拉列表中，展开**ReceiveOrders**，然后单击**接收处理程序**。  
  
    4.  在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。  
  
3.  右键单击**冲突解决程序**集合**BreRoute**模型元素，并依次**添加新解析程序**。 在**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**ByMessageType**。  
  
    2.  在**解析程序实现**下拉列表中，单击**Bre 冲突解决程序扩展**。  
  
    3.  在**策略**下拉列表中，单击**RouteBasedOnMessageType v 1.0**。  
  
4.  在工具箱中，单击**连接器**。 将从连接**ReceiveOrders**到模型元素**BreRoute**模型元素。  
  
5.  从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**BreRoute**模型元素。 在**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SendBasedOnType**。  
  
    2.  在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 扩展程序**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。  
  
6.  从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**BreRoute**模型元素和**SendBasedOnType**模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SendPortFilter**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**关闭负载增加扩展程序**。  
  
    3.  在**关闭负载增加**下拉列表中，展开**SendBasedOnType**，然后单击**发送处理程序**。  
  
7.  在工具箱中，单击**连接器**。 将从连接**BreRoute**到模型元素**SendPortFilter**模型元素。  
  
8.  在工具箱中，单击**连接器**。 将从连接**SendPortFilter**到模型元素**SendBasedOnType**模型元素。  
  
 **若要导出与路线测试客户端一起使用的模型**  
  
1.  在 Visual Studio 中，右键单击的设计图面**MessageType**路线，，然后单击**导出模型**。  
  
    > [!NOTE]
    >  在 Visual Studio 中打开的 XML 版本的路线。  
  
2.  保存所有项目。  
  
3.  在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries，并注意你路线 XML (MessageType.xml) 创建。  
  
 **若要测试路线**  
  
1.  打开路线测试客户端示例应用程序使用期间创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。  
  
2.  在路线测试客户端中，清除**使用 WCF 服务**复选框，并依次**负载路线**。  
  
3.  在**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。 选择**MessageType.xml**，然后单击**打开**加载路线。  
  
4.  单击**确定**清除**成功加载路线**消息。  
  
5.  在路线测试客户端上，单击旁边的省略号按钮 （...）**负载消息**框。  
  
6.  在**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。 选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。  
  
7.  单击**提交请求**按钮。 在测试完成后，单击**确定**关闭出现的确认。  
  
8.  在 Windows 资源管理器，浏览到 C:\HowTos\Out\\。 验证 NorthAmerica%MessageID%.xml 消息已写入到目录。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [如何：使用业务规则策略选择路线](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [如何：转换消息并使用路线传送名单将生成的消息路由至文件位置](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [如何：使用已知消息类型的业务规则策略实现基于内容的路由](../esb-toolkit/apply-content-based-routing-using-business-rules-policy-for-known-message-type.md)  
  
-   [开发活动](../esb-toolkit/development-activities.md)  
  
-   [消息路由模式](../esb-toolkit/message-routing-patterns.md)  
  
-   [使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)