---
title: 如何： 将一条消息路由到多个收件人使用路线路由的滑动 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 42c30493-4fe1-4fd5-8bc7-af091535b091
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c493b33081e540a4e18d6d20e4813cdddad894a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010470"
---
# <a name="how-to-route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip"></a>如何： 将一条消息路由到多个收件人使用路线路由的滑动
## <a name="goal"></a>目的  
 本部分演示如何使用设计器域特定语言 (DSL) 来创建一条路线，将消息路由到使用静态的解析程序和 BizTalk Server 文件适配器的三个不同的收件人。  
  
 在本操作方法主题中，你将完成以下步骤：  
  
-   使用消息路由到多个收件人的三个静态解析程序创建一条路线。  
  
-   测试路线使用路线测试客户端示例应用程序。  
  
## <a name="prerequisites"></a>先决条件  
 此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。  
  
## <a name="steps"></a>步骤  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>若要创建 ESB 路线 DSL 模型  
  
1.  在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器，右键单击**ItineraryLibrary**，指向**添加**，然后单击**新路线**。  
  
3.  在**添加新项**对话框中，单击**ItineraryDsl**在模板窗格中。  
  
4.  在**名称**框中，键入**RecipientList**，然后单击**添加**。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>若要配置路线的属性  
  
1.  在 Visual Studio 中，单击 RecipientList.itinerary 的设计图面。 在 RecipientList 属性窗口中，配置以下属性：  
  
    1.  在**模型导出程序**下拉列表中，单击**XML 路线导出程序**。  
  
    2.  在**扩展程序设置**部分，旁边**路线 XML 文件**属性，单击省略号按钮 （…）。  
  
    3.  在**选择 XML 文件**对话框中，在**文件名**框中，键入**C:\HowTos\Itineraries\RecipientList**，然后单击**保存**。  
  
        > [!NOTE]
        >  此步骤允许您路线作为 XML 导出到本地文件位置。 通过到路线的数据库，而不导出到本地文件的位置，一条路线使测试路线使用 ESB 测试客户端应用程序。 你将完成本操作方法主题中后面此过程。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>若要定义路线的结构  
  
1.  从工具箱中，拖动**上负载增加**到设计图面上的模型元素。 在**OnRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**ReceiveNAOrder**。  
  
    2.  在**扩展程序**下拉列表中，单击**上负载增加扩展程序**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
    4.  在**接收端口**下拉列表中，单击**OnRamp.Itinerary**。  
  
2.  从工具箱中，拖动**路线服务**模型元素到设计图面，然后将其放到右侧**上负载增加**模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**RouteToThreeRecipients**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**消息传送扩展程序**。  
  
        > [!NOTE]
        >  此属性定义的过程将需要在管道 （消息传送） 中的位置。 或者，如果过程将需要一个业务流程中的位置，则设置**路线服务扩展程序**属性**Orchestration 扩展程序**。  
  
    3.  在**容器**下拉列表中，展开**ReceiveNaOrderDoc**，然后单击**接收处理程序**。  
  
    4.  在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。  
  
3.  右键单击**冲突解决程序**集合**RouteToThreeRecipients**模型元素，并依次**添加新解析程序**。 在**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**FirstResolver**。  
  
    2.  在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。  
  
    3.  在**传输名称**下拉列表中，单击**文件**。  
  
    4.  单击**传输位置**属性，再然后键入**C:\HowTos\Out\First%MessageID%.xml**。  
  
        > [!NOTE]
        >  你已经添加此路线服务的三个冲突解决程序的第一个。 现在，您将添加两个详细的解析程序，来将消息路由到其他收件人。  
  
4.  右键单击**冲突解决程序**集合**RouteToThreeRecipients**模型元素，并依次**添加新解析程序**。 在**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SecondResolver**。  
  
    2.  在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。  
  
    3.  在**传输名称**下拉列表中，单击**文件**。  
  
    4.  单击**传输位置**属性，再然后键入**C:\HowTos\Out\Second%MessageID%.xml**。  
  
5.  右键单击**冲突解决程序**集合**RouteToThreeRecipients**模型元素，并依次**添加新解析程序**。 在**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**ThirdResolver**。  
  
    2.  在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。  
  
    3.  在**传输名称**下拉列表中，单击**文件**。  
  
    4.  单击**传输位置**属性，再然后键入**C:\HowTos\Out\Third%MessageID%.xml**。  
  
6.  在工具箱中，单击**连接器**。 将从连接**ReceiveNAOrder**到模型元素**RouteToThreeRecipients**模型元素。  
  
7.  从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**RouteToThreeRecipients**模型元素。 在**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SendThreeMessages**。  
  
    2.  在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 扩展程序**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。  
  
8.  从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**RouteToThreeRecipients**模型元素和**SendThreeMessages**模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SendPortFilter**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**关闭负载增加扩展程序**。  
  
    3.  在**关闭负载增加**下拉列表中，展开**SendThreeMessages**，然后单击**发送处理程序**。  
  
9. 在工具箱中，单击**连接器**。 将从连接**RouteToThreeRecipients**到模型元素**SendPortFilter**模型元素。  
  
10. 在工具箱中，单击**连接器**。 将从连接**SendPortFilter**到模型元素**SendThreeMessages**模型元素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>若要导出与路线测试客户端一起使用的模型  
  
1.  在 Visual Studio 中，右键单击的设计图面**RecipientList**路线，，然后单击**导出模型**。  
  
    > [!NOTE]
    >  在 Visual Studio 中打开的 XML 版本的路线。  
  
2.  保存所有项目。  
  
3.  在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries，，然后记下你路线 XML (RecipientList.xml) 创建。  
  
#### <a name="to-test-the-itinerary"></a>若要测试路线  
  
1.  打开路线测试客户端示例应用程序使用期间创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。  
  
2.  在路线测试客户端中，清除**使用 WCF 服务**复选框，并依次**负载路线**。  
  
3.  在**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。 选择**RecipientList.xml**，然后单击**打开**加载路线。  
  
4.  单击**确定**以清除"路线成功加载： 消息。  
  
5.  在路线测试客户端上，单击旁边的省略号按钮 （...）**负载消息**框。  
  
6.  在**选择要加载 XML 文档**对话框中，浏览到 C:\Patterns。 选择 NAOrderDoc.xml，，然后单击**打开**加载测试消息。  
  
7.  单击**提交请求**按钮。 在测试完成后，单击**确定**关闭出现的确认。  
  
8.  在 Windows 资源管理器，浏览到 C:\HowTos\Out\\。 验证目录中已写的以下消息：  
  
    -   First%MessageID%.xml  
  
    -   Second%MessageID%.xml  
  
    -   Third%MessageID%.xml  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [开发活动](../esb-toolkit/development-activities.md)  
  
-   [消息路由模式](../esb-toolkit/message-routing-patterns.md)  
  
-   [使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)