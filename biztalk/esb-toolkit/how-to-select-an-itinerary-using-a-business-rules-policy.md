---
title: "如何： 选择使用业务规则策略路线 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f6373a8-d9d6-46c6-95e3-f62dd33c342a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d06bdea233c88fb740c728a414472d01a8fdc34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-select-an-itinerary-using-a-business-rules-policy"></a>如何： 选择使用业务规则策略路线
## <a name="goal"></a>目的  
 本部分演示如何创建可用于选择一条路线基于收到的消息内容的业务规则以及如何配置路线选择器管道组件内泛型路线入口以调用这些规则。 本部分介绍在该消息将路由以不同方式，根据客户所在的地区一个业务方案。  
  
 在本操作方法主题中，你将完成以下步骤：  
  
-   客户全局 Bank 西部和美国东部部门的的模型路线。  
  
-   创建将用于选择的处理请求路线的业务规则策略。  
  
-   配置要使用业务规则策略来选择适当的路线的路线选择器管道组件。  
  
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
  
#### <a name="to-create-a-business-rules-engine-bre-policy-to-select-an-itinerary-using-custom-message-properties"></a>若要创建业务规则引擎 (BRE) 策略来选择使用自定义消息属性路线  
  
1.  单击**启动**在任务栏中，指向**所有程序**，指向 **[!INCLUDE[prague](../includes/prague-md.md)]** ，然后单击**业务规则编辑器**。  
  
2.  在策略资源管理器中，右键单击**策略**，然后单击**添加新策略**。 命名策略时**ResolveItineraryBasedOnCustomer**。  
  
    > [!NOTE]
    >  本操作指南主题的主题中创建使用相同的业务规则策略和路线[如何： 拆分将交换并将生成的消息路由到多个文件的位置使用不同路线](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)。 如果你已完成该部分，可以跳过本主题中后面到过程中，"以创建和配置 ESB 入口"。  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-west"></a>若要添加客户 GlobalBank 西部选择规则  
  
1.  在**ResolveItineraryBasedOnCustomer**策略，右键单击**（不保存） 1.0 版**，然后单击**添加新规则**。 命名规则**SetGlobalBankWestItinerary**。  
  
2.  在事实数据资源管理器，单击**XML 架构**选项卡上，右键单击**架构**，然后单击**浏览**。  
  
3.  在**架构文件**对话框中，浏览到 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB。DynamicResolution.Schemas，选择**NAOrderDoc.xsd**，然后单击**打开**。  
  
    > [!NOTE]
    >  这是定义 NAOrderDoc.xml 消息，用于创建将用于测试的西部和东部消息的架构。  
  
4.  在事实数据资源管理器，单击**NAOrderDoc.xsd**，单击**文档类型**属性在属性窗格中，然后键入**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.  
  
    > [!NOTE]
    >  这是架构的完全限定的名称。  
  
5.  在事实数据资源管理器中，展开**NAOrderDoc.xsd**，然后展开**OrderDoc**。  
  
6.  在规则窗口中，右键单击**条件**，指向**谓词**，然后单击**相等**。  
  
7.  从事实数据资源管理器拖动**customerName**元素**argument1**节点下的**条件**。  
  
8.  单击**argument2**节点，并键入**GlobalBankWest**。  
  
9. 在事实数据资源管理器，单击**词汇**选项卡。展开**ESB。路线**词汇，展开**版本 1.1**，然后拖动**设置路线名称**定义与**操作**。  
  
10. 单击**\<空字符串 >**，然后键入**GlobalBankWestItinerary**。  
  
    > [!NOTE]
    >  更高版本在本操作方法主题中，你将创建处理这些消息的此路线，从 GlobalBank 西部。  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-east"></a>若要为客户 GlobalBank 东部添加一个选择规则  
  
1.  在策略资源管理器中，右键单击**SetGlobalBankWestItinerary**规则，并依次**复制**。  
  
2.  右键单击**（不保存） 1.0 版**，然后单击**粘贴**。  
  
3.  在**新规则名称**对话框中，键入**SetGlobalBankEastItinerary**，然后单击**确定**。  
  
4.  在策略资源管理器，单击**SetGlobalBankEastItinerary**规则。  
  
5.  在**条件**部分中，右键单击**GlobalBankWest**，然后单击**重置参数**。  
  
6.  单击**argument2**，然后键入**GlobalBankEast**。  
  
7.  在**操作**部分中，右键单击**GlobalBankWestItinerary**，然后单击**重置参数**。  
  
8.  单击**\<空字符串 >**然后键入**GlobalBankEastItinerary**。  
  
    > [!NOTE]
    >  更高版本中的操作方法主题，你将从 GlobalBank 东处理这些消息创建此路线。  
  
#### <a name="to-publish-and-deploy-the-policy"></a>若要发布和部署策略  
  
1.  在策略资源管理器下**ResolveItineraryBasedOnCustomer**策略中，右击**（不保存） 1.0 版**，然后单击**发布**。  
  
