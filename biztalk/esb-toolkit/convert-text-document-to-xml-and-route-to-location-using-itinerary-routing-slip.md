---
title: 如何：将文本文档转换为 XML 并使用路线传送名单的文件位置的路由 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01597a5f-5ca3-440e-ad97-70332233f319
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9258493ebd15e12bcb10d4a4dba51a14fdb51c0c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302056"
---
# <a name="how-to-convert-a-text-document-to-xml-and-route-to-a-file-location-using-an-itinerary-routing-slip"></a>如何：将文本文档转换为 XML 并路由到使用路线传送名单的文件位置
## <a name="goal"></a>目的  
 部分演示如何创建一个管道，用于将转换为 XML 文本文档然后选择相应的路线并将消息路由到某个文件位置。  
  
 在本操作指南主题中，您将完成以下步骤：  
  
-   使用管道以接收平面文件文档并将其转换为 XML。  
  
-   配置路线选择器管道组件以解析相应的传送名单。  
  
-   创建入口使用自定义管道。  
  
-   测试基于路线的路由的平面文件消息。  
  
## <a name="prerequisites"></a>先决条件  
 本操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。  
  
## <a name="before-you-begin"></a>开始之前  
 在本操作指南主题的后面部分执行的步骤之前，请完成以下任务：  
  
- 部署**DataFormatTransformation**路线。  
  
- 创建测试消息。  
  
  以下过程介绍如何执行其中每项功能。  
  
#### <a name="to-deploy-the-dataformattransformation-itinerary"></a>若要部署 DataFormatTransformation 路线  
  
1.  In Visual Studio, open C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation\DataFormatTransformation.sln.  
  
2.  在解决方案资源管理器中**Itinerary.Library**项目中，双击**DataFormatTransformation.itinerary**在路线设计器中打开它。  
  
3.  在 Visual Studio 中，单击的设计图面**DataFormatTransformation.itinerary**。 在中**DataFormatTransformation.itinerary**属性窗口中，配置以下属性：  
  
    1.  在中**路线状态**下拉列表中，单击**已部署**。  
  
    2.  在中**模型导出程序**下拉列表中，单击**数据库路线导出程序**。  
  
    3.  单击省略号按钮 （...） 下一步**行程数据库**属性。  
  
    4.  在中**连接属性**对话框中，选择承载路线的存储库数据库的 SQL 服务器，然后指定数据库的名称 (默认名称是**EsbItineraryDb**)。  
  
4.  保存项目的所有项目。  
  
5.  在 Visual Studio 中，右键单击设计图面的**DataModelTransformation**路线，并单击**导出模型**。  
  
#### <a name="to-create-the-receive-pipeline"></a>若要创建的接收管道  
  
1.  在 Visual Studio 中，右键单击**DataFormatTransformation.Schemas**，然后单击**属性**。 单击**应用程序**，然后键入**GlobalBank.ESB.DataFormatTransformation.Schemas**中**程序集名称**框。  
  
2.  右键单击**DataFormatTransformation.Schemas**，然后单击**属性**。 单击**签名**，然后确认**程序集签名**复选框处于选中状态和程序集位置指向 **。\\...\\..\\..\\..\\..\keys\Microsoft.Practices.ESB.snk**。  
  
3.  右键单击**DataFormatTransformation.Pipelines**，然后单击**删除**。  
  
4.  右键单击**DataFormatTransformation**，依次指向**添加**，然后单击**新项目**。 单击**Biztalk 项目**，然后单击**空的 Biztalk Server 项目**。 在中**名称**框中，键入**DataFormatTransformationReceive.Pipeline**。  
  
5.  右键单击**DataFormatTransformationReceive.Pipeline**，然后单击**属性**。 单击**签名**，然后确认**程序集签名**复选框处于选中状态和程序集位置指向**C:\projects\Microsoft.Practices.ESB\keys\Microsoft.Practices.ESB.snk**。  
  
6.  右键单击**DataFormatTransformationReceive.Pipeline**，依次指向**添加**，然后单击**新项**。  
  
7.  在中**添加新项**对话框中，单击**接收管道**模板窗格中。 在中**名称**框中，键入**ItinerarySelectReceiveFF**，然后单击**添加**。  
  
8.  右键单击**引用**DataFormatTransformationReceive.Pipeline 项目，并单击**添加引用**。 单击**项目**选项卡，然后依次**DataFormatTransformation.Schemas**。 单击**确定**将引用添加。  
  
9. 从工具箱拖动**平面文件拆装器**管道组件**拆装**管道阶段。  
  
10. 在属性窗口中的平面文件反汇编，请单击**DataModelTransformation.Schemas.NAOrderDocFF**中**文档架构**下拉列表。  
  
11. 从工具箱拖动**ESB 路线选择器**管道组件**解析参与方**管道阶段。  
  
