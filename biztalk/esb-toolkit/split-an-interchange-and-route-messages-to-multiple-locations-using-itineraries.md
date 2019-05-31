---
title: 如何：将某个交换拆分，并将结果的消息路由到多个使用不同的路线的文件位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccd46bee-e4a1-4846-8bde-b0460bda1e72
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36287f22290f30b687e90e9a111a3ae79aa53d5e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268903"
---
# <a name="how-to-split-an-interchange-and-route-the-resulting-messages-to-multiple-file-locations-using-distinct-itineraries"></a>如何：将某个交换拆分，并将结果的消息路由到多个使用不同的路线的文件位置
## <a name="goal"></a>目的  
 本部分演示如何创建 ESB 接入点使用**ItinerarySelectReceiveXml**管道以及如何配置管道组件将入站的交换拆分并选择适当的路由的滑动每个生成的消息，根据消息上下文。 将使用业务规则策略，解决路线选择，将以不同的方式根据客户所在的区域路由消息。  
  
 在本操作指南主题中，您将完成以下步骤：  
  
-   创建 ESB 接入点拆分为一个 XML 交换的。  
  
-   配置路线选择器管道组件以使用业务规则策略选择适当的路线。  
  
## <a name="prerequisites"></a>先决条件  
 本操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。  
  
## <a name="before-you-begin"></a>开始之前  
 在本操作指南主题的后面部分执行的步骤之前，请完成以下任务：  
  
-   创建所需的项目。  
  
-   将架构项目添加到模式解决方案。  
  
-   将项目添加到架构项目。  
  
-   创建 BRE 策略来选择使用自定义消息属性路线。  
  
-   添加客户 GlobalBank 西部选择规则。  
  
-   添加客户 GlobalBank 东部选择规则。  
  
-   发布和部署策略。  
  
-   创建用于 GlobalBank 西部消息的 ESB 路线域特定语言 (DSL) 模型。  
  
-   配置 GlobalBank 西部路线的属性。  
  
-   定义 GlobalBank 西部路线的结构。  
  
-   GlobalBank 西部模型导出到路线的数据库。  
  
-   创建 GlobalBank 东部消息 ESB 路线 DSL 模型。  
  
-   配置 GlobalBank 东部路线的属性。  
  
-   定义 GlobalBank 东部路线的结构。  
  
-   GlobalBank 东部模型导出到路线的数据库。  
  
     以下过程介绍如何执行其中每项功能。  
  
#### <a name="to-create-the-required-artifacts"></a>若要创建所需的项目  
  
1.  在 Windows 资源管理器，浏览到 C:\HowTos。  
  
2.  创建名为 OrderDocEnvelope.xsd 的新文本文档。  
  
3.  在记事本中打开 OrderDocEnvelope.xsd 架构。  
  
4.  编辑该文档使用以下代码。  
  
    ```  
    <?xml version="1.0" ?>  
    <xs:schema xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="http://ESB.BizUnit.Map.Test" targetNamespace="http://ESB.BizUnit.Map.Test" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  
      <xs:import schemaLocation="GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc" namespace="http://globalbank.esb.dynamicresolution.com/northamericanservices/" />  
      <xs:annotation>  
        <xs:appinfo>  
          <b:schemaInfo is_envelope="yes" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" />  
          <b:references>  
            <b:reference targetNamespace="http://globalbank.esb.dynamicresolution.com/northamericanservices/" />  
          </b:references>  
        </xs:appinfo>  
      </xs:annotation>  
      <xs:element name="OrderEnvelope">  
        <xs:annotation>  
          <xs:appinfo>  
            <b:recordInfo body_xpath="/*[local-name()='OrderEnvelope' and namespace-uri()='http://ESB.BizUnit.Map.Test']" />  
          </xs:appinfo>  
        </xs:annotation>  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element ref="ns0:OrderDoc" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:schema>  
    ```  
  
5.  将 OrderDocEnvelope.xsd 另存为 utf-8，，然后关闭记事本。  
  
6.  在 C:\HowTos 文件夹中，创建名为 Batch.xml 的新文本文档。  
  
