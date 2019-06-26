---
title: 如何：转换消息并使用请求-响应消息交换模式的服务终结点的路由 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b1e656fb-6c5f-4b2b-a1b6-4c812b78ee22
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7bea07435e4d9bf10df8e47fda319a0fd106ed9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399648"
---
# <a name="how-to-transform-a-message-and-route-to-a-service-endpoint-using-a-request-response-message-exchange-pattern"></a>如何：转换消息并使用请求-响应消息交换模式的服务终结点的路由
## <a name="goal"></a>目的  
 本部分演示如何使用 ESB 设计器特定于域的语言 (DSL) 来创建可用于双向接入点请求-响应路线。 您将创建一个传送名单收到一条消息、 将消息转换、 提交到服务，消息和服务响应消息返回到原始消息的提交者。  
  
 在本操作指南主题中，您将完成以下步骤：  
  
-   使用实现了一个 Microsoft BizTalk Server 映射转换路线服务创建路线传送名单。  
  
-   配置路线以便将转换后的消息路由到服务终结点。  
  
-   配置路线服务响应消息返回到原始发送方。  
  
-   测试使用路线测试客户端示例应用程序的路线。  
  
## <a name="prerequisites"></a>先决条件  
 本操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。  
  
## <a name="steps"></a>步骤  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>若要创建的 ESB 路线 DSL 模型  
  
1.  在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器中右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。  
  
3.  在中**添加新项**对话框中**名称**框中，键入**RequestResponse**，然后单击**添加**。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>若要配置的路线属性  
  
1.  在 Visual Studio 中，单击的设计图面**RequestResponse.itinerary**。 在中**RequestResponse**属性窗口中，配置以下属性：  
  
    1.  在中**是请求响应**下拉列表中，单击**True**。  
  
    2.  在中**模型导出程序**下拉列表中，单击**XML 路线导出程序**。  
  
    3.  在中**扩展器设置**部分中下, 一步**路线 XML 文件**属性中，单击省略号按钮 （...）。  
  
    4.  在中**选择 XML 文件**对话框中**文件名**框中，键入**C:\HowTos\Itineraries\RequestResponse**，然后单击**保存**。  
  
        > [!NOTE]
        >  此步骤中，可将路线以 XML 形式导出到本地文件位置。 通过为行程数据库，而不导出到本地文件的位置，路线，路线使用 ESB 测试客户端应用程序的测试。 您将完成此过程更高版本的本操作指南主题。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>若要定义路线的结构  
  
1.  从工具箱拖动**接入点**至设计图面上的模型元素。 在中**OnRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**ReceiveNAOrder**。  
  
    2.  在中**Extender**下拉列表中，单击**接入点 ESB 扩展器**。  
  
    3.  在中**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
    4.  在中**接收端口**下拉列表中，单击**OnRamp.Itinerary.Response**。  
  
2.  从工具箱拖动**路线服务**模型元素到设计图面，然后将它放到右侧**接入点**模型元素。 在中**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**MapNAOrderToCNOrder**。  
  
    2.  在**路线服务 Extender**下拉列表中，单击**消息扩展器**。  
  
        > [!NOTE]
        >  此属性定义，过程将花费 （消息传送） 管道中的位置。 或者，如果该过程会发生在业务流程中，设置**路线服务 Extender**属性设置为**业务流程扩展器**。  
  
    3.  在中**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。  
  
    4.  在中**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Transform**。  
  
3.  右键单击**冲突解决程序**系列**MapNAOrderToCNOrder**模型元素，然后单击**添加新解析程序**。 在中**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**StaticallySpecifyTheMap**。  
  
    2.  在中**解析程序实现**下拉列表中，单击**静态解析程序扩展**。  
  
    3.  在中**转换的类型**下拉列表中，单击**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**。  
  
4.  在工具箱中，单击**连接器**。 将从连接**ReceiveNAOrder**到模型元素**MapNAOrderToCNOrder**模型元素。  
  