12. 从工具箱拖动**ESB 调度程序**管道组件**解析参与方**阶段的管道，然后将它下放**ESB 路线选择器**管道组件。  
  
13. 保存项目的所有项目。  
  
## <a name="to-create-the-test-message"></a>若要创建测试消息  
  
1.  DataFormatTransformation.Schemas 项目在 NAOrderDocFF.xsd 架构文件中单击一次。 在 Visual Studio 属性窗格中，更改以下两个属性：  
  
    -   **生成实例输出类型**。 单击以将其更改为此属性的下拉列表**本机**。  
  
    -   **输出实例文件名**。 单击此属性的省略号按钮 （...） 并接受 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation 的默认路径。 在中**文件名**框中，键入**NAOrderDocFF**，然后单击**保存**。  
  
2.  右键单击**NAOrderDocFF.xsd**下**DataFormatTransformation.Schemas**，然后单击**生成实例**。 此时，应具有 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation 目录中生成一个新文件。  
  
3.  复制 （不移动） 到 C:\HowTos NAOrderDocFF.txt C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation 从该文件。  
  
    > [!NOTE]
    >  这是将接收并将转换为 XML 的消息。 本文档表示 North American 订单文档的平面文件版本。  
  
## <a name="steps"></a>步骤  
  
#### <a name="to-deploy-the-receive-pipeline-and-the-schema"></a>若要部署接收管道和架构  
  
1.  右键单击**DataFormatTransformationReceive.Pipeline**，然后单击**属性**。 单击**部署**，然后键入**Microsoft.Practices.ESB**中**应用程序名称**框。  
  
2.  右键单击**DataFormatTransformation.Schemas**项目，并单击**属性**。 单击**部署**，然后键入**Microsoft.Practices.ESB**中**应用程序名称**框。  
  
3.  同时关闭属性窗格**DataFormatTransformationReceive.Pipeline**并**DataFormatTransformation.Schemas**。  
  
4.  在解决方案资源管理器中右键单击**DataFormatTransformation**项目，并单击**部署解决方案**。  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a>若要创建和配置 ESB 接入点  
  
1.  单击**启动**在任务栏上，依次指向**所有程序**，指向**BizTalk Server**，然后单击**BizTalk Server 管理**。  
  
2.  在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后单击**Microsoft.Practices.ESB**。  
  
3.  右键单击**接收位置**，依次指向**新建**，然后单击**单向接收位置**。  
  
4.  在中**选择接收端口**对话框中，单击**OnRamp.Itinerary**，然后单击**确定**。  
  
5.  在中**接收位置属性**对话框中**名称**框中，键入**OnRamp.Itinerary.FlatFile.FILE**。  
  
6.  在中**类型**下拉列表中，单击**文件**，然后单击**配置**。  
  
7.  在中**FILE 传输属性**对话框中**接收文件夹**框中，键入**C:\HowTos\DropFolder**。  
  
8.  在中**FILE 传输属性**对话框中**文件掩码**框中，键入 **\*.txt**，然后单击**确定**。  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a>若要配置路线选择器管道组件  
  
1.  在中**接收位置属性**对话框中，单击**ItinerarySelectReceiveFF**中**接收管道**下拉列表中，然后单击省略号按钮 （...）。  
  
2.  使用**配置管道**对话框可以配置以下**路线选择器**组件属性：  
  
    1.  单击**ItineraryFactKey**属性，并键入**Resolver.Itinerary**。  
  
    2.  单击**ResolverConnectionString**属性中，键入**路线：\\\name=DataFormatTransformation;** ，然后单击**确定**。  
  
3.  单击**确定**以关闭**接收位置属性**对话框。  
  
4.  在 BizTalk Server 管理控制台中，右键单击**OnRamp.Itinerary.FlatFile.FILE**接收位置，然后依次**启用**。  
  
#### <a name="to-test-itinerary-based-routing-of-a-flat-file-message"></a>若要测试基于路线的路由的平面文件消息  
  
1.  在 Windows 资源管理器，浏览到 C:\HowTos。  
  
2.  复制 （不移动） 到 C:\HowTos\DropFolder NAOrderDocFF.txt。  
  
3.  浏览到 C:\HowTos\Out。验证 DFT%MessageID%.xml 消息已写入到目录。  
  
4.  在 BizTalk Server 管理控制台中，右键单击**OnRamp.Itinerary.FlatFile.FILE**接收位置，然后依次**禁用**。  
  
5.  之后**OnRamp.Itinerary.FlatFile.FILE**接收位置被禁用，右键单击它，并单击**删除**。 在中**确认删除接收位置**对话框中，单击**是**。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [如何：转换消息并将生成的消息路由到使用路线传送名单的文件位置](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [如何：将一条消息路由到多个收件人使用路线传送名单](../esb-toolkit/route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip.md)  
  
-   [开发活动](../esb-toolkit/development-activities.md)  
  
-   [消息转换模式](../esb-toolkit/message-transformation-patterns.md)