7.  在记事本中，打开 Batch.xml。  
  
8.  编辑该文档使用以下代码。  
  
    ```  
    <?xml version="1.0" ?>  
    <ns0:OrderEnvelope xmlns:ns0="http://ESB.BizUnit.Map.Test">  
      <ns0:OrderDoc xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/">  
        <ns0:customerName>GlobalBankWest</ns0:customerName>  
        <ns0:ID>ns0:ID_0</ns0:ID>  
        <ns0:requestType>10</ns0:requestType>  
      </ns0:OrderDoc>  
      <ns0:OrderDoc xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/">  
        <ns0:customerName>GlobalBankEast</ns0:customerName>  
        <ns0:ID>ns0:ID_0</ns0:ID>  
        <ns0:requestType>11</ns0:requestType>  
      </ns0:OrderDoc>  
      <ns0:OrderDoc xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/">  
        <ns0:customerName>GlobalBankEast</ns0:customerName>  
        <ns0:ID>ns0:ID_0</ns0:ID>  
        <ns0:requestType>12</ns0:requestType>  
      </ns0:OrderDoc>  
    </ns0:OrderEnvelope>  
    ```  
  
9. 保存并关闭 Batch.xml。  
  
#### <a name="to-add-a-schemas-project-to-the-patterns-solution"></a>若要将架构项目添加到模式解决方案  
  
1.  在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器中右键单击**解决方案模式**，依次指向**添加**，然后单击**新项目**。  
  
3.  在中**添加新项目**对话框中，在项目类型窗格中，单击**BizTalk 项目**，然后执行以下操作：  
  
    1.  在模板窗格中单击**空的 BizTalk Server 项目**。  
  
    2.  在中**名称**框中，键入**Patterns.Schemas**，然后单击**确定**。  
  
4.  在解决方案资源管理器中右键单击**Patterns.Schemas**，然后单击**属性**。  
  
5.  在属性窗口上**签名**选项卡上，选择**程序集签名**复选框。  
  
6.  在中**选择强名称密钥文件**下拉列表中，单击 **\<新建...\>** .  
  
7.  在中**创建强名称密钥**对话框框中，配置以下属性：  
  
    1.  在中**密钥文件名称**框中，键入**拆分**。  
  
    2.  清除**保护密钥文件使用密码**复选框，然后依次**确定**。  
  
8.  在属性窗口上**部署**选项卡上，在**应用程序名称**框中，键入**Microsoft.Practices.ESB**。  
  
9. 关闭“属性”窗口。  
  
#### <a name="to-add-the-artifacts-to-the-schemas-project"></a>若要将项目添加到架构项目  
  
1.  在解决方案资源管理器中右键单击**Patterns.Schemas**，然后单击**添加引用**。  
  
2.  上**浏览**选项卡**添加引用**对话框中，浏览到并选择 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB。DynamicResolution.Schemas\bin\Debug\GlobalBank.ESB.DynamicResolution.Schemas.dll，并单击**确定**。  
  
3.  在解决方案资源管理器中右键单击**Patterns.Schemas**，依次指向**添加**，然后单击**现有项**。  
  
4.  在中**添加现有项**对话框中，浏览并选择 C:\HowTos\OrderDocEnvelope.xsd，，然后单击**添加**。  
  
5.  保存解决方案的所有项目。  
  
6.  在解决方案资源管理器中右键单击**Patterns.Schemas**，然后单击**部署**。  
  
    > [!NOTE]
    >  本操作指南主题中创建的那些与使用相同的业务规则策略和路线[如何：选择使用业务规则策略路线](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)主题。 如果尚未完成该部分，请完成以下附加步骤。 如果已完成该部分，继续到"步骤"部分。  
  
#### <a name="to-create-a-business-rules-engine-bre-policy-to-select-an-itinerary-using-custom-message-properties"></a>若要创建业务规则引擎 (BRE) 策略来选择使用自定义消息属性路线  
  
1.  单击**启动**在任务栏上，依次指向**所有程序**，指向**BizTalk Server**，然后单击**业务规则编辑器**。  
  
