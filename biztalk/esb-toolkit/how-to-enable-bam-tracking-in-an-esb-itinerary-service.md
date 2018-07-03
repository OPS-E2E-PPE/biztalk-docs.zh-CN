---
title: 如何： 启用 BAM 跟踪在 ESB 路线服务中 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58859937-f8d0-4c33-9a7a-62fec8441936
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27d0338ad56daa342fce1d339b9e7aa43fd7e25e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991542"
---
# <a name="how-to-enable-bam-tracking-in-an-esb-itinerary-service"></a>如何： 启用 BAM 跟踪在 ESB 路线服务
## <a name="goal"></a>目的  
 本部分演示如何启用业务活动监视 (BAM) 跟踪现有路线。  
  
 在本操作指南主题中，您将完成以下步骤：  
  
-   启用用于跟踪使用业务活动监视的路线服务的属性。  
  
-   测试使用路线测试客户端示例应用程序的 BAM 跟踪。  
  
-   验证 BAM 结果使用 SQL 查询。  
  
## <a name="prerequisites"></a>必要條件  
 本操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。  
  
## <a name="before-you-begin"></a>开始之前  
 在本操作指南主题的后面部分执行的步骤之前，请完成以下任务：  
  
- 创建的 ESB 路线域特定语言 (DSL) 模型。  
  
- 配置路线的属性。  
  
- 定义路线的结构。  
  
  以下过程介绍如何执行其中每项功能。  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>若要创建的 ESB 路线 DSL 模型  
  
1.  在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器中右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。  
  
3.  在中**添加新项**对话框中，单击**ItineraryDsl**模板窗格中。  
  
4.  在中**名称**框中，键入**BamTracking**，然后单击**添加**。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>若要配置的路线属性  
  
1.  在 Visual Studio 中，单击的设计图面**BamTracking.itinerary**。 在中**BamTracking**属性窗口中，配置以下属性：  
  
    1.  在中**模型导出程序**下拉列表中，单击**XML 路线导出程序**。  
  
    2.  在中**扩展器设置**部分中下, 一步**路线 XML 文件**属性中，单击省略号按钮 （...）。  
  
    3.  在中**选择 XML 文件**对话框中**文件名**框中，键入**C:\HowTos\Itineraries\BamTracking** ，然后单击**保存**。  
  
        > [!NOTE]
        >  此步骤中，可将路线以 XML 形式导出到本地文件位置。 通过为行程数据库，而不导出到本地文件的位置，路线，路线使用 ESB 测试客户端应用程序的测试。 您将完成此过程更高版本的本操作指南主题。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>若要定义路线的结构  
  
1.  从工具箱拖动**接入点**至设计图面上的模型元素。 在中**OnRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**ReceiveNAOrder**。  
  
    2.  在中**Extender**下拉列表中，单击**接入点 ESB 服务扩展**。  
  
    3.  在中**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
    4.  在中**接收端口**下拉列表中，单击**OnRamp.Itinerary**。  
  
2.  从工具箱拖动**路线服务**模型元素到设计图面，然后将它放到右侧**接入点**模型元素。 在中**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**MapNAOrderToCNOrder**。  
  
    2.  在**路线服务 Extender**下拉列表中，单击**Messaging 路线服务扩展**。  
  
        > [!NOTE]
        >  此属性定义，过程将花费 （消息传送） 管道中的位置。 或者，如果该过程会发生在业务流程中，设置**路线服务 Extender**属性设置为**业务流程路线服务扩展**。  
  
    3.  在中**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。  
  
    4.  在中**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Transform**。  
  
3.  右键单击**冲突解决程序**系列**MapNAOrderToCNOrder**模型元素，然后单击**添加新解析程序**。 在中**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**StaticallySpecifyTheMap**。  
  
    2.  在中**解析程序实现**下拉列表中，单击**静态解析程序扩展**。  
  
    3.  在中**转换的类型**下拉列表中，单击**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**。  
  
    4.  在中**TransportName**下拉列表中，单击**文件**。  
  
4.  在工具箱中，单击**连接器**。 将从连接**ReceiveNAOrder**到模型元素**MapNAOrderToCNOrder**模型元素。  
  
