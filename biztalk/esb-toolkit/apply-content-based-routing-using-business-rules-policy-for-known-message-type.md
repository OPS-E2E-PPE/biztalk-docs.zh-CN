---
title: 如何： 实现基于内容的路由使用业务规则策略为已知的消息类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44451c85-929a-4d13-b0dd-53ea600d0859
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7b47fd54aaf6dc93ed26ba7efec3b14bf31401e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004910"
---
# <a name="how-to-implement-content-based-routing-using-a-business-rules-policy-for-a-known-message-type"></a>如何： 实现基于内容的路由使用业务规则策略为已知的消息类型
## <a name="goal"></a>目的  
 本部分演示如何创建动态路由基于消息的路线上已知的消息类型 （架构部署到 Microsoft BizTalk Server 配置数据库） 的内容，使用业务规则策略。  
  
 在本操作指南主题中，您将完成以下步骤：  
  
-   创建将用于基于内容将消息路由的业务规则策略。  
  
-   使用 BRE 冲突解决程序以动态方式路由消息创建路线传送名单。  
  
-   测试使用路线测试客户端示例应用程序的路线。  
  
## <a name="prerequisites"></a>必要條件  
 本操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。  
  
## <a name="before-you-begin"></a>开始之前  
 在本操作指南主题的后面部分执行的步骤之前，请完成以下任务：  
  
- 创建 GlobalBank 西部测试消息。  
  
- 创建 GlobalBank 东部测试消息。  
  
  以下过程介绍如何执行其中每项功能。  
  
#### <a name="to-create-the-globalbank-west-test-message"></a>若要创建 GlobalBank 西部测试消息  
  
1.  在 Windows 资源管理器，浏览到 C:\HowTos。  
  
2.  创建一份 NAOrderDoc.xml，并将其命名为 West.xml 的副本。  
  
3.  在记事本中，打开 West.xml，并更改的值**customerName**元素**GlobalBankWest**。  
  
4.  将 West.xml 另存为 utf-8，，然后关闭记事本。  
  
#### <a name="to-create-the-globalbank-east-test-message"></a>若要创建 GlobalBank 东部测试消息  
  
1.  在 Windows 资源管理器，浏览到 C:\HowTos。  
  
2.  创建一份 NAOrderDoc.xml，并将其命名为 East.xml 的副本。  
  
3.  在记事本中，打开 East.xml，并更改的值**customerName**元素**GlobalBankEast**。  
  
4.  将 East.xml 另存为 utf-8，，然后关闭记事本。  
  
## <a name="steps"></a>步骤  
  
#### <a name="to-create-a-bre-policy-to-route-using-custom-message-properties"></a>若要创建 BRE 策略路由使用自定义消息属性  
 此规则将使用客户的名称来动态地设置用于将消息路由的终结点。  
  
1.  单击**启动**在任务栏上，依次指向**所有程序**，指向**BizTalk Server**，然后单击**业务规则编辑器**。  
  
2.  在策略浏览器中右键单击**策略**，然后单击**添加新策略**。 将策略命名**RouteBasedOnCustomerKnownType**。  
  
#### <a name="to-add-a-routing-rule-for-customer-globalbank-west"></a>若要添加的路由规则，客户 GlobalBank 西部  
  
1. 在中**RouteBasedOnCustomerKnownType**策略中，右键单击**版本 1.0 （未保存）**，然后单击**添加新规则**。 命名规则**SetWestEndpoint**。  
  
2. 在事实浏览器中单击**XML 架构**选项卡上，右键单击**架构**，然后单击**浏览**。  
  
3. 在中**架构文件**对话框中，浏览到 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB。DynamicResolution.Schemas，选择**NAOrderDoc.xsd**，然后单击**打开**。  
  
   > [!NOTE]
   >  这是定义 NAOrderDoc.xml 消息，用于创建将用于测试的左和右消息的架构。  
  
4. 在事实浏览器中单击**NAOrderDoc.xsd**，然后在属性窗格中，单击**文档类型**属性，并键入**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.  
  
   > [!NOTE]
   >  这是架构的完全限定的名称。  
  
5. 在事实浏览器中，展开**NAOrderDoc.xsd**，然后展开**OrderDoc**。  
  
6. 在规则窗口中，右键单击**条件**，依次指向**谓词**，然后单击**相等**。  
  
7. 从事实浏览器中，将**customerName**元素**argument1**节点下的**条件**。  
  
8. 单击**argument2**节点，并键入**GlobalBankWest**。  
  
