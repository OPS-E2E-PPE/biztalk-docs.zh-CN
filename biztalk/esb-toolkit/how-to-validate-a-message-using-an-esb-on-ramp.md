---
title: 如何： 验证使用 ESB 入口的消息 |Microsoft 文档
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
ms.openlocfilehash: 4e14fd3f433609da7748197a8b67112d815da153
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009518"
---
# <a name="how-to-validate-a-message-using-an-esb-on-ramp"></a>如何： 验证使用 ESB 入口的消息
## <a name="goal"></a>目的  
 本部分演示如何配置 ESB 调度程序反汇编管道组件来执行消息验证的 XML 消息提交到 ESB 入口。  
  
 在本操作方法主题中，你将完成以下步骤：  
  
-   创建 ESB 入口使用**ItinerarySelectReceiveXml**管道。  
  
-   配置 ESB 调度程序反汇编管道组件，以验证消息的内容。  
  
-   配置路线选择器管道组件，若要解决适当的路线。  
  
-   测试使用有效的消息和一个无效的消息的消息验证。  
  
## <a name="prerequisites"></a>先决条件  
 此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。  
  
## <a name="before-you-begin"></a>开始之前  
 本操作方法主题中的更高版本执行的步骤之前，请完成以下任务：  
  
-   创建一个无效的测试消息。  
  
-   创建一个 ESB 路线域特定语言 (DSL) 模型。  
  
-   配置路线的属性。  
  
-   定义路线的结构。  
  
-   导出到路线数据库模型。  
  
 下面的过程介绍如何执行其中每个操作。  
  
#### <a name="to-create-an-invalid-test-message"></a>若要创建一个无效的测试消息  
  
1.  在 Windows 资源管理器，浏览到 C:\HowTos。  
  
2.  创建一份 NAOrderDoc.xml，，然后重命名副本 Invalid.xml。  
  
3.  在记事本中，打开 Invalid.xml。  
  
4.  更改 **\<ns0:requestType\>10\</ns0:requestType\>到\<ns0:requestType\>十个\</ns0:requestType\>** .  
  
5.  将 Invalid.xml 另存为 utf-8，，然后关闭记事本。  
  
    > [!NOTE]
    >  通过将此元素的数字值更改为文本，消息不再将根据架构有效。  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>若要创建 ESB 路线 DSL 模型  
  
1.  在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器，右键单击**ItineraryLibrary**，指向**添加**，然后单击**新路线**。  
  
3.  在**添加新项**对话框中，键入**验证**中**名称**框中，并依次**添加**。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>若要配置路线的属性  
  
1.  在 Visual Studio 中，单击的设计图面**Validation.itinerary**。 在**验证**属性窗口中，配置以下属性：  
  
    1.  在**模型导出程序**下拉列表中，单击**数据库路线导出程序**。  
  
    2.  单击旁边的省略号按钮 （...）**路线数据库**属性。  
  
    3.  在**连接属性**对话框中，选择承载路线存储库数据库中，SQL Server，然后指定数据库的名称 (默认名称是**EsbItineraryDb**)。  
  
2.  在**路线状态**下拉列表中，单击**已部署**。  
  
    > [!NOTE]
    >  此步骤允许您将导出到一个中心存储库; 路线可以选择并收到消息时，从该存储库附加路线。 更高版本，你将配置路线选择器管道组件配置为使用静态冲突解决程序从此存储库中选择相应的路线。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>若要定义路线的结构  
  
1.  从工具箱中，拖动**上负载增加**到设计图面上的模型元素。 在**OnRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**ReceiveNAOrder**。  
  
    2.  在**扩展程序**下拉列表中，单击**上负载增加 ESB 扩展程序**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
    4.  在**接收端口**下拉列表中，单击**OnRamp.Itinerary**。  
  
2.  从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到现有的模型元素的右侧。 在**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SendNAOrder**。  
  
    2.  在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 扩展程序**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。  
  
3.  从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**ReceiveNAOrder**模型元素和**SendNAOrder**模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SendPortFilter**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**关闭负载增加扩展程序**。  
  
    3.  在**关闭负载增加**下拉列表中，展开**SendNAOrder**，然后单击**发送处理程序**。  
  
4.  右键单击**冲突解决程序**集合**SendPortFilter**元素，，然后单击**添加新解析程序**。 在**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**ConfigureOffRamp**。  
  
    2.  在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。  
  
    3.  在**传输名称**下拉列表中，单击**文件**。  
  
    4.  单击**传输位置**属性，再然后键入**C:\HowTos\Out\Validated%MessageID%.xml**。  
  
5.  在工具箱中，单击**连接器**。 将从连接**ReceiveNAOrder**到模型元素**SendPortFilter**模型元素。  
  
6.  在工具箱中，单击**连接器**。 将从连接**SendPortFilter**到模型元素**SendNAOrder**模型元素。  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a>将导出到路线的数据库的模型  
  
