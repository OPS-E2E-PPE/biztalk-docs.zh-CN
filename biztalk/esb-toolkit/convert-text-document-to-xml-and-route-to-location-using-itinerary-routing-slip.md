---
title: "如何： 将文本文档转换为 XML 和路由到文件位置使用路线的路由滑动 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 01597a5f-5ca3-440e-ad97-70332233f319
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8284c1623329133533fe03aab567b1281f07c1a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-convert-a-text-document-to-xml-and-route-to-a-file-location-using-an-itinerary-routing-slip"></a>如何： 将文本文档转换为 XML 和路由到使用路线的路由滑动的文件位置
## <a name="goal"></a>目的  
 部分演示如何创建将将文本文档转换为 XML，选择适当的路线，然后将消息路由到某个文件位置的管道。  
  
 在本操作方法主题中，你将完成以下步骤：  
  
-   使用管道接收平面文件文档并将其转换为 XML。  
  
-   配置要解决适当的路由滑动的路线选择器管道组件。  
  
-   创建入口使用自定义的管道。  
  
-   测试路线基于路由的平面文件消息。  
  
## <a name="prerequisites"></a>先决条件  
 此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。  
  
## <a name="before-you-begin"></a>开始之前  
 本操作方法主题中的更高版本执行的步骤之前，请完成以下任务：  
  
-   部署**DataFormatTransformation**路线。  
  
-   创建测试消息。  
  
 下面的过程介绍如何执行其中每个操作。  
  
#### <a name="to-deploy-the-dataformattransformation-itinerary"></a>若要部署 DataFormatTransformation 路线  
  
1.  在 Visual Studio 中，打开 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation\DataFormatTransformation.sln。  
  
2.  在解决方案资源管理器，在**Itinerary.Library**项目中，双击**DataFormatTransformation.itinerary**在路线设计器中打开它。  
  
3.  在 Visual Studio 中，单击的设计图面**DataFormatTransformation.itinerary**。 在**DataFormatTransformation.itinerary**属性窗口中，配置以下属性：  
  
    1.  在**路线状态**下拉列表中，单击**已部署**。  
  
    2.  在**模型导出程序**下拉列表中，单击**数据库路线导出程序**。  
  
    3.  单击旁边的省略号按钮 （...）**路线数据库**属性。  
  
    4.  在**连接属性**对话框中，选择承载路线存储库数据库中，SQL Server，然后指定数据库的名称 (默认名称是**EsbItineraryDb**)。  
  
4.  保存所有项目。  
  
5.  在 Visual Studio 中，右键单击的设计图面**DataModelTransformation**路线，，然后单击**导出模型**。  
  
#### <a name="to-create-the-receive-pipeline"></a>若要创建接收管道  
  
1.  在 Visual Studio 中，右键单击**DataFormatTransformation.Schemas**，然后单击**属性**。 单击**应用程序**，然后键入**GlobalBank.ESB.DataFormatTransformation.Schemas**中**程序集名称**框。  
  
2.  右键单击**DataFormatTransformation.Schemas**，然后单击**属性**。 单击**签名**，然后确认**对程序集签名**复选框处于选中状态，该程序集位置指向**。\\...\\..\\..\\..\\..\keys\Microsoft.Practices.ESB.snk**。  
  
3.  右键单击**DataFormatTransformation.Pipelines**，然后单击**删除**。  
  
4.  右键单击**DataFormatTransformation**，指向**添加**，然后单击**新项目**。 单击**Biztalk 项目**，然后单击**空 Biztalk 服务器项目**。 在**名称**框中，键入**DataFormatTransformationReceive.Pipeline**。  
  
5.  右键单击**DataFormatTransformationReceive.Pipeline**，然后单击**属性**。 单击**签名**，然后确认**对程序集签名**复选框处于选中状态，该程序集位置指向**C:\projects\Microsoft.Practices.ESB\keys\Microsoft.Practices.ESB.snk**。  
  
6.  右键单击**DataFormatTransformationReceive.Pipeline**，指向**添加**，然后单击**新项**。  
  
7.  在**添加新项**对话框中，单击**接收管道**在模板窗格中。 在**名称**框中，键入**ItinerarySelectReceiveFF**，然后单击**添加**。  
  
8.  右键单击**引用**作为 DataFormatTransformationReceive.Pipeline 项目，然后单击**添加引用**。 单击**项目**选项卡上，并依次**DataFormatTransformation.Schemas**。 单击**确定**添加引用。  
  
9. 从工具箱中，拖动**平面文件反汇编程序**到管道组件**拆卸**管道的阶段。  
  
10. 在平面文件的属性窗口中反汇编，请单击**DataModelTransformation.Schemas.NAOrderDocFF**中**文档架构**下拉列表。  
  
11. 从工具箱中，拖动**ESB 路线选择器**到管道组件**解决方**管道的阶段。  
  