9. 在事实浏览器中单击**词汇**选项卡上，展开**ESB。EndPointInfo**，然后展开**版本 1.0**。  
  
   > [!NOTE]
   >  [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括几个可用于在 ESB 中创建使用规则的词汇。 其中一些应替换或扩充了自己的词汇。 例如， **DynamicRunTimeMaptypes**具有中提供的映射的定义**GlobalBank**示例。  
  
10. 从事实浏览器中，将**设置终结点出站传输位置**定义**操作**。  
  
11. 单击**\<空字符串\>** ，然后键入**C:\HowTos\Out\West%MessageID%.xml**。  
  
12. 从事实浏览器中，将**设置终结点出站传输类型**定义**操作**。  
  
13. 在事实浏览器中展开**ESB。TransportTypes**，展开**版本 1.0**，然后将拖**适配器提供程序**定义**\<空字符串\>**.  
  
14. 在中**操作**窗格中，展开**适配器提供程序**下拉列表，再单击**文件**。  
  
#### <a name="to-add-a-routing-rule-for-customer-globalbank-east"></a>若要添加的路由规则，客户 GlobalBank 东部  
  
1.  在策略浏览器中右键单击**SetWestEndpoint**规则，然后依次**副本**。  
  
2.  右键单击**版本 1.0 （未保存）**，然后单击**粘贴**。  
  
3.  在中**新建规则名称**对话框中，键入**SetEastEndpoint**，然后单击**确定**。  
  
4.  在策略浏览器中单击**SetEastEndpoint**规则。  
  
5.  在中**条件**部分中，右键单击**GlobalBankWest**，然后单击**重置参数**。  
  
6.  单击**argument2**，然后键入**GlobalBankEast**。  
  
7.  在中**操作**部分中，右键单击**C:\HowTos\Out\West%MessageID%.xml**，然后单击**重置参数**。  
  
8.  单击**\<空字符串\>**，然后键入**C:\HowTos\Out\East%MessageID%.xml**。  
  
#### <a name="to-add-a-routing-rule-for-unknown-customers"></a>若要为未知客户添加路由规则  
  
1.  在 RouteBasedOnCustomerKnownType 策略中，右键单击版本 1.0 （未保存），然后单击添加新规则。 命名规则 SetUnknownCustomerEndpoint。  
  
2.  在规则窗口中，右键单击条件，然后单击添加逻辑 and。  
  
3.  在规则窗口中，右键单击，指向谓词，，然后单击 NotEqual。  
  
4.  在事实浏览器中，依次单击 XML 架构选项卡、 NAOrderDoc.xsd，和 OrderDoc。  
  
5.  从事实浏览器中，将 customerName 元素拖到条件下的 argument1 节点。  
  
6.  单击参数 2 节点，然后键入 GlobalBankWest。  
  
7.  在规则窗口中，右键单击，指向谓词，，然后单击 NotEqual。  
  
8.  从事实浏览器中，将 customerName 元素拖到条件下的 argument1 节点。  
  
9. 单击参数 2 节点，然后键入 GlobalBankEast。  
  
10. 在事实浏览器中，单击词汇选项卡，展开 ESB。EndPointInfo，然后展开版本 1.0。  
  
11. 从事实浏览器中，将设置终结点出站传输位置定义拖动到操作。  
  
12. 单击\<空字符串\>，然后键入 C:\HowTos\Out\CustomerUnknown%MessageID%.xml。  
  
13. 从事实浏览器中，将设置终结点出站传输类型定义拖动到操作。  
  
14. 在事实浏览器中展开 ESB。TransportTypes，展开版本 1.0，并将该适配器提供程序定义\<空字符串\>。  
  
15. 在操作窗格中，展开适配器提供程序下拉列表，然后单击文件。  
  
#### <a name="to-publish-and-deploy-the-policy"></a>若要发布和部署策略  
  
1.  在策略浏览器下**RouteBasedOnCustomerKnownType**策略中，右键单击**版本 1.0 （未保存）**，然后单击**发布**。  
  
2.  在策略浏览器下**RouteBasedOnCustomerKnownType**策略中，右键单击**版本 1.0-已发布**，然后单击**部署**。  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>若要创建的 ESB 路线 DSL 模型  
  
1.  在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器中右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。  
  
3.  在中**添加新项**对话框中**名称**框中，键入**CbrKnownType**，然后单击**添加**。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>若要配置的路线属性  
  
1.  在 Visual Studio 中，单击的设计图面**CbrKnownType.itinerary**。 在中**CbrKnownType**属性窗口中，配置以下属性：  
  
    1.  在中**模型导出程序**下拉列表中，单击**XML 路线导出程序**。  
  
    2.  在中**扩展器设置**部分中下, 一步**路线 XML 文件**属性中，单击省略号按钮 （...）。  
  
    3.  在中**选择 XML 文件**对话框中，键入**C:\HowTos\Itineraries\CbrKnownType**中**文件名**框，并单击**保存**。  
  
        > [!NOTE]
        >  此步骤中，可将路线以 XML 形式导出到本地文件位置。 通过为行程数据库，而不导出到本地文件的位置，路线，路线使用 ESB 测试客户端应用程序的测试。 您将完成此过程更高版本的本操作指南主题。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>若要定义路线的结构  
  
1.  从工具箱拖动**接入点**至设计图面上的模型元素。 在中**OnRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**ReceiveNAOrder**。  
  
    2.  在中**Extender**下拉列表中，单击**接入点 ESB 扩展器**。  
  
    3.  在中**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
    4.  在中**接收端口**下拉列表中，单击**OnRamp.Itinerary**。  
  
2.  从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**ReceiveNAOrder**模型元素。 在中**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**SendRegionalOrders**。  
  
    2.  在**Extender**下拉列表中，单击**关闭负载增加 ESB 扩展器**。  
  
    3.  在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在中**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。  
  
3.  从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**ReceiveNAOrder**模型元素和**SendRegionalOrders**模型元素。 在中**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**SendPortFilter**。  
  
    2.  在**路线服务 Extender**下拉列表中，单击**接入点关闭扩展器**。  
  
    3.  在中**关闭负载增加**下拉列表中，展开**SendRegionalOrders**，然后单击**发送处理程序**。  
  
4.  右键单击**冲突解决程序**系列**SendPortFilter**模型元素，然后单击**添加新解析程序**。 在中**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**RouteRegionalOrders**。  
  
    2.  在中**传输名称**下拉列表中，单击**BRE**。  
  
    3.  在中**解析程序实现**下拉列表中，单击**Bre 冲突解决程序扩展**。  
  
    4.  在中**策略**下拉列表中，单击**RouteBasedOnCustomerKnownType**。  
  
    5.  在中**识别消息格式**下拉列表中，单击**True**。  
  
    6.  在中**UseMsg**下拉列表中，单击**True**。  
  
        > [!NOTE]
        >  如果使用 BRE 冲突解决程序扩展业务流程中，从**recognizeMessageFormat**属性必须设置为**False**。  
  
5.  在工具箱中，单击**连接器**。 将从连接**ReceiveNAOrder**到模型元素**SendPortFilter**模型元素。  
  
6.  在工具箱中，单击**连接器**。 将从连接**SendPortFilter**到模型元素**SendRegionalOrders**模型元素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>若要导出与路线测试客户端一起使用的模型  
  
1.  在 Visual Studio 中，右键单击设计图面的**CbrKnownType**路线，并单击**导出模型**。  
  
    > [!NOTE]
    >  在 Visual Studio 中打开的 XML 版本的路线。  
  
2.  保存项目的所有项目。  
  
3.  在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries 并请注意，您的路线 XML (CbrKnownType.xml) 创建。  
  
#### <a name="to-test-the-itinerary-and-business-rules"></a>若要测试的路线和业务规则  
  
1.  打开路线测试客户端示例应用程序使用过程中创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。  
  
2.  在路线测试客户端，清除**使用 WCF 服务**复选框，然后依次**负载路线**。  
  
3.  在中**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。 选择**CbrKnownType.xml**，然后单击**打开**加载路线。  
  
4.  单击**确定**清除**成功加载路线**消息。  
  
5.  在路线测试客户端，单击下一步的省略号按钮 （...）**负载消息**框。  
  
6.  在中**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。 选择**West.xml**，然后单击**打开**加载测试消息。  
  
7.  单击**提交请求**按钮。 测试完成后，单击**确定**若要消除出现的确认。  
  
8.  在 Windows 资源管理器，浏览到 C:\HowTos\Out。验证 West%MessageID%.xml 消息已写入到目录。  
  
9. 重复使用 East.xml 消息的测试过程。  
  
10. 在 Windows 资源管理器，浏览到 C:\HowTos\Out。验证 East%MessageID%.xml 消息已写入到目录。  
  
11. 重复使用 NAOrderDoc.xml 消息的测试过程。  
  
12. 在 Windows 资源管理器，浏览到 C:\HowTos\Out。验证 CustomerUnknown%MessageID%.xml 消息已写入到目录。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [如何：使用业务规则策略选择路线](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [如何：使用业务规则策略动态路由基于消息上下文的消息](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
-   [开发活动](../esb-toolkit/development-activities.md)  
  
-   [消息路由模式](../esb-toolkit/message-routing-patterns.md)