5.  从工具箱拖动**路线服务**模型元素到设计图面，然后将它放到右侧**MapNAOrderToCNOrder**模型元素。 在中**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**RouteToCNService**。  
  
    2.  在**路线服务 Extender**下拉列表中，单击**消息扩展器**。  
  
        > [!NOTE]
        >  此属性定义，过程将花费 （消息传送） 管道中的位置。 或者，如果该过程会发生在业务流程中，设置**路线服务 Extender**属性设置为**业务流程扩展器**。  
  
    3.  在中**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。  
  
    4.  在中**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。  
  
6.  右键单击**冲突解决程序**系列**RouteToCNService**模型元素，然后单击**添加新解析程序**。 在中**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**StaticallySpecifyTheService**。  
  
    2.  在中**解析程序实现**下拉列表中，单击**静态解析程序扩展**。  
  
    3.  在中**传输名称**下拉列表中，单击**Wcf-basichttp**。  
  
    4.  单击**传输位置**属性，并键入 **http://localhost/ESB.CanadianServices/SubmitPOService.asmx** 。  
  
    5.  单击**目标 Namespace**属性，并键入 **http://globalbank.esb.dynamicresolution.com/canadianservices** 。  
  
    6.  单击**操作**属性，并键入**submitOrder**。  
  
7.  在工具箱中，单击**连接器**。 将从连接**MapNAOrderToCNOrder**到模型元素**RouteToCNService**模型元素。  
  
8.  从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**RouteToCNService**模型元素。 在中**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**InvokeCNService**。  
  
    2.  在**Extender**下拉列表中，单击**关闭负载增加 ESB 扩展器**。  
  
    3.  在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在中**发送端口**下拉列表中，单击**DynamicResolutionSolicitResp**。  
  
9. 从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**RouteToCNService**模型元素和**InvokeCNService**模型元素。 在中**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**SendPortFilter**。  
  
    2.  在**路线服务 Extender**下拉列表中，单击**接入点关闭扩展器**。  
  
    3.  在中**关闭负载增加**下拉列表中，展开**InvokeCNService**，然后单击**发送处理程序**。  
  
10. 在工具箱中，单击**连接器**。 将从连接**RouteToCNService**到模型元素**SendPortFilter**模型元素。  
  
11. 在工具箱中，单击**连接器**。 将从连接**SendPortFilter**到模型元素**InvokeCNService**模型元素。  
  
12. 右键单击设计图面上，然后依次**验证**。  
  
    > [!NOTE]
    >  路线验证;不需要关闭负载增加重新连接到了的途径，若要将响应消息发送回请求方。 通过使用双向接入点，最后一条消息自动返回到请求方。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>若要导出与路线测试客户端一起使用的模型  
  
1.  在 Visual Studio 中，右键单击设计图面的**RequestResponse**路线，并单击**导出模型**。  
  
    > [!NOTE]
    >  在 Visual Studio 中打开的 XML 版本的路线。  
  
2.  保存项目的所有项目。  
  
3.  在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries。 请注意，您的路线 XML (RequestResponse.xml) 创建。  
  
#### <a name="to-test-the-itinerary"></a>若要测试路线  
  
1.  打开路线测试客户端示例应用程序使用过程中创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。  
  
2.  在路线测试客户端，清除**使用 WCF 服务**复选框。  
  
3.  在中**Web 服务选项**部分中，选择**两种方式服务**复选框，然后依次**负载路线**。  
  
4.  在中**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。 选择**RequestResponse.xml**，然后单击**打开**加载路线。  
  
5.  单击**确定**清除**成功加载路线**消息。  
  
6.  在路线测试客户端，单击下一步的省略号按钮 （...）**负载消息**框。  
  
7.  在中**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。 选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。  
  
8.  单击**提交请求**按钮。 测试完成后，单击**确定**若要消除出现的确认。  
  
9. 在中**结果**框中，请注意，消息的根节点是**submitOrderResponse**和默认命名空间是...**canadianservices**。  
  
    > [!NOTE]
    >  如果响应消息响应发送到请求方之前需要其他转换，则必须使用包含 ESB 转发器组件的管道。 有关此功能的示例，请参阅[安装和运行多个 Web 服务示例](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [如何：转换消息并将生成的消息路由到使用路线传送名单的文件位置](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [开发活动](../esb-toolkit/development-activities.md)  
  
-   [消息路由模式](../esb-toolkit/message-routing-patterns.md)  
  
-   [安装和运行多个 Web 服务示例](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)