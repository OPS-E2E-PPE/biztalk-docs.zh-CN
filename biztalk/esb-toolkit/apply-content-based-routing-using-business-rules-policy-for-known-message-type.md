---
title: "如何： 实现基于内容的路由使用业务规则的一个已知的消息类型的策略 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 44451c85-929a-4d13-b0dd-53ea600d0859
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b384c63b26f98a866390a001c7d7c2ec6f3f7cb2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-implement-content-based-routing-using-a-business-rules-policy-for-a-known-message-type"></a>如何： 实现基于内容的路由使用业务规则的一个已知的消息类型的策略
## <a name="goal"></a>目的  
 本部分演示如何创建动态路由消息，基于路线上一个已知的消息类型 （部署到 Microsoft BizTalk Server 配置数据库的架构） 的内容，使用业务规则策略。  
  
 在本操作方法主题中，你将完成以下步骤：  
  
-   创建业务规则策略将使用基于内容将消息路由。  
  
-   使用 BRE 解析程序将消息路由动态创建路线的路由滑动。  
  
-   测试路线使用路线测试客户端示例应用程序。  
  
## <a name="prerequisites"></a>先决条件  
 此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。  
  
## <a name="before-you-begin"></a>开始之前  
 本操作方法主题中的更高版本执行的步骤之前，请完成以下任务：  
  
-   创建 GlobalBank 西部测试消息。  
  
-   创建 GlobalBank 东部测试消息。  
  
 下面的过程介绍如何执行其中每个操作。  
  
#### <a name="to-create-the-globalbank-west-test-message"></a>若要创建 GlobalBank 西部测试消息  
  
1.  在 Windows 资源管理器，浏览到 C:\HowTos。  
  
2.  创建一份 NAOrderDoc.xml，并将其命名为复制 West.xml。  
  
3.  在记事本中，打开 West.xml，并将的值**customerName**元素**GlobalBankWest**。  
  
4.  将 West.xml 另存为 utf-8，，然后关闭记事本。  
  
#### <a name="to-create-the-globalbank-east-test-message"></a>若要创建 GlobalBank 东部测试消息  
  
1.  在 Windows 资源管理器，浏览到 C:\HowTos。  
  
2.  创建一份 NAOrderDoc.xml，并将其命名为复制 East.xml。  
  
3.  在记事本中，打开 East.xml，并将的值**customerName**元素**GlobalBankEast**。  
  
4.  将 East.xml 另存为 utf-8，，然后关闭记事本。  
  
## <a name="steps"></a>步骤  
  
#### <a name="to-create-a-bre-policy-to-route-using-custom-message-properties"></a>若要创建 BRE 策略来路由使用自定义消息属性  
 此规则将使用客户的动态设置用于将消息路由到的终结点。  
  
1.  单击**启动**在任务栏中，指向**所有程序**，指向 **[!INCLUDE[prague](../includes/prague-md.md)]** ，然后单击**业务规则编辑器**。  
  
2.  在策略资源管理器中，右键单击**策略**，然后单击**添加新策略**。 命名策略时**RouteBasedOnCustomerKnownType**。  
  
#### <a name="to-add-a-routing-rule-for-customer-globalbank-west"></a>若要添加客户 GlobalBank 西部的路由规则  
  
1.  在**RouteBasedOnCustomerKnownType**策略，右键单击**（不保存） 1.0 版**，然后单击**添加新规则**。 命名规则**SetWestEndpoint**。  
  
2.  在事实数据资源管理器，单击**XML 架构**选项卡上，右键单击**架构**，然后单击**浏览**。  
  
3.  在**架构文件**对话框中，浏览到 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB。DynamicResolution.Schemas，选择**NAOrderDoc.xsd**，然后单击**打开**。  
  
    > [!NOTE]
    >  这是定义 NAOrderDoc.xml 消息，用于创建将用于测试的西部和东部消息的架构。  
  
4.  在事实数据资源管理器，单击**NAOrderDoc.xsd**，然后在属性窗格中，单击**文档类型**属性，再然后键入**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.  
  
    > [!NOTE]
    >  这是架构的完全限定的名称。  
  
5.  在事实数据资源管理器中，展开**NAOrderDoc.xsd**，然后展开**OrderDoc**。  
  
6.  在规则窗口中，右键单击**条件**，指向**谓词**，然后单击**相等**。  
  
7.  从事实数据资源管理器拖动**customerName**元素**argument1**节点下的**条件**。  
  
8.  单击**argument2**节点，并键入**GlobalBankWest**。  
  