2.  在策略浏览器中右键单击**策略**，然后单击**添加新策略**。 将策略命名**ResolveItineraryBasedOnCustomer**。  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-west"></a>若要添加客户 GlobalBank 西部选择规则  
  
1.  在中**ResolveItineraryBasedOnCustomer**策略中，右键单击**版本 1.0 （未保存）** ，然后单击**添加新规则**。 命名规则**SetGlobalBankWestItinerary**。  
  
2.  在事实浏览器中单击**XML 架构**选项卡上，右键单击**架构**，然后单击**浏览**。  
  
3.  在中**架构文件**对话框中，浏览到 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB。DynamicResolution.Schemas，选择 NAOrderDoc.xsd，，然后单击**打开**。  
  
    > [!NOTE]
    >  这是定义 NAOrderDoc.xml 消息，用于创建将用于测试的左和右消息的架构。  
  
4.  在事实浏览器中单击 NAOrderDoc.xsd 中，单击**文档类型**属性中为属性窗格，然后按**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**。  
  
    > [!NOTE]
    >  这是架构的完全限定的名称。  
  
5.  在事实浏览器中，展开**NAOrderDoc.xsd**，然后展开**OrderDoc**。  
  
6.  在规则窗口中，右键单击**条件**，依次指向**谓词**，然后单击**相等**。  
  
7.  从事实浏览器中，将**customerName**元素**argument1**节点下的**条件**。  
  
8.  单击**argument2**节点，并键入**GlobalBankWest**。  
  
9. 在事实浏览器中单击**词汇**选项卡。展开**ESB。路线**词汇，展开**版本 1.1**，然后将拖**集路线名称**定义**操作**。  
  
10. 单击 **\<空字符串\>** ，然后键入**GlobalBankWestItinerary**。  
  
    > [!NOTE]
    >  本操作指南主题中稍后将此路线创建处理消息从 GlobalBank 西部。  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-east"></a>若要添加客户 GlobalBank 东部选择规则  
  
1.  在策略浏览器中右键单击**SetGlobalBankWestItinerary**规则，然后依次**副本**。  
  
2.  右键单击**版本 1.0 （未保存）** ，然后单击**粘贴**。  
  
3.  在中**新建规则名称**对话框中，键入**SetGlobalBankEastItinerary**，然后单击**确定**。  
  
4.  在策略浏览器中单击**SetGlobalBankEastItinerary**规则。  
  
5.  在中**条件**部分中，右键单击**GlobalBankWest**，然后单击**重置参数**。  
  
6.  单击**argument2**，然后键入**GlobalBankEast**。  
  
7.  在中**操作**部分中，右键单击**GlobalBankWestItinerary**，然后单击**重置参数**。  
  
8.  单击 **\<空字符串\>** ，然后键入**GlobalBankEastItinerary。**  
  
    > [!NOTE]
    >  本操作指南主题中稍后将此路线创建处理消息从 GlobalBank 东部。  
  
#### <a name="to-publish-and-deploy-the-policy"></a>若要发布和部署策略  
  
1.  在策略浏览器下**ResolveItineraryBasedOnCustomer**策略中，单击**版本 1.0 （未保存）** ，然后单击**发布**。  
  
2.  在策略浏览器下**ResolveItineraryBasedOnCustomer**策略中，单击**版本 1.0-已发布**，然后单击**部署**。  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-west-messages"></a>若要创建 GlobalBank 西部消息 ESB 路线 DSL 模型  
  
1.  在中**Visual Studio**，打开 C:\HowTos\Patterns\Patterns.sln。  
  
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
    >  此步骤允许您将导出到一个中央存储库; 路线可以选择和接收消息时，此存储库中附加路线。 稍后将配置路线选择器管道组件以使用 BRI 冲突解决程序来评估入站的消息，并从此存储库中选择相应的路线。  
  
#### <a name="to-define-the-structure-of-the-globalbank-west-itinerary"></a>若要定义 GlobalBank 西部路线的结构  
  
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
  
#### <a name="to-export-the-globalbank-west-model-to-the-itinerary-database"></a>若要将 GlobalBank 西部模型导出到路线的数据库  
  