2.  在策略资源管理器下**ResolveItineraryBasedOnCustomer**策略中，右击**版本 1.0-发布**，然后单击**部署**。  
  
#### <a name="to-create-an-esb-itinerary-domain-specific-language-dsl-model-for-globalbank-west-messages"></a>若要创建 GlobalBank 西部消息 ESB 路线域特定语言 (DSL) 模型  
  
1.  在[!INCLUDE[vs2010](../includes/vs2010-md.md)]，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器，右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。  
  
3.  在**添加新项**对话框中，在模板窗格中，单击**ItineraryDsl**。  
  
4.  在**名称**框中，键入**GlobalBankWestItinerary**，然后单击**添加**。  
  
#### <a name="to-configure-the-properties-of-the-globalbank-west-itinerary"></a>若要配置 GlobalBank 西部路线的属性  
  
1.  在 Visual Studio 中，单击的设计图面**GlobalBankWestItinerary.itinerary**。 在**GlobalBankWestItinerary**属性窗口中，配置以下属性：  
  
    1.  在**模型导出程序**下拉列表中，单击**数据库路线导出程序**。  
  
    2.  单击旁边的省略号按钮 （...）**路线数据库**属性。  
  
    3.  在**连接属性**对话框中，选择承载路线存储库数据库中，SQL Server，然后指定数据库的名称 (默认名称是**EsbItineraryDb**)。  
  
2.  在**路线状态**下拉列表中，单击**已部署**。  
  
    > [!NOTE]
    >  此步骤允许您将导出到一个中心存储库; 路线可以选择路线，并将其附加从在接收到消息时此存储库。 更高版本，你将配置路线选择器管道组件配置为使用业务规则引擎冲突解决程序 (BRI) 要评估的入站的消息和从此存储库中选择相应的路线。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>若要定义路线的结构  
  
1.  从工具箱中，拖动**上负载增加**到设计图面上的模型元素。 在**OnRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**ReceiveNAOrder**。  
  
    2.  在**扩展程序**下拉列表中，单击**上负载增加 ESB 服务扩展**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
    4.  在**接收端口**下拉列表中，单击**OnRamp.Itinerary**。  
  
2.  从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**ReceiveNAOrder**模型元素。 在**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SendNAOrder**。  
  
    2.  在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 服务扩展**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。  
  
3.  从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**ReceiveNAOrder**模型元素和**SendNAOrder**模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**RouteMessage**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**关闭负载增加路线服务扩展**。  
  
    3.  在**关闭负载增加**下拉列表中，展开**SendNAOrder**，然后单击**发送处理程序**。  
  
4.  右键单击**冲突解决程序**集合**RouteMessage**模型元素，并依次**添加新解析程序**。 在**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**StaticResolver**。  
  
    2.  在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。  
  
    3.  在**传输名称**下拉列表中，单击**文件**。  
  
    4.  单击**传输位置**属性，再然后键入**C:\HowTos\Out\West%MessageID%.xml**。  
  
5.  在工具箱中，单击**连接器**。 将从连接**ReceiveNAOrder**到模型元素**RouteMessage**模型元素。  
  
6.  在工具箱中，单击**连接器**。 将从连接**RouteMessage**到模型元素**SendNAOrder**模型元素。  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a>将导出到路线的数据库的模型  
  
1.  在 Visual Studio 中，右键单击的设计图面**GlobalBankWestItinerary**路线，，然后单击**导出模型**。  
  
    > [!NOTE]
    >  路线已导出到路线的数据库，现在可以使用由路线选择器组件。  
  
2.  保存所有项目。  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-east-message"></a>若要创建 GlobalBank 东部消息 ESB 路线 DSL 模型  
  
1.  在[!INCLUDE[vs2010](../includes/vs2010-md.md)]，打开 C:\HowTos\Patterns.sln。  
  
2.  在解决方案资源管理器，右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。  
  
3.  在**添加新项**对话框中，在模板窗格中，单击**ItineraryDsl**。  
  
4.  在**名称**框中，键入**GlobalBankEastItinerary**，然后单击**添加**。  
  
#### <a name="to-configure-the-properties-of-the-globalbank-east-itinerary"></a>若要配置 GlobalBank 东部路线的属性  
  
1.  在 Visual Studio 中，单击的设计图面**GlobalBankEastItinerary.itinerary**。 在**GlobalBankEastItinerary**属性窗口中，配置以下属性：  
  
    1.  在**模型导出程序**下拉列表中，单击**数据库路线导出程序**。  
  
    2.  单击旁边的省略号按钮 （...）**路线数据库**属性。  
  
    3.  在**连接属性**对话框中，选择承载路线存储库数据库中，SQL Server，然后指定数据库的名称 (默认名称是**EsbItineraryDb**)。  
  
2.  在**路线状态**下拉列表中，单击**已部署**。  
  
    > [!NOTE]
    >  此步骤允许您将导出到一个中心存储库; 路线可以选择路线，并将其从此存储库中接收消息时附加。 更高版本，你将配置路线选择器管道组件配置为使用 BRI 解析程序要评估的入站的消息和从此存储库中选择相应的路线。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>若要定义路线的结构  
  
