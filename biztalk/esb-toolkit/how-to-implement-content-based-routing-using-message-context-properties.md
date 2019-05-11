---
title: 如何：实现基于内容的路由使用消息上下文属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 952af792-5762-4b04-9087-980bb3323568
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 200341cb4866806429ee132d07f17b94379a9583
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295821"
---
# <a name="how-to-implement-content-based-routing-using-message-context-properties"></a>如何：实现基于内容的路由使用消息上下文属性
## <a name="goal"></a>目的  
 本部分演示如何使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线设计器创建路线选择消息接收方根据消息上下文属性，然后将消息路由到该收件人使用路线 Broker 消息传递服务。  
  
 在本主题中，您将完成以下步骤：  
  
-   使用路线 broker 和使用静态冲突解决程序的两个路由服务创建路线。  
  
-   测试使用路线测试客户端示例应用程序的路线。  
  
> [!NOTE]
>  当前实现中不提供了任何基于业务流程的 broker 服务。  
  
## <a name="prerequisites"></a>先决条件  
 本操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。  
  
## <a name="steps"></a>步骤  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>若要创建的 ESB 路线 DSL 模型  
  
1.  在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器中右键单击**ItineraryLibrary**，依次指向**添加**，然后单击**新路线**。  
  
3.  在中**添加新项**对话框中，单击**ItineraryDsl**模板窗格中。  
  
4.  在中**名称**框中，键入**ChoiceRouter**，然后单击**添加**。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>若要配置的路线属性  
  
1.  在 Visual Studio 中，单击的设计图面**ChoiceRouter**路线。 在中**ChoiceRouter**属性窗口中，配置以下属性：  
  
    1.  在中**模型导出程序**下拉列表中，单击**XML 路线导出程序**。  
  
    2.  在中**扩展器设置**部分中，单击旁边的省略号按钮 （...）**路线 XML 文件**属性。  
  
    3.  在中**导出模式**属性下拉列表中，单击**Strict**。  
  
    4.  在中**选择 XML 文件**对话框中，键入**C:\HowTos\Itineraries\ChoiceRouter**中**文件名**框，并单击**保存**。  
  
    > [!NOTE]
    >  此步骤中，可将路线以 XML 形式导出到本地文件位置。 通过将一条路线到本地文件的位置，而不导出到行程数据库，您可以测试路线使用 ESB 测试客户端应用程序。 您将完成此过程更高版本的本操作指南主题。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>若要定义路线的结构  
  
1.  从工具箱拖动**接入点**至设计图面上的模型元素。 在 OnRamp1 属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**ReceiveNAOrder**。  
  
    2.  在中**Extender**下拉列表中，单击**接入点扩展程序**。  
  
    3.  在中**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
    4.  在中**接收端口**下拉列表中，单击**OnRamp.Itinerary**。  
  
2.  从工具箱拖动**路线 Broker 服务**模型设计器图面，元素，然后将它放到右侧**接入点**模型元素。 在中**ItineraryBrokerService1**，配置以下属性：  
  
    1.  单击**名称**属性，并键入**RouteBrokerService**。  
  
    2.  在中**Extender**下拉列表中，单击**消息传送中转站扩展器**。  
  
    3.  在中**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。  
  
    4.  在中**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Itinerary.Services.Broker.MessagingBroker**。  
  
