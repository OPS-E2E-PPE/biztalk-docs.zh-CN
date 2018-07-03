---
title: 如何： 验证使用 ESB 接入点的消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43dfc791-7cb6-45a4-898f-f53def199c08
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62df8ec8628353aa127ed6cde8380e5724ddf12a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020565"
---
# <a name="how-to-validate-a-message-using-an-esb-on-ramp"></a>如何： 验证使用 ESB 接入点的消息
## <a name="goal"></a>目的  
 本部分演示如何配置 ESB 调度程序反汇编管道组件来执行消息验证的 XML 消息提交到 ESB 接入点。  
  
 在本操作指南主题中，您将完成以下步骤：  
  
-   创建 ESB 接入点使用**ItinerarySelectReceiveXml**管道。  
  
-   配置 ESB 调度程序拆装管道组件以验证消息内容。  
  
-   配置路线选择器管道组件以解析相应的路线。  
  
-   测试使用了有效的消息和一个无效的消息的消息验证。  
  
## <a name="prerequisites"></a>必要條件  
 本操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。  
  
## <a name="before-you-begin"></a>开始之前  
 在本操作指南主题的后面部分执行的步骤之前，请完成以下任务：  
  
- 创建无效的测试消息。  
  
- 创建的 ESB 路线域特定语言 (DSL) 模型。  
  
- 配置路线的属性。  
  
- 定义路线的结构。  
  
- 将模型导出到行程数据库。  
  
  以下过程介绍如何执行其中每项功能。  
  
#### <a name="to-create-an-invalid-test-message"></a>若要创建无效的测试消息  
  
1.  在 Windows 资源管理器，浏览到 C:\HowTos。  
  
2.  创建一份 NAOrderDoc.xml，，然后重命名副本 Invalid.xml。  
  
3.  在记事本中，打开 Invalid.xml。  
  
4.  更改**\<ns0:requestType\>10\</ns0:requestType\>到\<ns0:requestType\>十个\</ns0:requestType\>**.  
  
5.  将 Invalid.xml 另存为 utf-8，，然后关闭记事本。  
  
    > [!NOTE]
    >  通过此元素的数字值更改为文本，该消息将不再符合架构。  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>若要创建的 ESB 路线 DSL 模型  
  
1.  在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器中右键单击**ItineraryLibrary**，依次指向**添加**，然后单击**新路线**。  
  
3.  在中**添加新项**对话框中，键入**验证**中**名称**框，并单击**添加**。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>若要配置的路线属性  
  
1.  在 Visual Studio 中，单击的设计图面**Validation.itinerary**。 在中**验证**属性窗口中，配置以下属性：  
  
    1.  在中**模型导出程序**下拉列表中，单击**数据库路线导出程序**。  
  
    2.  单击省略号按钮 （...） 下一步**行程数据库**属性。  
  
    3.  在中**连接属性**对话框中，选择承载路线的存储库数据库的 SQL 服务器，然后指定数据库的名称 (默认名称是**EsbItineraryDb**)。  
  
2.  在中**路线状态**下拉列表中，单击**已部署**。  
  
    > [!NOTE]
    >  此步骤允许您将导出到一个中央存储库; 路线可以选择并收到消息时，此存储库中附加路线。 稍后将配置路线选择器管道组件以使用静态冲突解决程序从此存储库中选择相应的路线。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>若要定义路线的结构  
  
1.  从工具箱拖动**接入点**至设计图面上的模型元素。 在中**OnRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**ReceiveNAOrder**。  
  
    2.  在中**Extender**下拉列表中，单击**接入点 ESB 扩展器**。  
  
    3.  在中**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
    4.  在中**接收端口**下拉列表中，单击**OnRamp.Itinerary**。  
  
2.  从工具箱拖动**接入点关闭**模型元素到设计图面，然后将它放到现有的模型元素的右边。 在中**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**SendNAOrder**。  
  
    2.  在**Extender**下拉列表中，单击**关闭负载增加 ESB 扩展器**。  
  
    3.  在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在中**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。  
  
3.  从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**ReceiveNAOrder**模型元素和**SendNAOrder**模型元素。 在中**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**SendPortFilter**。  
  
    2.  在**路线服务 Extender**下拉列表中，单击**接入点关闭扩展器**。  
  
    3.  在中**关闭负载增加**下拉列表中，展开**SendNAOrder**，然后单击**发送处理程序**。  
  
4.  右键单击**冲突解决程序**系列**SendPortFilter**元素，并单击**添加新解析程序**。 在中**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**ConfigureOffRamp**。  
  
    2.  在中**解析程序实现**下拉列表中，单击**静态解析程序扩展**。  
  
    3.  在中**传输名称**下拉列表中，单击**文件**。  
  
    4.  单击**传输位置**属性，并键入**C:\HowTos\Out\Validated%MessageID%.xml**。  
  
5.  在工具箱中，单击**连接器**。 将从连接**ReceiveNAOrder**到模型元素**SendPortFilter**模型元素。  
  
6.  在工具箱中，单击**连接器**。 将从连接**SendPortFilter**到模型元素**SendNAOrder**模型元素。  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a>若要将模型导出到路线的数据库  
  
