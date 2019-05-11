---
title: 如何：动态路由基于消息上下文中使用业务规则策略的消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d3b68de-6b24-46fe-ae0d-91afb630bc19
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e13a2e214622027ee8e28980c4d7cbc97714bd7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306298"
---
# <a name="how-to-dynamically-route-a-message-based-on-message-context-using-a-business-rules-policy"></a>如何：动态路由基于消息上下文中使用业务规则策略的消息
## <a name="goal"></a>目的  
 本部分演示如何创建路线，其确定消息终结点，基于消息上下文属性，使用 BizTalk Server 业务规则引擎 (BRE) 策略，然后使用 BizTalk Server 文件适配器将消息路由。  
  
 在本操作指南主题中，您将完成以下步骤：  
  
-   创建业务规则策略来评估消息类型。  
  
-   创建路线传送名单以动态方式路由使用业务规则策略。  
  
-   测试使用路线测试客户端示例应用程序的路线。  
  
## <a name="prerequisites"></a>先决条件  
 本操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。  
  
## <a name="steps"></a>步骤  
 **若要创建使用消息上下文属性将消息路由的 BRE 策略**  
  
1. 单击**启动**在任务栏上，依次指向**所有程序**，指向**BizTalk Server**，然后单击**业务规则编辑器**。  
  
2. 在策略浏览器中右键单击**策略**，然后单击**添加新策略**。 将策略命名**RouteBasedOnMessageType**。  
  
   **若要添加的路由规则，北美的订单**  
  
3. 在中**RouteBasedOnMessageType**策略中，右键单击**版本 1.0 （未保存）**，然后单击**添加新规则**。 命名规则**SetNAOrderEndpoint**。  
  
4. 在规则窗口中，右键单击**条件**，依次指向**谓词**，然后单击**相等**。  
  