3.  右键单击**筛选器**集合，并单击**添加新的筛选器**。 在中**Filter1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**ASMXFilter**。  
  
    2.  单击**筛选器**实现下拉列表，再单击**XPath 筛选器**。  
  
    3.  单击**表达式**属性，并键入**计数 (/ ContextProperties/属性 [@name= InboundTransportLocation] [包含 (。，ProcessItinerary.asmx')]) > 0**。  
  
4.  右键单击**筛选器**集合，并单击**添加新的筛选器**。 在中**Filter1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**WCFFilter**。  
  
    2.  单击**筛选器实现**下拉列表中，然后单击**XPath 筛选器**。  
  
    3.  单击**表达式**属性，并键入**计数 (/ ContextProperties/属性 [@name= InboundTransportLocation] [包含 (。，ESB。ItineraryServices.WCF')]) > 0**。  
  
5.  右键单击**冲突解决程序**系列**RouteBrokerService**模型元素，然后单击**添加新解析程序**。 在中**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**ResolverBrokerRoute**。  
  
    2.  在中**解析程序实现**下拉列表中，单击**MessageContext 冲突解决程序扩展**。  
  
6.  在工具箱中，单击**连接器**。 将从连接**ReceiveNAOrder**到模型元素**RouteBrokerService**模型元素。  
  
7.  从工具箱拖动**路线服务**模型元素到设计图面，然后将其下放置**RouteBrokerService**模型元素。 在中**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**RouteToFileFromASMX**。  
  
    2.  在**路线服务 Extender**下拉列表中，单击**消息扩展器**。  
  
        > [!NOTE]
        >  此属性定义，过程将花费 （消息传送） 管道中的位置。 或者，如果该过程会发生在业务流程中，设置**路线服务 Extender**属性设置为**业务流程扩展器**。  
  
    3.  在中**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。  
  
    4.  在中**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。  
  
8.  右键单击**冲突解决程序**系列**RouteToFileFromASMX**模型元素，然后单击**添加新解析程序**。 在中**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**ResolverFromAsmx**。  
  
    2.  在中**解析程序实现**下拉列表中，单击**静态解析程序扩展**。  
  
    3.  在中**传输名称**下拉列表中，单击**文件**。  
  
    4.  单击**传输位置**属性，并键入**c:\howtos\out\asmx%MessageId%.xml**。  
  
9. 从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**RouteToFileFromASMX**模型元素。 在中**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**SendASMXOrder**。  
  
    2.  在**Extender**下拉列表中，单击**关闭负载增加 ESB 扩展器**。  
  
    3.  在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在中**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。  
  
10. 从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**RouteToFileFromASMX**模型元素和**SendASMXOrder**模型元素。 在中**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**SendPortFilterASMX**。  
  
    2.  在**路线服务 Extender**下拉列表中，单击**接入点关闭扩展器**。  
  
    3.  在中**关闭负载增加**下拉列表中，展开**SendASMXOrder**，然后单击**发送处理程序**。  
  
11. 在工具箱中，单击**连接器**。 将从连接**RouteToFileFromASMX**到模型元素**SendPortFilterASMX**模型元素。  
  
12. 在工具箱中，单击**连接器**。 将从连接**SendPortFilterASMX**到模型元素**SendASMXOrder**模型元素。  
  
13. 从工具箱拖动**路线服务**模型元素到设计图面，然后将它放到右侧**RouteBrokerService**模型元素。 在中**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**RouteToFileFromWCF**。  
  
    2.  在**路线服务 Extender**下拉列表中，单击**消息扩展器**。  
  
        > [!NOTE]
        >  此属性定义，过程将花费 （消息传送） 管道中的位置。 或者，如果该过程会发生在业务流程中，设置**路线服务 Extender**属性设置为**业务流程扩展器**。  
  
    3.  在中**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。  
  
    4.  在中**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。  
  
14. 右键单击**冲突解决程序**系列**RouteToFileFromWCF**模型元素，然后单击**添加新解析程序**。 在中**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**ResolverFromWCF**。  
  
    2.  在中**解析程序实现**下拉列表中，单击**静态解析程序扩展**。  
  
    3.  在中**传输名称**下拉列表中，单击**文件**。  
  
    4.  单击**传输位置**属性，并键入**c:\howtos\out\wcf%MessageId%.xml**。  
  
15. 从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**RouteToFileFromWCF**模型元素。 在中**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**SendWCFOrder**。  
  
    2.  在**Extender**下拉列表中，单击**关闭负载增加 ESB 扩展器**。  
  
    3.  在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在中**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。  
  
16. 从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**RouteToFileFromWCF**模型元素和**SendWCFOrder**模型元素。 在中**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**SendPortFilterWCF**。  
  
    2.  在**路线服务 Extender**下拉列表中，单击**接入点关闭扩展器**。  
  
    3.  在中**关闭负载增加**下拉列表中，展开**SendWCFOrder**，然后单击**发送处理程序**。  
  
17. 在工具箱中，单击**连接器**。 将从连接**RouteToFileFromWCF**到模型元素**SendPortFilterWCF**模型元素。  
  
18. 在工具箱中，单击**连接器**。 将从连接**SendPortFilterWCF**到模型元素**SendWCFOrder**模型元素。  
  
19. 从工具箱拖动**路线 Outport**右边框的模型元素**RouteBrokerService**。 在中**ItineraryBrokerOutPort1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**WCF 端口**。  
  
    2.  在中**筛选器**下拉列表中，单击**WCFFilter**。  
  
    3.  在中**冲突解决程序**下拉列表中，单击**ResolverBrokerRoute**。  
  
20. 从工具箱拖动**路线 Outport**模型元素的下边框**RouteBrokerService**。 在中**ItineraryBrokerOutPort1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**ASMX 端口**。  
  
    2.  在中**筛选器**下拉列表中，单击**ASMXFilter**。  
  
    3.  在中**冲突解决程序**下拉列表中，单击**ResolverBrokerRoute**。  
  
21. 在工具箱中，单击**连接器**。 将从连接**WCF 端口**到模型元素**RouteToFileFromWCF**模型元素。  
  
22. 在工具箱中，单击**连接器**。 将从连接**ASMX 端口**到模型元素**RouteToFileFromASMX**模型元素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>若要导出与路线测试客户端一起使用的模型  
  
> [!NOTE]
>  将需要两次导出路线： 在 XML 中一次，另一个时间到数据库来测试通过代理路由。  
  
1.  在 Visual Studio 中，右键单击设计图面的**ChoiceRouter**路线，并单击**导出模型**。  
  
    > [!NOTE]
    >  在 Visual Studio 中打开的 XML 版本的路线。  
  
2.  在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries，，然后请注意，您的路线 XML (ChoiceRouter.xml) 创建。  
  
3.  在 Visual Studio 中，右键单击设计图面的**ChoiceRouter**路线，并单击**导出模型**。  
  
4.  在属性窗口中，单击**数据库路线导出程序**中**模型导出程序**下拉列表。  
  
5.  在属性窗口中设置**行程数据库**属性以指向路线的数据库的连接字符串。  
  
6.  在中**路线状态**属性下拉列表中，选择**已部署**。  
  
7.  在 Visual Studio 中，右键单击设计图面的**ChoiceRouter**路线，并单击**导出模型**。  
  
#### <a name="to-test-the-itinerary"></a>若要测试路线  
  
1.  打开路线测试客户端示例应用程序使用过程中创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。  
  
2.  在路线测试客户端，清除**使用 WCF 服务**复选框，然后依次**负载路线**。  
  
3.  在中**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。 选择**ChoiceRouter.xml**，然后单击**打开**加载路线。  
  
4.  单击**确定**以关闭"路线加载成功"消息。  
  
5.  在路线测试客户端，单击下一步的省略号按钮 （...）**负载消息**框。  
  
6.  在中**选择要加载 XML 文档**对话框中，浏览到 C:\Patterns\HowTos。 选择 NAOrderDoc.xml，，然后单击**打开**加载测试消息。  
  
7.  单击**提交请求**按钮。 测试完成后，单击**确定**关闭出现的确认消息。  
  
8.  在 Windows 资源管理器，浏览到 C:\HowTos\Out。验证已将 ASMX%MessageID%.xml 消息写入到此目录。  
  
9. 单击路线测试客户端**使用 WCF 服务**复选框。 在中**路线名称**框中，键入**ChoiceRouter**，然后单击**提交申请**按钮。 测试完成后，单击**确定**关闭确认消息。  
  
10. 在 Windows 资源管理器，浏览到 C:\HowTos\Out。验证已将 WCF%MessageID%.xml 消息写入到此目录。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [如何：选择使用业务规则策略路线](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [如何：动态路由基于消息上下文中使用业务规则策略的消息](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
-   [开发活动](../esb-toolkit/development-activities.md)  
  
-   [消息路由模式](../esb-toolkit/message-routing-patterns.md)