1.  从工具箱中，拖动**上负载增加**到设计图面上的模型元素。 在**OnRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**ReceiveNAOrder**。  
  
    2.  在**扩展程序**下拉列表中，单击**上负载增加 ESB 服务扩展**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
    4.  在**接收端口**下拉列表中，单击**OnRamp.Itinerary**。  
  
2.  从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**ReceiveNAOrder**模型元素。 在**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SendNAOrder**。  
  
    2.  在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 服务扩展**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。  
  
3.  从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**ReceiveNAOrder**模型元素和**SendNAOrder**模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**RouteMessage**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**关闭负载增加路线服务扩展**。  
  
    3.  在**关闭负载增加**下拉列表中，展开**SendNAOrder**，然后单击**发送处理程序**。  
  
4.  右键单击**冲突解决程序**集合**RouteMessage**模型元素，并依次**添加新解析程序**。 在**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**StaticResolver**。  
  
    2.  在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。  
  
    3.  在**传输名称**下拉列表中，单击**文件**。  
  
    4.  单击**传输位置**属性，再然后键入**C:\HowTos\Out\East%MessageID%.xml**。  
  
5.  在工具箱中，单击**连接器**。 将从连接**ReceiveNAOrder**到模型元素**RouteMessage**模型元素。  
  
6.  在工具箱中，单击**连接器**。 将从连接**RouteMessage**到模型元素**SendNAOrder**模型元素。  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a>将导出到路线的数据库的模型  
  
1.  在 Visual Studio 中，右键单击的设计图面**GlobalBankEastItinerary**路线，，然后单击**导出模型**。  
  
    > [!NOTE]
    >  路线已导出到路线的数据库，现在可以使用由路线选择器组件。  
  
2.  保存所有项目。  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a>若要创建和配置 ESB 入口  
  
1.  单击**启动**在任务栏中，指向**所有程序**，指向 **[!INCLUDE[prague](../includes/prague-md.md)]** ，然后单击**BizTalk Server 管理**.  
  
2.  在[!INCLUDE[prague](../includes/prague-md.md)]管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开**Microsoft.Practices.ESB**。  
  
3.  右键单击**接收位置**，指向**新建**，然后单击**单向接收位置**。  
  
4.  在**选择接收端口**对话框中，单击**OnRamp.Itinerary**，然后单击**确定**。  
  
5.  在**接收位置属性**对话框中，在**名称**框中，键入**OnRamp.Itinerary.HowTo**。  
  
6.  在**类型**下拉列表中，单击**文件**，然后单击**配置**。  
  
7.  在**文件传输属性**对话框中，在**接收文件夹**框中，键入**C:\HowTos\DropFolder**，然后单击**确定**。  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a>若要配置路线选择器管道组件  
  
1.  在**接收位置属性**对话框中，在**接收管道**下拉列表中，单击**ItinerarySelectReceiveXml**，然后单击省略号按钮 （...).  
  
2.  使用**配置管道**对话框中，配置以下各项**路线选择器**组件属性：  
  
    1.  单击**ItineraryFactKey**属性，再然后键入**Resolver.Itinerary**。  
  
    2.  单击**ResolverConnectionString**属性，再然后键入**BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**  
  
    3.  单击**确定**关闭**配置管道**对话框。  
  
3.  单击**确定**关闭**接收位置属性**对话框。  
  
4.  在[!INCLUDE[prague](../includes/prague-md.md)]管理控制台中，右键单击**OnRamp.Itinerary.HowTo**接收位置，并依次**启用**。  
  
#### <a name="to-test-the-itinerary-selector-and-business-rules"></a>若要测试的路线的选择器和业务规则  
  
1.  在 Windows 资源管理器，浏览到 C:\HowTos。  
  
2.  复制 （不移动） 到 DropFolder 文件夹 East.xml 和 West.xml 的文件。  
  
3.  浏览到 C:\HowTos\Out。验证目录中已写的 East%MessageID%.xml 和 West%MessageID%.xml 消息。  
  
    > [!NOTE]
    >  尽管除外客户元素的值相同，消息已处理使用不同路线，根据路线选择器管道组件的分辨率。  
  
4.  在[!INCLUDE[prague](../includes/prague-md.md)]管理控制台中，右键单击**OnRamp.Itinerary.HowTo**接收位置，并依次**禁用**。  
  
5.  后**OnRamp.Itinerary.HowTo**接收位置处于禁用状态，右键单击它，，然后单击**删除**。 在**确认删除接收位置**对话框中，单击**是**。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [如何： 拆分将交换，并将生成的消息路由到多个使用不同路线的文件位置](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)  
  
-   [开发活动](../esb-toolkit/development-activities.md)  
  
-   [安装和运行动态解析示例](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)  
  
-   [消息路由模式](../esb-toolkit/message-routing-patterns.md)