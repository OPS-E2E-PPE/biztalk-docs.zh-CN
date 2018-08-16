---
title: 如何： 选择使用业务规则策略路线 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f6373a8-d9d6-46c6-95e3-f62dd33c342a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12496da0de4057e96be0b714ad1af048ee6b8ef1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976958"
---
# <a name="how-to-select-an-itinerary-using-a-business-rules-policy"></a>如何： 选择使用业务规则策略路线
## <a name="goal"></a>目的  
 本部分演示如何创建可用于选择路线根据收到的消息的内容的业务规则以及如何配置路线选择器管道组件中泛型路线接入点来调用这些规则。 本部分介绍业务方案中的消息路由以不同的方式，根据客户所在的区域。  
  
 在本操作指南主题中，您将完成以下步骤：  
  
-   有关客户 Global Bank 的西欧和美国东部部门的模型路线。  
  
-   创建将用于选择用于处理请求路线的业务规则策略。  
  
-   配置路线选择器管道组件以使用业务规则策略选择适当的路线。  
  
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
  
#### <a name="to-create-a-business-rules-engine-bre-policy-to-select-an-itinerary-using-custom-message-properties"></a>若要创建业务规则引擎 (BRE) 策略来选择使用自定义消息属性路线  
  
1.  单击**启动**在任务栏上，依次指向**所有程序**，指向**BizTalk Server**，然后单击**业务规则编辑器**。  
  
2.  在策略浏览器中右键单击**策略**，然后单击**添加新策略**。 将策略命名**ResolveItineraryBasedOnCustomer**。  
  
    > [!NOTE]
    >  本操作指南主题的主题中创建使用相同的业务规则策略和路线[如何： 拆分交换并将生成的消息路由到多个文件的位置使用不同的路线](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)。 如果你已完成该部分，可以跳过本主题中后面到过程中，"以创建和配置 ESB 接入点"。  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-west"></a>若要添加客户 GlobalBank 西部选择规则  
  
1.  在中**ResolveItineraryBasedOnCustomer**策略中，右键单击**版本 1.0 （未保存）**，然后单击**添加新规则**。 命名规则**SetGlobalBankWestItinerary**。  
  
2.  在事实浏览器中单击**XML 架构**选项卡上，右键单击**架构**，然后单击**浏览**。  
  
3.  在中**架构文件**对话框中，浏览到 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB。DynamicResolution.Schemas，选择**NAOrderDoc.xsd**，然后单击**打开**。  
  
    > [!NOTE]
    >  这是定义 NAOrderDoc.xml 消息，用于创建将用于测试的左和右消息的架构。  
  
4.  在事实浏览器中单击**NAOrderDoc.xsd**，单击**文档类型**属性中为属性窗格，然后按**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.  
  
    > [!NOTE]
    >  这是架构的完全限定的名称。  
  
5.  在事实浏览器中，展开**NAOrderDoc.xsd**，然后展开**OrderDoc**。  
  
6.  在规则窗口中，右键单击**条件**，依次指向**谓词**，然后单击**相等**。  
  
7.  从事实浏览器中，将**customerName**元素**argument1**节点下的**条件**。  
  
8.  单击**argument2**节点，并键入**GlobalBankWest**。  
  
9. 在事实浏览器中单击**词汇**选项卡。展开**ESB。路线**词汇，展开**版本 1.1**，然后将拖**集路线名称**定义**操作**。  
  
10. 单击**\<空字符串\>**，然后键入**GlobalBankWestItinerary**。  
  
    > [!NOTE]
    >  本操作指南主题中稍后将此路线创建处理消息从 GlobalBank 西部。  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-east"></a>若要添加客户 GlobalBank 东部的选择规则  
  
1.  在策略浏览器中右键单击**SetGlobalBankWestItinerary**规则，然后依次**副本**。  
  
2.  右键单击**版本 1.0 （未保存）**，然后单击**粘贴**。  
  
3.  在中**新建规则名称**对话框中，键入**SetGlobalBankEastItinerary**，然后单击**确定**。  
  
4.  在策略浏览器中单击**SetGlobalBankEastItinerary**规则。  
  
5.  在中**条件**部分中，右键单击**GlobalBankWest**，然后单击**重置参数**。  
  
6.  单击**argument2**，然后键入**GlobalBankEast**。  
  
7.  在中**操作**部分中，右键单击**GlobalBankWestItinerary**，然后单击**重置参数**。  
  
8.  单击**\<空字符串\>** ，然后键入**GlobalBankEastItinerary**。  
  
    > [!NOTE]
    >  更高版本中的操作方法主题，您将创建来处理消息的此路线，从 GlobalBank 东部。  
  
#### <a name="to-publish-and-deploy-the-policy"></a>若要发布和部署策略  
  
1.  在策略浏览器下**ResolveItineraryBasedOnCustomer**策略中，右键单击**版本 1.0 （未保存）**，然后单击**发布**。  
  
2.  在策略浏览器下**ResolveItineraryBasedOnCustomer**策略中，右键单击**版本 1.0-已发布**，然后单击**部署**。  
  