1.  在 Visual Studio 中，右键单击设计图面的**验证**路线，并单击**导出模型**。  
  
    > [!NOTE]
    >  路线已导出到行程数据库，并且现在可由路线选择器管道组件。  
  
2.  保存项目的所有项目。  
  
## <a name="steps"></a>步骤  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a>若要创建和配置 ESB 接入点  
  
1.  单击**启动**在任务栏上，依次指向**所有程序**，指向**BizTalk Server**，然后单击**BizTalk Server 管理**。  
  
2.  在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开**Microsoft.Practices.ESB**。  
  
3.  右键单击**接收位置**，依次指向**新建**，然后单击**单向接收位置**。  
  
4.  在中**选择接收端口**对话框中，单击**OnRamp.Itinerary**，然后单击**确定**。  
  
5.  在中**接收位置属性**对话框中，键入**OnRamp.Itinerary.HowTo**中**名称**框。  
  
6.  在中**类型**下拉列表中，单击**文件**，然后单击**配置**。  
  
7.  在中**FILE 传输属性**对话框中，键入**C:\HowTos\DropFolder**中**接收文件夹**框，并单击**确定**。  
  
#### <a name="to-configure-the-on-ramp-to-perform-message-validation"></a>若要配置的途径，用以执行消息验证  
  
1.  在中**接收位置属性**对话框中**接收管道**下拉列表中，单击**ItinerarySelectReceiveXml**，然后单击省略号按钮 （...).  
  
2.  使用**配置管道**对话框可以配置以下**XML 拆装器**组件属性：  
  
    1.  展开 GlobalBank.Esb 应用程序，然后依次**架构**。 右键单击**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**，然后单击**属性**。 复制**名称**并**程序集**属性并将其粘贴到文本文件中。  
  
    2.  在中**拆装**组件，单击**True**中**ValidateDocument**下拉列表。  
  
    3.  单击**DocumentSpecNames**属性，并键入完全限定名称的架构。 完全限定的名名称开头且后跟一个逗号和在步骤中提取的程序集信息。 以下是一个示例：  
  
         GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc，GlobalBank.ESB.DynamicResolution.Schemas，版本 = 2.0.0.0，区域性 = 中性，PublicKeyToken = c2c8b2b87f54180a  
  
        > [!NOTE]
        >  这是架构的要进行验证，则的完全限定的名称它包含的架构名称和四个程序集属性： 程序集名称、 版本、 区域性和公钥标记。 允许多个值;使用竖线分隔多个架构 (&#124;) 符号。  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a>若要配置路线选择器管道组件  
  
1.  在中**配置管道**对话框框中，配置以下各项**路线选择器**组件属性：  
  
    1.  单击**ItineraryFactKey**属性，并键入**Resolver.Itinerary**。  
  
    2.  单击**ResolverConnectionString**属性，并键入**路线：\\\name=Validation;**。  
  
    3.  单击**确定**以关闭**配置管道**对话框。  
  
2.  单击**确定**以关闭**接收位置属性**对话框。  
  
3.  在 BizTalk Server 管理控制台中，右键单击**OnRamp.Itinerary.HowTo**接收位置，然后依次**启用**。  
  
#### <a name="to-test-the-message-validation-and-itinerary-selection"></a>若要测试消息验证和路线选择  
  
1.  在 Windows 资源管理器，浏览到 C:\HowTos。  
  
2.  复制 （不移动） 到 DropFolder 文件夹 NAOrderDoc.xml。  
  
3.  浏览到 C:\HowTos\Out。验证 Validated%MessageID%.xml 已写入到目录。  
  
    > [!NOTE]
    >  有效的消息完成其基于路线的路由，按预期方式。  
  
4.  从扩展文件夹中删除 Validated%MessageID%.xml。  
  
5.  在 Windows 资源管理器，浏览到 C:\HowTos。  
  
6.  复制 （不移动） 到 DropFolder 文件夹 Invalid.xml。  
  
7.  浏览到 C:\HowTos\Out。验证已传递任何新的消息。  
  
    > [!NOTE]
    >  无法验证消息;因此，基于路线的路由无法完成。  
  
8.  单击**启动**在任务栏上，依次指向**管理工具**，然后单击**事件查看器**。  
  
9. 在事件查看器中，展开**Windows 日志**，然后单击**应用程序**。  
  
10. 找到最新事件其中**源**是**BizTalk Server**，并**事件 ID**是**5719**。  
  
    > [!NOTE]
    >  提交和失败的无效消息导致应用程序事件日志异常项。  
  
11. 在 BizTalk Server 管理控制台中，右键单击**OnRamp.Itinerary.HowTo**接收位置，然后依次**禁用**。  
  
12. 之后**OnRamp.Itinerary.HowTo**接收位置被禁用，右键单击它，并单击**删除**。 在中**确认删除接收位置**对话框中，单击**是**。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [如何：使用业务规则策略选择路线](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [开发活动](../esb-toolkit/development-activities.md)  
  
-   [安装和运行动态解析示例](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)