1.  在 Visual Studio 中，右键单击的设计图面**验证**路线，，然后单击**导出模型**。  
  
    > [!NOTE]
    >  路线已导出到路线的数据库，现在可以使用通过路线选择器管道组件。  
  
2.  保存所有项目。  
  
## <a name="steps"></a>步骤  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a>若要创建和配置 ESB 入口  
  
1.  单击**启动**在任务栏中，指向**所有程序**，指向**BizTalk Server**，然后单击**BizTalk Server 管理**。  
  
2.  在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开**Microsoft.Practices.ESB**。  
  
3.  右键单击**接收位置**，指向**新建**，然后单击**单向接收位置**。  
  
4.  在**选择接收端口**对话框中，单击**OnRamp.Itinerary**，然后单击**确定**。  
  
5.  在**接收位置属性**对话框中，键入**OnRamp.Itinerary.HowTo**中**名称**框。  
  
6.  在**类型**下拉列表中，单击**文件**，然后单击**配置**。  
  
7.  在**文件传输属性**对话框中，键入**C:\HowTos\DropFolder**中**接收文件夹**框中，并依次**确定**。  
  
#### <a name="to-configure-the-on-ramp-to-perform-message-validation"></a>若要配置上的负载增加执行消息验证  
  
1.  在**接收位置属性**对话框中，在**接收管道**下拉列表中，单击**ItinerarySelectReceiveXml**，然后单击省略号按钮 （...).  
  
2.  使用**配置管道**对话框中，配置以下各项**XML 反汇编程序**组件属性：  
  
    1.  展开 GlobalBank.Esb 应用程序，，然后单击**架构**。 右键单击**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**，然后单击**属性**。 复制**名称**和**程序集**属性并将其粘贴到文本文件。  
  
    2.  在**拆卸**组件，请单击**True**中**ValidateDocument**下拉列表。  
  
    3.  单击**DocumentSpecNames**属性，再然后键入完全限定名称的架构。 完全限定的名名称开头后, 跟一个逗号和在步骤中提取的程序集信息。 以下是一个示例：  
  
         GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc，GlobalBank.ESB.DynamicResolution.Schemas，版本 = 2.0.0.0，区域性 = neutral，PublicKeyToken = c2c8b2b87f54180a  
  
        > [!NOTE]
        >  这是架构的要进行验证，则的完全限定的名称它包含的架构名称和四个程序集属性： 程序集名称、 版本、 区域性和公钥标记。 允许多个值;用管道 (&#124;) 分隔多个架构符号。  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a>若要配置路线选择器管道组件  
  
1.  在**配置管道**对话框框中，配置以下各项**路线选择器**组件属性：  
  
    1.  单击**ItineraryFactKey**属性，再然后键入**Resolver.Itinerary**。  
  
    2.  单击**ResolverConnectionString**属性，再然后键入**路线：\\\name=Validation;**。  
  
    3.  单击**确定**关闭**配置管道**对话框。  
  
2.  单击**确定**关闭**接收位置属性**对话框。  
  
3.  在 BizTalk Server 管理控制台中，右键单击**OnRamp.Itinerary.HowTo**接收位置，并依次**启用**。  
  
#### <a name="to-test-the-message-validation-and-itinerary-selection"></a>若要测试的消息验证和路线选择  
  
1.  在 Windows 资源管理器，浏览到 C:\HowTos。  
  
2.  复制 （不移动） 到 DropFolder 文件夹 NAOrderDoc.xml。  
  
3.  浏览到 C:\HowTos\Out。验证 Validated%MessageID%.xml 已写入到目录。  
  
    > [!NOTE]
    >  有效的消息完成其路线基于的路由，按预期方式。  
  
4.  删除扩展文件夹 Validated%MessageID%.xml。  
  
5.  在 Windows 资源管理器，浏览到 C:\HowTos。  
  
6.  复制 （不移动） 到 DropFolder 文件夹 Invalid.xml。  
  
7.  浏览到 C:\HowTos\Out。验证已传递任何新的消息。  
  
    > [!NOTE]
    >  无法验证消息;因此，基于路线的路由无法完成。  
  
8.  单击**启动**在任务栏中，指向**管理工具**，然后单击**事件查看器**。  
  
9. 在事件查看器中，展开**Windows 日志**，然后单击**应用程序**。  
  
10. 找到的最新事件其中**源**是**BizTalk Server**，和**事件 ID**是**5719**。  
  
    > [!NOTE]
    >  提交和失败的无效消息应用程序事件日志导致的异常条目。  
  
11. 在 BizTalk Server 管理控制台中，右键单击**OnRamp.Itinerary.HowTo**接收位置，并依次**禁用**。  
  
12. 后**OnRamp.Itinerary.HowTo**接收位置处于禁用状态，右键单击它，，然后单击**删除**。 在**确认删除接收位置**对话框中，单击**是**。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [如何：使用业务规则策略选择路线](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [开发活动](../esb-toolkit/development-activities.md)  
  
-   [安装和运行动态解析示例](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)