---
title: 如何：转换消息并将生成的消息路由到使用路线传送名单的文件位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c27749ba-c228-4cd4-827e-e8009a0c999d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e671e48ea2da80783b714a8be6c503b80b95f27
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399664"
---
# <a name="how-to-transform-a-message-and-route-the-resulting-message-to-a-file-location-using-an-itinerary-routing-slip"></a>如何：转换消息并将生成的消息路由到使用路线传送名单的文件位置
## <a name="goal"></a>目的  
 本部分演示如何使用 ESB 设计器特定于域的语言 (DSL) 来创建路线通过调用 BizTalk 映射时，实现消息转换，然后使用消息路由[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]文件适配器。  
  
 在本操作指南主题中，您将完成以下步骤：  
  
-   使用实现了一个 BizTalk 映射转换路线服务创建路线传送名单。  
  
-   配置路线以便将转换后的消息路由到某个文件位置。  
  
-   测试使用路线测试客户端示例应用程序的路线。  
  
## <a name="prerequisites"></a>先决条件  
 本操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。  
  
## <a name="steps"></a>步骤  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>若要创建的 ESB 路线 DSL 模型  
  
1.  在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器中右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。  
  
3.  在中**添加新项**对话框中，单击**ItineraryDsl**模板窗格中。  
  
4.  在中**名称**框中，键入**DataModelTransformation**，然后单击**添加**。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>若要配置的路线属性  
  
1.  在 Visual Studio 中，单击的设计图面**DataModelTransformation.itinerary**。 在中**DataModelTransformation**属性窗口中，配置以下属性：  
  
    1.  在中**模型导出程序**下拉列表中，单击**XML 路线导出程序**。  
  
    2.  在中**扩展器设置**部分中下, 一步**路线 XML 文件**属性中，单击省略号按钮 （...）。  
  
    3.  在中**选择 XML 文件**对话框中**文件名**框中，键入**C:\HowTos\Itineraries\DataModelTransformation**，然后单击**保存**.  
  
        > [!NOTE]
        >  此步骤中，可将路线以 XML 形式导出到本地文件位置。 通过为行程数据库，而不导出到本地文件的位置，路线，路线使用 ESB 测试客户端应用程序的测试。 您将完成此过程更高版本的本操作指南主题。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>若要定义路线的结构  
  
1.  从工具箱拖动**接入点**至设计图面上的模型元素。 在中**OnRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**ReceiveNAOrder**。  
  
    2.  在中**Extender**下拉列表中，单击**接入点 ESB 服务扩展**。  
  
    3.  在中**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
    4.  在中**接收端口**下拉列表中，单击**OnRamp.Itinerary**。  
  
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
  
    4.  在中**传输名称**下拉列表中，单击**文件**。  
  
4.  在工具箱中，单击**连接器**。 将从连接**ReceiveNAOrder**到模型元素**MapNAOrderToCNOrder**模型元素。  
  
5.  从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**MapNAOrderToCNOrder**模型元素。 在中**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**SendCNOrder**。  
  
    2.  在**Extender**下拉列表中，单击**关闭负载增加 ESB 扩展器**。  
  
    3.  在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在中**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。  
  
6.  从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**MapNAOrderToCNOrder**模型元素和**SendCNOrder**模型元素。 在中**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**SendPortFilter**。  
  
    2.  在**路线服务 Extender**下拉列表中，单击**接入点关闭扩展器**。  
  
    3.  在中**关闭负载增加**下拉列表中，展开**SendCNOrder**，然后单击**发送处理程序**。  
  
7.  右键单击**冲突解决程序**系列**SendPortFilter**模型元素，然后单击**添加新解析程序**。 在中**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**ConfigureFolderSettings**。  
  
    2.  在中**传输名称**下拉列表中，单击**文件**。  
  
    3.  单击**传输位置**属性，并键入**C:\HowTos\Out\\%MessageID%.xml**。  
  
        > [!NOTE]
        >  每个关闭接入点将具有与它; 关联的路线服务路线服务属性和关闭负载增加的属性的组合定义的动态发送端口的订阅。  
  
8.  在工具箱中，单击**连接器**。 将从连接**MapNAOrderToCNOrder**到模型元素**SendPortFilter**模型元素。  
  
9. 在工具箱中，单击**连接器**。 将从连接**SendPortFilter**到模型元素**SendCNOrder**模型元素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>若要导出与路线测试客户端一起使用的模型  
  
1.  在 Visual Studio 中，右键单击设计图面的**DataModelTransformation**路线，并单击**导出模型**。  
  
    > [!NOTE]
    >  在 Visual Studio 中打开的 XML 版本的路线。  
  
2.  保存项目的所有项目。  
  
3.  在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries 并请注意，您的路线 XML (DataModelTransformation.xml) 创建。  
  
#### <a name="to-test-the-itinerary"></a>若要测试路线  
  
1.  打开路线测试客户端示例应用程序使用过程中创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。  
  
2.  在路线测试客户端，清除**使用 WCF 服务**复选框，然后依次**负载路线**。  
  
3.  在中**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。 选择**DataModelTransformation.xml**，然后单击**打开**加载路线。  
  
4.  单击**确定**清除**成功加载路线**消息。  
  
5.  在路线测试客户端，单击下一步的省略号按钮 （...）**负载消息**框。  
  
6.  在中**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。 选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。  
  
7.  单击**提交请求**按钮。 测试完成后，单击**确定**若要消除出现的确认。  
  
8.  在 Windows 资源管理器，浏览到 C:\HowTos\Out。确认 **%MessageID%.xml**消息已写入到的目录。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅以下相关主题：  
  
1.  [如何：将某个交换拆分，并将结果的消息路由到多个使用不同的路线的文件位置](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)  
  
2.  [开发活动](../esb-toolkit/development-activities.md)  
  
3.  [消息转换模式](../esb-toolkit/message-transformation-patterns.md)