---
title: "如何： 实现基于内容的路由使用消息上下文属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 952af792-5762-4b04-9087-980bb3323568
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be099923fea9d5dbb22559203b297fadf5dd1fdc
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-implement-content-based-routing-using-message-context-properties"></a>如何： 实现基于内容的路由使用消息上下文属性
## <a name="goal"></a>目的  
 本部分演示如何使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线设计器来创建一条路线选择消息接收方根据消息上下文属性，然后将消息路由到此收件人使用路线 Broker 消息传递服务。  
  
 在本主题中，你将完成以下步骤：  
  
-   使用路线 broker 和使用静态解析程序的两个路由服务创建一条路线。  
  
-   测试路线使用路线测试客户端示例应用程序。  
  
> [!NOTE]
>  在当前实现中提供了不基于业务流程的 broker 服务。  
  
## <a name="prerequisites"></a>先决条件  
 此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。  
  
## <a name="steps"></a>步骤  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>若要创建 ESB 路线 DSL 模型  
  
1.  在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器，右键单击**ItineraryLibrary**，指向**添加**，然后单击**新路线**。  
  
3.  在**添加新项**对话框中，单击**ItineraryDsl**在模板窗格中。  
  
4.  在**名称**框中，键入**ChoiceRouter**，然后单击**添加**。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>若要配置路线的属性  
  
1.  在 Visual Studio 中，单击的设计图面**ChoiceRouter**路线。 在**ChoiceRouter**属性窗口中，配置以下属性：  
  
    1.  在**模型导出程序**下拉列表中，单击**XML 路线导出程序**。  
  
    2.  在**扩展程序设置**部分中，单击旁边的省略号按钮 （...）**路线 XML 文件**属性。  
  
    3.  在**导出模式**属性下拉列表中，单击**Strict**。  
  
    4.  在**选择 XML 文件**对话框中，键入**C:\HowTos\Itineraries\ChoiceRouter**中**文件名**框中，并依次**保存**。  
  
    > [!NOTE]
    >  此步骤允许您路线作为 XML 导出到本地文件位置。 通过将一条路线到本地文件的位置，而不导出到路线的数据库中，你可以测试路线使用 ESB 测试客户端应用程序。 你将完成本操作方法主题中后面此过程。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>若要定义路线的结构  
  
1.  从工具箱中，拖动**上负载增加**到设计图面上的模型元素。 在 OnRamp1 属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**ReceiveNAOrder**。  
  
    2.  在**扩展程序**下拉列表中，单击**上负载增加扩展程序**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
    4.  在**接收端口**下拉列表中，单击**OnRamp.Itinerary**。  
  
2.  从工具箱中，拖动**路线 Broker 服务**模型元素到设计器图面，然后将其放到右侧**上负载增加**模型元素。 在**ItineraryBrokerService1**，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**RouteBrokerService**。  
  
    2.  在**扩展程序**下拉列表中，单击**消息传递代理扩展程序**。  
  
    3.  在**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。  
  
    4.  在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Itinerary.Services.Broker.MessagingBroker**。  
  
3.  右键单击**筛选器**集合，，然后单击**添加新的筛选器**。 在**Filter1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**ASMXFilter**。  
  
    2.  单击**筛选器**实现下拉列表，然后单击**XPath 筛选器**。  
  
    3.  单击**表达式**属性，再然后键入**计数 (/ ContextProperties/属性 [@name= InboundTransportLocation] [包含 (。，ProcessItinerary.asmx)]) > 0**。  
  