1.  在 Visual Studio 中，右键单击设计图面的**GlobalBankWestItinerary**路线，并单击**导出模型**。  
  
    > [!NOTE]
    >  路线已导出到行程数据库，并且现在可由路线选择器组件。  
  
2.  保存项目的所有项目。  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-east-message"></a>若要创建 GlobalBank 东部消息 ESB 路线 DSL 模型  
  
1.  在中**Visual Studio**，打开 C:\HowTos\Patterns.sln。  
  
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
  
#### <a name="to-define-the-structure-of-the-globalbank-east-itinerary"></a>若要定义 GlobalBank 东部路线的结构  
  
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
  
#### <a name="to-export-the-globalbank-east-model-to-the-itinerary-database"></a>若要将 GlobalBank 东部模型导出到路线的数据库  
  
1.  在 Visual Studio 中，右键单击设计图面的**GlobalBankEastItinerary**路线，并单击**导出模型**。  
  
    > [!NOTE]
    >  路线已导出到行程数据库，并且现在可由路线选择器组件。  
  
2.  保存项目的所有项目。  
  
## <a name="steps"></a>步骤  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a>若要创建和配置 ESB 接入点  
  
1.  单击**启动**在任务栏上，依次指向**所有程序**，指向**BizTalk Server**，然后单击**BizTalk Server 管理**。  
  
2.  在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开**Microsoft.Practices.ESB**。  
  
3.  右键单击**接收位置**，依次指向**新建**，然后单击**单向接收位置**。  
  
4.  在中**选择接收端口**对话框中，单击**OnRamp.Itinerary**，然后单击**确定**。  
  
5.  在中**接收位置属性**对话框中**名称**框中，键入**OnRamp.Itinerary.HowTo**。  
  
6.  在中**类型**下拉列表中，单击**文件中，** ，然后单击**配置**。  
  
7.  在中**FILE 传输属性**对话框中**接收文件夹**框中，键入**C:\HowTos\DropFolder**，然后单击**确定**。  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a>若要配置路线选择器管道组件  
  
1.  在中**接收位置属性**对话框中，单击**ItinerarySelectReceiveXml**中**接收管道**下拉列表，并单击省略号按钮 （...）。  
  
2.  使用**配置管道**对话框可以配置以下**路线选择器**组件属性：  
  
    1.  单击**ItineraryFactKey**属性，并键入**Resolver.Itinerary**。  
  
    2.  单击**ResolverConnectionString**属性，并键入**BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**  
  
    3.  单击**确定**以关闭**配置管道**对话框。  
  
        > [!NOTE]
        >  由于此接收位置拆装一个 XML 交换，不不需要任何 XML 拆装器组件配置。  
  
3.  单击**确定**以关闭**接收位置属性**对话框。  
  
4.  在 BizTalk Server 管理控制台中，右键单击**OnRamp.Itinerary.HowTo**接收位置，然后依次**启用**。  
  
#### <a name="to-test-the-itinerary-selector-and-business-rules"></a>若要测试的路线选择器和业务规则  
  
1.  在 Windows 资源管理器，浏览到 C:\HowTos。  
  
2.  复制 （不移动） 到 DropFolder 文件夹 Batch.xml。  
  
3.  浏览到 C:\HowTos\Out。验证一个 West%MessageID%.xml 消息和两个 East%MessageID%.xml 消息已写入到的目录。  
  
    > [!NOTE]
    >  虽然消息除外客户元素的值完全相同，但在处理使用不同路线，路线选择器管道组件的分辨率。  
  
4.  在 BizTalk Server 管理控制台中，右键单击 OnRamp.Itinerary.HowTo 的接收位置，然后单击禁用。  
  
5.  之后**OnRamp.Itinerary.HowTo**接收位置被禁用，右键单击它，并单击**删除**。 在中**确认删除接收位置**对话框中，单击**是**。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [如何：选择使用业务规则策略路线](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [开发活动](../esb-toolkit/development-activities.md)  
  
-   [安装和运行动态解析示例](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)  
  
-   [消息路由模式](../esb-toolkit/message-routing-patterns.md)