9. 在事实数据资源管理器，单击**词汇**选项卡上，展开**ESB。EndPointInfo**，然后展开**版本 1.0**。  
  
    > [!NOTE]
    >  [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括可以用于在 ESB 中创建使用规则的多个词汇。 其中一些应替换或扩充自己词汇。 例如， **DynamicRunTimeMaptypes**拥有中提供的映射用于定义**GlobalBank**示例。  
  
10. 从事实数据资源管理器拖动**设置终结点出站传输位置**定义与**操作**。  
  
11. 单击**\<空字符串 >**然后键入**C:\HowTos\Out\West%MessageID%.xml**。  
  
12. 从事实数据资源管理器拖动**设置终结点出站传输类型**定义与**操作**。  
  
13. 在事实数据资源管理器中，展开**ESB。TransportTypes**，展开**版本 1.0**，然后拖动**适配器提供程序**定义与**\<空字符串 >**。  
  
14. 在**操作**窗格中，展开**适配器提供程序**下拉列表，然后单击**文件**。  
  
#### <a name="to-add-a-routing-rule-for-customer-globalbank-east"></a>若要添加客户 GlobalBank 东部的路由规则  
  
1.  在策略资源管理器中，右键单击**SetWestEndpoint**规则，并依次**复制**。  
  
2.  右键单击**（不保存） 1.0 版**，然后单击**粘贴**。  
  
3.  在**新规则名称**对话框中，键入**SetEastEndpoint**，然后单击**确定**。  
  
4.  在策略资源管理器，单击**SetEastEndpoint**规则。  
  
5.  在**条件**部分中，右键单击**GlobalBankWest**，然后单击**重置参数**。  
  
6.  单击**argument2**，然后键入**GlobalBankEast**。  
  
7.  在**操作**部分中，右键单击**C:\HowTos\Out\West%MessageID%.xml**，然后单击**重置参数**。  
  
8.  单击**\<空字符串 >**，然后键入**C:\HowTos\Out\East%MessageID%.xml**。  
  
#### <a name="to-add-a-routing-rule-for-unknown-customers"></a>若要为未知客户添加一个路由规则  
  
1.  在 RouteBasedOnCustomerKnownType 策略中，右键单击 （不保存），版本 1.0，然后单击添加新规则。 命名规则 SetUnknownCustomerEndpoint。  
  
2.  在规则窗口中，右键单击条件，，然后单击添加逻辑 and。  
  
3.  在规则窗口中，右键单击，指向谓词，，然后单击 NotEqual。  
  
4.  在事实数据资源管理器中，单击 XML 架构选项卡，展开 NAOrderDoc.xsd，，然后展开 OrderDoc。  
  
5.  从事实数据资源管理器中，将 customerName 元素拖到条件下的 argument1 节点。  
  
6.  单击 argument2 节点，然后键入 GlobalBankWest。  
  
7.  在规则窗口中，右键单击，指向谓词，，然后单击 NotEqual。  
  
8.  从事实数据资源管理器中，将 customerName 元素拖到条件下的 argument1 节点。  
  
9. 单击 argument2 节点，然后键入 GlobalBankEast。  
  
10. 在事实数据资源管理器，单击词汇选项卡中，展开 ESB。EndPointInfo，然后展开版本 1.0。  
  
11. 从事实数据资源管理器中，将设置终结点出站传输位置定义拖动到操作。  
  
12. 单击\<空字符串 >，然后键入 C:\HowTos\Out\CustomerUnknown%MessageID%.xml。  
  
13. 从事实数据资源管理器中，将设置终结点出站传输类型定义拖动到操作。  
  
14. 在事实数据资源管理器中，展开 ESB。TransportTypes，展开版本 1.0，然后拖动到的适配器提供程序定义\<空字符串 >。  
  
15. 在操作窗格中，展开适配器提供程序下拉列表中，，然后单击文件。  
  
#### <a name="to-publish-and-deploy-the-policy"></a>若要发布和部署策略  
  
1.  在策略资源管理器下**RouteBasedOnCustomerKnownType**策略中，右击**（不保存） 1.0 版**，然后单击**发布**。  
  
2.  在策略资源管理器下**RouteBasedOnCustomerKnownType**策略中，右击**版本 1.0-发布**，然后单击**部署**。  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>若要创建 ESB 路线 DSL 模型  
  
1.  在[!INCLUDE[vs2010](../includes/vs2010-md.md)]，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器，右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。  
  
3.  在**添加新项**对话框中，在**名称**框中，键入**CbrKnownType**，然后单击**添加**。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>若要配置路线的属性  
  
1.  在 Visual Studio 中，单击的设计图面**CbrKnownType.itinerary**。 在**CbrKnownType**属性窗口中，配置以下属性：  
  
    1.  在**模型导出程序**下拉列表中，单击**XML 路线导出程序**。  
  
    2.  在**扩展程序设置**部分，旁边**路线 XML 文件**属性，单击省略号按钮 （…）。  
  
    3.  在**选择 XML 文件**对话框中，键入**C:\HowTos\Itineraries\CbrKnownType**中**文件名**框中，并依次**保存**。  
  
        > [!NOTE]
        >  此步骤允许您路线作为 XML 导出到本地文件位置。 通过到路线的数据库，而不导出到本地文件的位置，一条路线使测试路线使用 ESB 测试客户端应用程序。 你将完成本操作方法主题中后面此过程。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>若要定义路线的结构  
  
1.  从工具箱中，拖动**上负载增加**到设计图面上的模型元素。 在**OnRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**ReceiveNAOrder**。  
  
    2.  在**扩展程序**下拉列表中，单击**上负载增加 ESB 扩展程序**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
    4.  在**接收端口**下拉列表中，单击**OnRamp.Itinerary**。  
  
2.  从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**ReceiveNAOrder**模型元素。 在**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SendRegionalOrders**。  
  
    2.  在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 扩展程序**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。  
  
3.  从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**ReceiveNAOrder**模型元素和**SendRegionalOrders**模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SendPortFilter**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**关闭负载增加扩展程序**。  
  
    3.  在**关闭负载增加**下拉列表中，展开**SendRegionalOrders**，然后单击**发送处理程序**。  
  
4.  右键单击**冲突解决程序**集合**SendPortFilter**模型元素，并依次**添加新解析程序**。 在**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**RouteRegionalOrders**。  
  
    2.  在**传输名称**下拉列表中，单击**BRE**。  
  
    3.  在**解析程序实现**下拉列表中，单击**Bre 冲突解决程序扩展**。  
  
    4.  在**策略**下拉列表中，单击**RouteBasedOnCustomerKnownType**。  
  
    5.  在**识别消息格式**下拉列表中，单击**True**。  
  
    6.  在**UseMsg**下拉列表中，单击**True**。  
  
        > [!NOTE]
        >  如果你使用从业务流程，BRE 冲突解决程序扩展**recognizeMessageFormat**属性必须设置为**False**。  
  
5.  在工具箱中，单击**连接器**。 将从连接**ReceiveNAOrder**到模型元素**SendPortFilter**模型元素。  
  
6.  在工具箱中，单击**连接器**。 将从连接**SendPortFilter**到模型元素**SendRegionalOrders**模型元素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>若要导出与路线测试客户端一起使用的模型  
  
1.  在 Visual Studio 中，右键单击的设计图面**CbrKnownType**路线，，然后单击**导出模型**。  
  
    > [!NOTE]
    >  在 Visual Studio 中打开的 XML 版本的路线。  
  
2.  保存所有项目。  
  
3.  在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries，并注意你路线 XML (CbrKnownType.xml) 创建。  
  
#### <a name="to-test-the-itinerary-and-business-rules"></a>若要测试的路线和业务规则  
  
1.  打开路线测试客户端示例应用程序使用期间创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。  
  
2.  在路线测试客户端中，清除**使用 WCF 服务**复选框，并依次**负载路线**。  
  
3.  在**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。 选择**CbrKnownType.xml**，然后单击**打开**加载路线。  
  
4.  单击**确定**清除**成功加载路线**消息。  
  
5.  在路线测试客户端上，单击旁边的省略号按钮 （...）**负载消息**框。  
  
6.  在**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。 选择**West.xml**，然后单击**打开**加载测试消息。  
  
7.  单击**提交请求**按钮。 在测试完成后，单击**确定**关闭出现的确认。  
  
8.  在 Windows 资源管理器，浏览到 C:\HowTos\Out。验证 West%MessageID%.xml 消息已写入到目录。  
  
9. 重复使用 East.xml 消息在测试过程。  
  
10. 在 Windows 资源管理器，浏览到 C:\HowTos\Out。验证 East%MessageID%.xml 消息已写入到目录。  
  
11. 重复使用 NAOrderDoc.xml 消息在测试过程。  
  
12. 在 Windows 资源管理器，浏览到 C:\HowTos\Out。验证 CustomerUnknown%MessageID%.xml 消息已写入到目录。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [如何： 选择使用业务规则策略路线](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [如何： 动态路由基于消息上下文使用业务规则策略在一条消息](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
-   [开发活动](../esb-toolkit/development-activities.md)  
  
-   [消息路由模式](../esb-toolkit/message-routing-patterns.md)