#### <a name="to-create-an-esb-itinerary-domain-specific-language-dsl-model-for-globalbank-west-messages"></a>若要创建 GlobalBank 西部消息 ESB 路线域特定语言 (DSL) 模型  
  
1.  在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器中右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。  
  
3.  在中**添加新项**对话框中，在模板窗格中，单击**ItineraryDsl**。  
  
4.  在中**名称**框中，键入**GlobalBankWestItinerary**，然后单击**添加**。  
  
#### <a name="to-configure-the-properties-of-the-globalbank-west-itinerary"></a>若要配置 GlobalBank 西部路线的属性  
  
1.  在 Visual Studio 中，单击的设计图面**GlobalBankWestItinerary.itinerary**。 在中**GlobalBankWestItinerary**属性窗口中，配置以下属性：  
  
    1.  在中**模型导出程序**下拉列表中，单击**数据库路线导出程序**。  
  
    2.  单击省略号按钮 （...） 下一步**行程数据库**属性。  
  
    3.  在中**连接属性**对话框中，选择承载路线的存储库数据库的 SQL 服务器，然后指定数据库的名称 (默认名称是**EsbItineraryDb**)。  
  
2.  在中**路线状态**下拉列表中，单击**已部署**。  
  
    > [!NOTE]
    >  此步骤允许您将导出到一个中央存储库; 路线可以选择并在接收到消息时此存储库从附加的路线。 稍后将配置路线选择器管道组件以使用业务规则引擎冲突解决程序 (BRI) 评估入站的消息，并从此存储库中选择相应的路线。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>若要定义路线的结构  
  
1.  从工具箱拖动**接入点**至设计图面上的模型元素。 在中**OnRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**ReceiveNAOrder**。  
  
    2.  在中**Extender**下拉列表中，单击**接入点 ESB 服务扩展**。  
  
    3.  在中**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
    4.  在中**接收端口**下拉列表中，单击**OnRamp.Itinerary**。  
  
2.  从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**ReceiveNAOrder**模型元素。 在中**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**SendNAOrder**。  
  
    2.  在中**Extender**下拉列表中，单击**关闭负载增加 ESB 服务扩展**。  
  
    3.  在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在中**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。  
  
3.  从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**ReceiveNAOrder**模型元素和**SendNAOrder**模型元素。 在中**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**RouteMessage**。  
  
    2.  在**路线服务 Extender**下拉列表中，单击**接入点关闭路线服务扩展**。  
  
    3.  在中**关闭负载增加**下拉列表中，展开**SendNAOrder**，然后单击**发送处理程序**。  
  
4.  右键单击**冲突解决程序**系列**RouteMessage**模型元素，然后单击**添加新解析程序**。 在中**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**StaticResolver**。  
  
    2.  在中**解析程序实现**下拉列表中，单击**静态解析程序扩展**。  
  
    3.  在中**传输名称**下拉列表中，单击**文件**。  
  
    4.  单击**传输位置**属性，并键入**C:\HowTos\Out\West%MessageID%.xml**。  
  
5.  在工具箱中，单击**连接器**。 将从连接**ReceiveNAOrder**到模型元素**RouteMessage**模型元素。  
  
6.  在工具箱中，单击**连接器**。 将从连接**RouteMessage**到模型元素**SendNAOrder**模型元素。  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a>若要将模型导出到路线的数据库  
  
1.  在 Visual Studio 中，右键单击设计图面的**GlobalBankWestItinerary**路线，并单击**导出模型**。  
  
    > [!NOTE]
    >  路线已导出到行程数据库，并且现在可由路线选择器组件。  
  
2.  保存项目的所有项目。  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-east-message"></a>若要创建 GlobalBank 东部消息 ESB 路线 DSL 模型  
  
1.  在 Visual Studio 中，打开 C:\HowTos\Patterns.sln。  
  
2.  在解决方案资源管理器中右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。  
  
3.  在中**添加新项**对话框中，在模板窗格中，单击**ItineraryDsl**。  
  
4.  在中**名称**框中，键入**GlobalBankEastItinerary**，然后单击**添加**。  
  
#### <a name="to-configure-the-properties-of-the-globalbank-east-itinerary"></a>若要配置 GlobalBank 东部路线的属性  
  
1.  在 Visual Studio 中，单击的设计图面**GlobalBankEastItinerary.itinerary**。 在中**GlobalBankEastItinerary**属性窗口中，配置以下属性：  
  
    1.  在中**模型导出程序**下拉列表中，单击**数据库路线导出程序**。  
  
    2.  单击省略号按钮 （...） 下一步**行程数据库**属性。  
  
    3.  在中**连接属性**对话框中，选择承载路线的存储库数据库的 SQL 服务器，然后指定数据库的名称 (默认名称是**EsbItineraryDb**)。  
  
2.  在中**路线状态**下拉列表中，单击**已部署**。  
  
    > [!NOTE]
    >  此步骤允许您将导出到一个中央存储库; 路线可以选择和接收消息时，此存储库中附加路线。 稍后将配置路线选择器管道组件以使用 BRI 冲突解决程序来评估入站的消息，并从此存储库中选择相应的路线。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>若要定义路线的结构  
  