5. 在事实浏览器中展开**ESB。ContextInfo**词汇，展开**版本 1.0**，然后将拖**上下文消息类型**事实**argument1**节点下的**条件**。  
  
   > [!NOTE]
   >  [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括几个可用于创建规则的词汇。 其中一些应替换或扩充了自己的词汇。 例如， **DynamicRunTimeMaptypes**策略具有定义中提供的映射**GlobalBank**示例。  
  
6. 单击**argument2**节点，并键入 **http://globalbank.esb.dynamicresolution.com/northamericanservices/#OrderDoc**  
  
7. 在事实浏览器中展开**ESB。EndPointInfo**词汇，展开**版本 1.0**，然后将拖**设置终结点出站传输位置**定义**操作**。  
  
8. 单击**\<空字符串\>**，然后键入**C:\HowTos\Out\NorthAmerica%MessageID%.xml**  
  
9. 从事实浏览器中，将**设置终结点出站传输类型**定义**操作**。  
  
10. 在事实浏览器中展开**ESB。TansportTypes**词汇，展开**版本 1.0**，然后将拖**适配器提供程序**定义**\<空字符串\>**.  
  
11. 在操作窗格中，展开**适配器提供程序**下拉列表，再单击**文件**。  
  
    **若要发布和部署策略**  
  
12. 在策略浏览器下**RouteBasedOnMessageType**策略中，右键单击**版本 1.0 （未保存）**，然后单击**发布**。  
  
13. 在策略浏览器下**RouteBasedOnMessageType**策略中，右键单击**版本 1.0-已发布**，然后单击**部署**。  
  
    **若要创建的 ESB 路线域特定语言 (DSL) 模型**  
  
14. 在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。  
  
15. 在解决方案资源管理器中右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。  
  
16. 在中**名称**框中，键入**MessageType**，然后单击**添加**。  
  
    **若要配置的路线属性**  
  
17. 在 Visual Studio 中，单击的设计图面**MessageType.itinerary**。 在中**MessageType**属性窗口中，配置以下属性：  
  
    1.  在中**模型导出程序**下拉列表中，单击**XML 路线导出程序**。  
  
    2.  在中**扩展器设置**部分中下, 一步**路线 XML 文件**属性中，单击省略号按钮 （...）。  
  
    3.  在中**选择 XML 文件**对话框中**文件名**框中，键入**C:\HowTos\Itineraries\MessageType**，然后单击**保存**。  
  
        > [!NOTE]
        >  此步骤中，可将路线以 XML 形式导出到本地文件位置。 为行程数据库，而不导出到本地文件的位置，路线，路线使用 ESB 测试客户端应用程序的测试。 您将完成此过程更高版本的本操作指南主题。  
  
    **若要定义路线的结构**  
  
18. 从工具箱拖动**接入点**至设计图面上的模型元素。 在中**OnRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**ReceiveOrders**。  
  
    2.  在中**Extender**下拉列表中，单击**接入点 ESB 扩展器**。  
  
    3.  在中**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
    4.  在中**接收端口**下拉列表中，单击**OnRamp.Itinerary**。  
  
19. 从工具箱拖动**路线服务**模型元素到设计图面，然后将它放到右侧**接入点**模型元素。 在中**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**BreRoute**。  
  
    2.  在**路线服务 Extender**下拉列表中，单击**消息扩展器**。  
  
        > [!NOTE]
        >  此属性定义，过程将花费 （消息传送） 管道中的位置。 或者，如果该过程会发生在业务流程中，设置**路线服务 Extender**属性设置为**业务流程扩展器**。  
  
    3.  在中**容器**下拉列表中，展开**ReceiveOrders**，然后单击**接收处理程序**。  
  
    4.  在中**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。  
  
20. 右键单击**冲突解决程序**系列**BreRoute**模型元素，然后单击**添加新解析程序**。 在中**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**ByMessageType**。  
  
    2.  在中**解析程序实现**下拉列表中，单击**Bre 冲突解决程序扩展**。  
  
    3.  在中**策略**下拉列表中，单击**RouteBasedOnMessageType v 1.0**。  
  
21. 在工具箱中，单击**连接器**。 将从连接**ReceiveOrders**到模型元素**BreRoute**模型元素。  
  
22. 从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**BreRoute**模型元素。 在中**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**SendBasedOnType**。  
  
    2.  在**Extender**下拉列表中，单击**关闭负载增加 ESB 扩展器**。  
  
    3.  在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在中**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。  
  
23. 从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**BreRoute**模型元素和**SendBasedOnType**模型元素。 在中**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**SendPortFilter**。  
  
    2.  在**路线服务 Extender**下拉列表中，单击**接入点关闭扩展器**。  
  
    3.  在中**关闭负载增加**下拉列表中，展开**SendBasedOnType**，然后单击**发送处理程序**。  
  
24. 在工具箱中，单击**连接器**。 将从连接**BreRoute**到模型元素**SendPortFilter**模型元素。  
  
25. 在工具箱中，单击**连接器**。 将从连接**SendPortFilter**到模型元素**SendBasedOnType**模型元素。  
  
    **若要导出与路线测试客户端一起使用的模型**  
  
26. 在 Visual Studio 中，右键单击设计图面的**MessageType**路线，并单击**导出模型**。  
  
    > [!NOTE]
    >  在 Visual Studio 中打开的 XML 版本的路线。  
  
27. 保存项目的所有项目。  
  
28. 在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries 并请注意，您的路线 XML (MessageType.xml) 创建。  
  
    **若要测试路线**  
  
29. 打开路线测试客户端示例应用程序使用过程中创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。  
  
30. 在路线测试客户端，清除**使用 WCF 服务**复选框，然后依次**负载路线**。  
  
31. 在中**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。 选择**MessageType.xml**，然后单击**打开**加载路线。  
  
32. 单击**确定**清除**成功加载路线**消息。  
  
33. 在路线测试客户端，单击下一步的省略号按钮 （...）**负载消息**框。  
  
34. 在中**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。 选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。  
  
35. 单击**提交请求**按钮。 测试完成后，单击**确定**若要消除出现的确认。  
  
36. 在 Windows 资源管理器，浏览到 C:\HowTos\Out\\。 验证 NorthAmerica%MessageID%.xml 消息已写入到目录。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [如何：选择使用业务规则策略路线](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [如何：转换消息并将生成的消息路由到使用路线传送名单的文件位置](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [如何：实现基于内容的路由使用业务规则策略为已知的消息类型](../esb-toolkit/apply-content-based-routing-using-business-rules-policy-for-known-message-type.md)  
  
-   [开发活动](../esb-toolkit/development-activities.md)  
  
-   [消息路由模式](../esb-toolkit/message-routing-patterns.md)  
  
-   [使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)