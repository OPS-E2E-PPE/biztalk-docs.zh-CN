---
title: "如何： 转换消息和使用请求-响应消息交换模式的服务终结点的路由 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b1e656fb-6c5f-4b2b-a1b6-4c812b78ee22
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dfc7c7d572f3370e87df2f03d392a993116b74d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-transform-a-message-and-route-to-a-service-endpoint-using-a-request-response-message-exchange-pattern"></a>如何： 转换消息和使用请求-响应消息交换模式的服务终结点的路由
## <a name="goal"></a>目的  
 本部分演示如何使用 ESB 设计器域特定语言 (DSL) 来创建可与双向入口使用请求-响应路线。 你将创建要收到一条消息、 消息转换、 提交到服务，消息和返回到原始消息的提交者的服务的响应消息的路由单。  
  
 在本操作方法主题中，你将完成以下步骤：  
  
-   创建转换路线服务实现 Microsoft BizTalk Server 映射路线的路由滑动。  
  
-   配置路线将已转换的消息路由到服务终结点。  
  
-   配置路线以返回到原始发送方的服务响应消息。  
  
-   测试路线使用路线测试客户端示例应用程序。  
  
## <a name="prerequisites"></a>先决条件  
 此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。  
  
## <a name="steps"></a>步骤  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>若要创建 ESB 路线 DSL 模型  
  
1.  在[!INCLUDE[vs2010](../includes/vs2010-md.md)]，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器，右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。  
  
3.  在**添加新项**对话框中，在**名称**框中，键入**请求响应**，然后单击**添加**。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>若要配置路线的属性  
  
1.  在 Visual Studio 中，单击的设计图面**RequestResponse.itinerary**。 在**请求响应**属性窗口中，配置以下属性：  
  
    1.  在**是请求响应**下拉列表中，单击**True**。  
  
    2.  在**模型导出程序**下拉列表中，单击**XML 路线导出程序**。  
  
    3.  在**扩展程序设置**部分，旁边**路线 XML 文件**属性，单击省略号按钮 （…）。  
  
    4.  在**选择 XML 文件**对话框中，在**文件名**框中，键入**C:\HowTos\Itineraries\RequestResponse**，然后单击**保存**。  
  
        > [!NOTE]
        >  此步骤允许您路线作为 XML 导出到本地文件位置。 通过到路线的数据库，而不导出到本地文件的位置，一条路线使测试路线使用 ESB 测试客户端应用程序。 你将完成本操作方法主题中后面此过程。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>若要定义路线的结构  
  
1.  从工具箱中，拖动**上负载增加**到设计图面上的模型元素。 在**OnRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**ReceiveNAOrder**。  
  
    2.  在**扩展程序**下拉列表中，单击**上负载增加 ESB 扩展程序**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
    4.  在**接收端口**下拉列表中，单击**OnRamp.Itinerary.Response**。  
  
2.  从工具箱中，拖动**路线服务**模型元素到设计图面，然后将其放到右侧**上负载增加**模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**MapNAOrderToCNOrder**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**消息传送扩展程序**。  
  
        > [!NOTE]
        >  此属性定义的过程将需要在管道 （消息传送） 中的位置。 或者，如果过程将需要一个业务流程中的位置，则设置**路线服务扩展程序**属性**Orchestration 扩展程序**。  
  
    3.  在**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。  
  
    4.  在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Transform**。  
  
3.  右键单击**冲突解决程序**集合**MapNAOrderToCNOrder**模型元素，并依次**添加新解析程序**。 在**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**StaticallySpecifyTheMap**。  
  
    2.  在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。  
  
    3.  在**转换类型**下拉列表中，单击**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**。  
  
4.  在工具箱中，单击**连接器**。 将从连接**ReceiveNAOrder**到模型元素**MapNAOrderToCNOrder**模型元素。  
  