1.  从工具箱拖动**接入点**至设计图面上的模型元素。 在中**OnRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**ReceiveNAOrder**。  
  
    2.  在中**Extender**下拉列表中，单击**接入点 ESB 服务扩展**。  
  
    3.  在中**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
    4.  在中**接收端口**下拉列表中，单击**OnRamp.Itinerary**。  
  
2.  从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**ReceiveNAOrder**模型元素。 在中**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**SendNAOrder**。  
  
    2.  在中**Extender**下拉列表中，单击**关闭负载增加 ESB 服务扩展**。  
  
    3.  在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在中**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。  
  
3.  从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**ReceiveNAOrder**模型元素和**SendNAOrder**模型元素。 在中**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**RouteMessage**。  
  
    2.  在**路线服务 Extender**下拉列表中，单击**接入点关闭路线服务扩展**。  
  
    3.  在中**关闭负载增加**下拉列表中，展开**SendNAOrder**，然后单击**发送处理程序**。  
  
4.  右键单击**冲突解决程序**系列**RouteMessage**模型元素，然后单击**添加新解析程序**。 在中**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**StaticResolver**。  
  
    2.  在中**解析程序实现**下拉列表中，单击**静态解析程序扩展**。  
  
    3.  在中**传输名称**下拉列表中，单击**文件**。  
  
    4.  单击**传输位置**属性，并键入**C:\HowTos\Out\East%MessageID%.xml**。  
  
5.  在工具箱中，单击**连接器**。 将从连接**ReceiveNAOrder**到模型元素**RouteMessage**模型元素。  
  
6.  在工具箱中，单击**连接器**。 将从连接**RouteMessage**到模型元素**SendNAOrder**模型元素。  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a>若要将模型导出到路线的数据库  
  
1.  在 Visual Studio 中，右键单击设计图面的**GlobalBankEastItinerary**路线，并单击**导出模型**。  
  
    > [!NOTE]
    >  路线已导出到行程数据库，并且现在可由路线选择器组件。  
  
2.  保存项目的所有项目。  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a>若要创建和配置 ESB 接入点  
  
1.  单击**启动**在任务栏上，依次指向**所有程序**，指向**BizTalk Server**，然后单击**BizTalk Server 管理**。  
  
2.  在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开**Microsoft.Practices.ESB**。  
  
3.  右键单击**接收位置**，依次指向**新建**，然后单击**单向接收位置**。  
  
4.  在中**选择接收端口**对话框中，单击**OnRamp.Itinerary**，然后单击**确定**。  
  
5.  在中**接收位置属性**对话框中**名称**框中，键入**OnRamp.Itinerary.HowTo**。  
  
6.  在中**类型**下拉列表中，单击**文件**，然后单击**配置**。  
  
7.  在中**FILE 传输属性**对话框中**接收文件夹**框中，键入**C:\HowTos\DropFolder**，然后单击**确定**。  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a>若要配置路线选择器管道组件  
  
1.  在中**接收位置属性**对话框中**接收管道**下拉列表中，单击**ItinerarySelectReceiveXml**，然后单击省略号按钮 （...).  
  
2.  使用**配置管道**对话框可以配置以下**路线选择器**组件属性：  
  
    1.  单击**ItineraryFactKey**属性，并键入**Resolver.Itinerary**。  
  
    2.  单击**ResolverConnectionString**属性，并键入**BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**  
  
    3.  单击**确定**以关闭**配置管道**对话框。  
  
3.  单击**确定**以关闭**接收位置属性**对话框。  
  
4.  在 BizTalk Server 管理控制台中，右键单击**OnRamp.Itinerary.HowTo**接收位置，然后依次**启用**。  
  
#### <a name="to-test-the-itinerary-selector-and-business-rules"></a>若要测试的路线选择器和业务规则  
  
1.  在 Windows 资源管理器，浏览到 C:\HowTos。  
  
2.  复制 （不移动） 到 DropFolder 文件夹 East.xml 和 West.xml 的文件。  
  
3.  浏览到 C:\HowTos\Out。验证已将 East%MessageID%.xml 和 West%MessageID%.xml 消息写入到目录。  
  
    > [!NOTE]
    >  除了客户元素的值完全相同，但使用不同路线，路线选择器管道组件的分辨率处理消息。  
  
4.  在 BizTalk Server 管理控制台中，右键单击**OnRamp.Itinerary.HowTo**接收位置，然后依次**禁用**。  
  
5.  之后**OnRamp.Itinerary.HowTo**接收位置被禁用，右键单击它，并单击**删除**。 在中**确认删除接收位置**对话框中，单击**是**。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [如何：拆分交换并使用不同的路线将生成的消息路由至多个文件位置](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)  
  
-   [开发活动](../esb-toolkit/development-activities.md)  
  
-   [安装和运行动态解析示例](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)  
  
-   [消息路由模式](../esb-toolkit/message-routing-patterns.md)