5.  从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**MapNAOrderToCNOrder**模型元素。 在中**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**SendCNOrder**。  
  
    2.  在中**Extender**下拉列表中，单击**关闭负载增加 ESB 服务扩展**。  
  
    3.  在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在中**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。  
  
6.  从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**MapNAOrderToCNOrder**模型元素和**SendCNOrder**模型元素。 在中**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**SendPortFilter**。  
  
    2.  在**路线服务 Extender**下拉列表中，单击**接入点关闭路线服务扩展**。  
  
    3.  在中**关闭负载增加**下拉列表中，展开**SendCNOrder**，然后单击**发送处理程序**。  
  
7.  右键单击**冲突解决程序**系列**SendPortFilter**模型元素，然后单击**添加新解析程序**。 在中**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**ConfigureFolderSettings**。  
  
    2.  在中**解析程序实现**下拉列表中，单击**静态解析程序扩展**。  
  
    3.  在中**传输名称**下拉列表中，单击**文件**。  
  
    4.  单击**传输位置**属性，并键入**C:\HowTos\Out\BAM%MessageID%.xml**  
  
        > [!NOTE]
        >  每个关闭接入点将具有与之; 关联的路线服务路线服务属性和关闭负载增加的属性的组合定义的动态发送端口的订阅。  
  
8.  在工具箱中，单击**连接器**。 将从连接**MapNAOrderToCNOrder**到模型元素**SendPortFilter**模型元素。  
  
9. 在工具箱中，单击**连接器**。 将从连接**SendPortFilter**到模型元素**SendCNOrder**模型元素。  
  
10. 保存项目的所有项目。  
  
## <a name="steps"></a>步骤  
  
#### <a name="to-modify-the-itinerary"></a>若要修改路线  
  
1.  在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器中双击**BamTracking.itinerary**。  
  
3.  单击**MapNAOrderToCNOrder**路线服务元素。  
  
4.  在中**MapNAOrderToCNOrder**属性窗口中，单击**True**中**启用跟踪**下拉列表。  
  
5.  单击**SendPortFilter**路线服务元素。  
  
6.  在中**SendPortFilter**属性窗口中，单击**True**中**启用跟踪**下拉列表。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>若要导出与路线测试客户端一起使用的模型  
  
1.  在 Visual Studio 中，右键单击设计图面的**BamTracking**路线，并单击**导出模型**。  
  
    > [!NOTE]
    >  在 Visual Studio 中打开的 XML 版本的路线。  
  
2.  保存项目的所有项目。  
  
3.  在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries 并请注意，您的路线 XML (BamTracking.xml) 创建。  
  
#### <a name="to-test-the-itinerary"></a>若要测试路线  
  
1.  打开路线测试客户端示例应用程序使用过程中创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。  
  
2.  在路线测试客户端，清除**使用 WCF 服务**复选框，然后依次**负载路线**。  
  
3.  在中**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。 选择**BamTracking.xml**，然后单击**打开**加载路线。  
  
4.  单击**确定**清除**成功加载路线**消息。  
  
5.  在路线测试客户端，单击下一步的省略号按钮 （...）**负载消息**框。  
  
6.  在中**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。 选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。  
  
7.  单击**提交请求**按钮。 测试完成后，单击**确定**若要消除出现的确认。  
  
8.  在 Windows 资源管理器，浏览到 C:\HowTos\Out。验证 BAM%MessageID%.xml 消息已写入到目录。  
  
#### <a name="to-verify-message-tracking"></a>若要验证消息跟踪  
  
1. 单击**启动**在任务栏上，依次指向**所有程序**，指向[!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]，然后单击**SQL Server Management Studio**。  
  
2. 单击 **“新建查询”**。  
  
3. 在查询窗格中，键入以下命令：  
  
   ```  
   SELECT *  
   FROM [BAMPrimaryImport].[dbo].[bam_ItineraryServiceActivity_Completed]  
   GO  
   ```  
  
4. 单击 **“执行”**。  
  
5. 在结果窗格中，使用**时间戳**列来查找最新条目。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [开发活动](../esb-toolkit/development-activities.md)  
  
-   [消息路由模式](../esb-toolkit/message-routing-patterns.md)  
  
-   [使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)