5.  从工具箱中，拖动**路线服务**模型元素到设计图面，然后将其放到右侧**MapNAOrderToCNOrder**模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**RouteToCNService**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**消息传送扩展程序**。  
  
        > [!NOTE]
        >  此属性定义的过程将需要在管道 （消息传送） 中的位置。 或者，如果过程将需要一个业务流程中的位置，则设置**路线服务扩展程序**属性**Orchestration 扩展程序**。  
  
    3.  在**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。  
  
    4.  在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。  
  
6.  右键单击**冲突解决程序**集合**RouteToCNService**模型元素，并依次**添加新解析程序**。 在**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**StaticallySpecifyTheService**。  
  
    2.  在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。  
  
    3.  在**传输名称**下拉列表中，单击**WCF BasicHttp**。  
  
    4.  单击**传输位置**属性，再然后键入**http://localhost/ESB.CanadianServices/SubmitPOService.asmx**。  
  
    5.  单击**目标 Namespace**属性，再然后键入**http://globalbank.esb.dynamicresolution.com/canadianservices**。  
  
    6.  单击**操作**属性，再然后键入**将订单**。  
  
7.  在工具箱中，单击**连接器**。 将从连接**MapNAOrderToCNOrder**到模型元素**RouteToCNService**模型元素。  
  
8.  从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**RouteToCNService**模型元素。 在**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**InvokeCNService**。  
  
    2.  在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 扩展程序**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在**发送端口**下拉列表中，单击**DynamicResolutionSolicitResp**。  
  
9. 从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**RouteToCNService**模型元素和**InvokeCNService**模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SendPortFilter**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**关闭负载增加扩展程序**。  
  
    3.  在**关闭负载增加**下拉列表中，展开**InvokeCNService**，然后单击**发送处理程序**。  
  
10. 在工具箱中，单击**连接器**。 将从连接**RouteToCNService**到模型元素**SendPortFilter**模型元素。  
  
11. 在工具箱中，单击**连接器**。 将从连接**SendPortFilter**到模型元素**InvokeCNService**模型元素。  
  
12. 右键单击设计图面上，并依次**验证**。  
  
    > [!NOTE]
    >  路线验证;不需要返回到上负载增加连接关闭负载增加，以将响应消息发送回请求方。 通过使用双向入口，最后一条消息将自动返回给请求方。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>若要导出与路线测试客户端一起使用的模型  
  
1.  在 Visual Studio 中，右键单击的设计图面**请求响应**路线，，然后单击**导出模型**。  
  
    > [!NOTE]
    >  在 Visual Studio 中打开的 XML 版本的路线。  
  
2.  保存所有项目。  
  
3.  在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries。 请注意你路线 XML (RequestResponse.xml) 创建。  
  
#### <a name="to-test-the-itinerary"></a>若要测试路线  
  
1.  打开路线测试客户端示例应用程序使用期间创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。  
  
2.  在路线测试客户端中，清除**使用 WCF 服务**复选框。  
  
3.  在**Web 服务选项**部分中，选择**两个方式服务**复选框，并依次**负载路线**。  
  
4.  在**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。 选择**RequestResponse.xml**，然后单击**打开**加载路线。  
  
5.  单击**确定**清除**成功加载路线**消息。  
  
6.  在路线测试客户端上，单击旁边的省略号按钮 （...）**负载消息**框。  
  
7.  在**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。 选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。  
  
8.  单击**提交请求**按钮。 在测试完成后，单击**确定**关闭出现的确认。  
  
9. 在**结果**框中，注意到消息的根节点是**submitOrderResponse**的默认命名空间和...**canadianservices**。  
  
    > [!NOTE]
    >  如果响应消息响应发送到请求方之前需要其他转换，则必须使用包含 ESB 转发器组件的管道。 有关此功能的示例，请参阅[安装和运行多个 Web 服务示例](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [如何： 转换一条消息，并将生成的消息路由到使用路线的路由滑动某个文件位置](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [开发活动](../esb-toolkit/development-activities.md)  
  
-   [消息路由模式](../esb-toolkit/message-routing-patterns.md)  
  
-   [安装和运行多个 Web 服务示例](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)