4.  右键单击**筛选器**集合，，然后单击**添加新的筛选器**。 在**Filter1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**WCFFilter**。  
  
    2.  单击**筛选器实现**下拉列表中，然后单击**XPath 筛选器**。  
  
    3.  单击**表达式**属性，再然后键入**计数 (/ ContextProperties/属性 [@name= InboundTransportLocation] [包含 (。，ESB。ItineraryServices.WCF')]) > 0**。  
  
5.  右键单击**冲突解决程序**集合**RouteBrokerService**模型元素，并依次**添加新解析程序**。 在**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**ResolverBrokerRoute**。  
  
    2.  在**解析程序实现**下拉列表中，单击**MessageContext 冲突解决程序扩展**。  
  
6.  在工具箱中，单击**连接器**。 将从连接**ReceiveNAOrder**到模型元素**RouteBrokerService**模型元素。  
  
7.  从工具箱中，拖动**路线服务**模型元素到设计图面，然后将其在**RouteBrokerService**模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**RouteToFileFromASMX**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**消息传送扩展程序**。  
  
        > [!NOTE]
        >  此属性定义的过程将需要在管道 （消息传送） 中的位置。 或者，如果过程将需要一个业务流程中的位置，则设置**路线服务扩展程序**属性**Orchestration 扩展程序**。  
  
    3.  在**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。  
  
    4.  在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。  
  
8.  右键单击**冲突解决程序**集合**RouteToFileFromASMX**模型元素，并依次**添加新解析程序**。 在**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**ResolverFromAsmx**。  
  
    2.  在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。  
  
    3.  在**传输名称**下拉列表中，单击**文件**。  
  
    4.  单击**传输位置**属性，再然后键入**c:\howtos\out\asmx%MessageId%.xml**。  
  
9. 从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**RouteToFileFromASMX**模型元素。 在**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SendASMXOrder**。  
  
    2.  在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 扩展程序**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。  
  
10. 从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**RouteToFileFromASMX**模型元素和**SendASMXOrder**模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SendPortFilterASMX**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**关闭负载增加扩展程序**。  
  
    3.  在**关闭负载增加**下拉列表中，展开**SendASMXOrder**，然后单击**发送处理程序**。  
  
11. 在工具箱中，单击**连接器**。 将从连接**RouteToFileFromASMX**到模型元素**SendPortFilterASMX**模型元素。  
  
12. 在工具箱中，单击**连接器**。 将从连接**SendPortFilterASMX**到模型元素**SendASMXOrder**模型元素。  
  
13. 从工具箱中，拖动**路线服务**模型元素到设计图面，然后将其放到右侧**RouteBrokerService**模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**RouteToFileFromWCF**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**消息传送扩展程序**。  
  
        > [!NOTE]
        >  此属性定义的过程将需要在管道 （消息传送） 中的位置。 或者，如果过程将需要一个业务流程中的位置，则设置**路线服务扩展程序**属性**Orchestration 扩展程序**。  
  
    3.  在**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。  
  
    4.  在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。  
  
14. 右键单击**冲突解决程序**集合**RouteToFileFromWCF**模型元素，并依次**添加新解析程序**。 在**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**ResolverFromWCF**。  
  
    2.  在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。  
  
    3.  在**传输名称**下拉列表中，单击**文件**。  
  
    4.  单击**传输位置**属性，再然后键入**c:\howtos\out\wcf%MessageId%.xml**。  
  
15. 从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**RouteToFileFromWCF**模型元素。 在**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SendWCFOrder**。  
  
    2.  在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 扩展程序**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。  
  
16. 从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**RouteToFileFromWCF**模型元素和**SendWCFOrder**模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SendPortFilterWCF**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**关闭负载增加扩展程序**。  
  
    3.  在**关闭负载增加**下拉列表中，展开**SendWCFOrder**，然后单击**发送处理程序**。  
  
17. 在工具箱中，单击**连接器**。 将从连接**RouteToFileFromWCF**到模型元素**SendPortFilterWCF**模型元素。  
  
18. 在工具箱中，单击**连接器**。 将从连接**SendPortFilterWCF**到模型元素**SendWCFOrder**模型元素。  
  
19. 从工具箱中，拖动**路线 Outport**到右边框的模型元素**RouteBrokerService**。 在**ItineraryBrokerOutPort1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**WCF 端口**。  
  
    2.  在**筛选器**下拉列表中，单击**WCFFilter**。  
  
    3.  在**冲突解决程序**下拉列表中，单击**ResolverBrokerRoute**。  
  
20. 从工具箱中，拖动**路线 Outport**到下边框的模型元素**RouteBrokerService**。 在**ItineraryBrokerOutPort1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**ASMX 端口**。  
  
    2.  在**筛选器**下拉列表中，单击**ASMXFilter**。  
  
    3.  在**冲突解决程序**下拉列表中，单击**ResolverBrokerRoute**。  
  
21. 在工具箱中，单击**连接器**。 将从连接**WCF 端口**到模型元素**RouteToFileFromWCF**模型元素。  
  
22. 在工具箱中，单击**连接器**。 将从连接**ASMX 端口**到模型元素**RouteToFileFromASMX**模型元素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>若要导出与路线测试客户端一起使用的模型  
  
> [!NOTE]
>  你将需要两次导出路线： 在 XML 中一次，另一个时间到数据库来测试通过代理路由。  
  
1.  在 Visual Studio 中，右键单击的设计图面**ChoiceRouter**路线，，然后单击**导出模型**。  
  
    > [!NOTE]
    >  在 Visual Studio 中打开的 XML 版本的路线。  
  
2.  在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries，，然后记下你路线 XML (ChoiceRouter.xml) 创建。  
  
3.  在 Visual Studio 中，右键单击的设计图面**ChoiceRouter**路线，，然后单击**导出模型**。  
  
4.  在属性窗口中，单击**数据库路线导出程序**中**模型导出程序**下拉列表。  
  
5.  在属性窗口中，设置**路线数据库**属性连接字符串以指向路线的数据库。  
  
6.  在**路线状态**属性下拉列表中，选择**已部署**。  
  
7.  在 Visual Studio 中，右键单击的设计图面**ChoiceRouter**路线，，然后单击**导出模型**。  
  
#### <a name="to-test-the-itinerary"></a>若要测试路线  
  
1.  打开路线测试客户端示例应用程序使用期间创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。  
  
2.  在路线测试客户端中，清除**使用 WCF 服务**复选框，并依次**负载路线**。  
  
3.  在**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。 选择**ChoiceRouter.xml**，然后单击**打开**加载路线。  
  
4.  单击**确定**以关闭"路线加载成功"消息。  
  
5.  在路线测试客户端上，单击旁边的省略号按钮 （...）**负载消息**框。  
  
6.  在**选择要加载 XML 文档**对话框中，浏览到 C:\Patterns\HowTos。 选择 NAOrderDoc.xml，，然后单击**打开**加载测试消息。  
  
7.  单击**提交请求**按钮。 在测试完成后，单击**确定**关闭显示的确认消息。  
  
8.  在 Windows 资源管理器，浏览到 C:\HowTos\Out。验证此目录中已写的 ASMX%MessageID%.xml 消息。  
  
9. 单击路线测试客户端**使用 WCF 服务**复选框。 在**路线名称**框中，键入**ChoiceRouter**，然后单击**提交请求**按钮。 在测试完成后，单击**确定**关闭确认消息。  
  
10. 在 Windows 资源管理器，浏览到 C:\HowTos\Out。验证此目录中已写的 WCF%MessageID%.xml 消息。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [如何：使用业务规则策略选择路线](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [如何：使用业务规则策略动态路由基于消息上下文的消息](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
-   [开发活动](../esb-toolkit/development-activities.md)  
  
-   [消息路由模式](../esb-toolkit/message-routing-patterns.md)