12. 从工具箱中，拖动**ESB 调度程序**到管道组件**解决方**阶段的管道，然后将其在放**ESB 路线选择器**管道组件。  
  
13. 保存所有项目。  
  
## <a name="to-create-the-test-message"></a>若要创建测试消息  
  
1.  单击 DataFormatTransformation.Schemas 项目 NAOrderDocFF.xsd 架构文件中的一次。 在 Visual Studio 的属性窗格中，将更改以下两个属性：  
  
    -   **生成实例输出类型**。 单击以将其更改为此属性的下拉列表**本机**。  
  
    -   **输出实例文件名**。 单击此属性的省略号按钮 （…） 并接受 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation 的默认路径。 在**文件名**框中，键入**NAOrderDocFF**，然后单击**保存**。  
  
2.  右键单击**NAOrderDocFF.xsd**下**DataFormatTransformation.Schemas**，然后单击**生成实例**。 此时，你应具有 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation 目录中生成一个新文件。  
  
3.  复制 （不移动） 到 C:\HowTos 从 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation NAOrderDocFF.txt 的文件。  
  
    > [!NOTE]
    >  这是你将收到并将转换为 XML 的消息。 本文档表示北美顺序文档的平面文件版本。  
  
## <a name="steps"></a>步骤  
  
#### <a name="to-deploy-the-receive-pipeline-and-the-schema"></a>若要部署接收管道和架构  
  
1.  右键单击**DataFormatTransformationReceive.Pipeline**，然后单击**属性**。 单击**部署**，然后键入**Microsoft.Practices.ESB**中**应用程序名称**框。  
  
2.  右键单击**DataFormatTransformation.Schemas**项目，，然后单击**属性**。 单击**部署**，然后键入**Microsoft.Practices.ESB**中**应用程序名称**框。  
  
3.  关闭两个属性窗格**DataFormatTransformationReceive.Pipeline**和**DataFormatTransformation.Schemas**。  
  
4.  在解决方案资源管理器，右键单击**DataFormatTransformation**项目，，然后单击**部署解决方案**。  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a>若要创建和配置 ESB 入口  
  
1.  单击**启动**在任务栏中，指向**所有程序**，指向**BizTalk Server**，然后单击**BizTalk Server 管理**。  
  
2.  在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后单击**Microsoft.Practices.ESB**。  
  
3.  右键单击**接收位置**，指向**新建**，然后单击**单向接收位置**。  
  
4.  在**选择接收端口**对话框中，单击**OnRamp.Itinerary**，然后单击**确定**。  
  
5.  在**接收位置属性**对话框中，在**名称**框中，键入**OnRamp.Itinerary.FlatFile.FILE**。  
  
6.  在**类型**下拉列表中，单击**文件**，然后单击**配置**。  
  
7.  在**文件传输属性**对话框中，在**接收文件夹**框中，键入**C:\HowTos\DropFolder**。  
  
8.  在**文件传输属性**对话框中，在**文件掩码**框中，键入 **\*.txt**，然后单击**确定**。  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a>若要配置路线选择器管道组件  
  
1.  在**接收位置属性**对话框中，单击**ItinerarySelectReceiveFF**中**接收管道**下拉列表中，然后单击省略号按钮 （…）。  
  
2.  使用**配置管道**对话框中，配置以下各项**路线选择器**组件属性：  
  
    1.  单击**ItineraryFactKey**属性，再然后键入**Resolver.Itinerary**。  
  
    2.  单击**ResolverConnectionString**属性中，键入**路线：\\\name=DataFormatTransformation;** ，然后单击**确定**。  
  
3.  单击**确定**关闭**接收位置属性**对话框。  
  
4.  在 BizTalk Server 管理控制台中，右键单击**OnRamp.Itinerary.FlatFile.FILE**接收位置，并依次**启用**。  
  
#### <a name="to-test-itinerary-based-routing-of-a-flat-file-message"></a>若要测试基于路线的平面文件消息的路由  
  
1.  在 Windows 资源管理器，浏览到 C:\HowTos。  
  
2.  复制 （不移动） 到 C:\HowTos\DropFolder NAOrderDocFF.txt。  
  
3.  浏览到 C:\HowTos\Out。验证 DFT%MessageID%.xml 消息已写入到目录。  
  
4.  在 BizTalk Server 管理控制台中，右键单击**OnRamp.Itinerary.FlatFile.FILE**接收位置，并依次**禁用**。  
  
5.  后**OnRamp.Itinerary.FlatFile.FILE**接收位置处于禁用状态，右键单击它，，然后单击**删除**。 在**确认删除接收位置**对话框中，单击**是**。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [如何：转换消息并使用路线传送名单将生成的消息路由至文件位置](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [如何：使用路线传送名单将单条消息路由至多个收件人](../esb-toolkit/route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip.md)  
  
-   [开发活动](../esb-toolkit/development-activities.md)  
  
-   [消息转换模式](../esb-toolkit/message-transformation-patterns.md)