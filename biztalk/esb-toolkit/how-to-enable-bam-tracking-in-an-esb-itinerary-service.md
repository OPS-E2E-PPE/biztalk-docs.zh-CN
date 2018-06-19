---
title: 如何： 启用 BAM 在 ESB 路线服务中跟踪 |Microsoft 文档
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
ms.openlocfilehash: 011de667e06f4275fe75a28b6566a6bc393cf841
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009622"
---
# <a name="how-to-enable-bam-tracking-in-an-esb-itinerary-service"></a>如何： 启用 BAM 在 ESB 路线服务中跟踪
## <a name="goal"></a>目的  
 本部分演示如何启用业务活动监视 (BAM) 跟踪现有路线。  
  
 在本操作方法主题中，你将完成以下步骤：  
  
-   启用用于跟踪使用业务活动监视器的路线服务的属性。  
  
-   测试 BAM 跟踪使用路线测试客户端示例应用程序。  
  
-   验证使用 SQL 查询的 BAM 结果。  
  
## <a name="prerequisites"></a>先决条件  
 此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。  
  
## <a name="before-you-begin"></a>开始之前  
 本操作方法主题中的更高版本执行的步骤之前，请完成以下任务：  
  
-   创建一个 ESB 路线域特定语言 (DSL) 模型。  
  
-   配置路线的属性。  
  
-   定义路线的结构。  
  
 下面的过程介绍如何执行其中每个操作。  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>若要创建 ESB 路线 DSL 模型  
  
1.  在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器，右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。  
  
3.  在**添加新项**对话框中，单击**ItineraryDsl**在模板窗格中。  
  
4.  在**名称**框中，键入**BamTracking**，然后单击**添加**。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>若要配置路线的属性  
  
1.  在 Visual Studio 中，单击的设计图面**BamTracking.itinerary**。 在**BamTracking**属性窗口中，配置以下属性：  
  
    1.  在**模型导出程序**下拉列表中，单击**XML 路线导出程序**。  
  
    2.  在**扩展程序设置**部分，旁边**路线 XML 文件**属性，单击省略号按钮 （…）。  
  
    3.  在**选择 XML 文件**对话框中，在**文件名**框中，键入**C:\HowTos\Itineraries\BamTracking** ，然后单击**保存**。  
  
        > [!NOTE]
        >  此步骤允许您路线作为 XML 导出到本地文件位置。 通过到路线的数据库，而不导出到本地文件的位置，一条路线使测试路线使用 ESB 测试客户端应用程序。 你将完成本操作方法主题中后面此过程。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>若要定义路线的结构  
  
1.  从工具箱中，拖动**上负载增加**到设计图面上的模型元素。 在**OnRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**ReceiveNAOrder**。  
  
    2.  在**扩展程序**下拉列表中，单击**上负载增加 ESB 服务扩展**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
    4.  在**接收端口**下拉列表中，单击**OnRamp.Itinerary**。  
  
2.  从工具箱中，拖动**路线服务**模型元素到设计图面，然后将其放到右侧**上负载增加**模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**MapNAOrderToCNOrder**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**Messaging 路线服务扩展**。  
  
        > [!NOTE]
        >  此属性定义的过程将需要在管道 （消息传送） 中的位置。 或者，如果过程将需要一个业务流程中的位置，则设置**路线服务扩展程序**属性**Orchestration 路线服务扩展**。  
  
    3.  在**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。  
  
    4.  在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Transform**。  
  
3.  右键单击**冲突解决程序**集合**MapNAOrderToCNOrder**模型元素，并依次**添加新解析程序**。 在**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**StaticallySpecifyTheMap**。  
  
    2.  在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。  
  
    3.  在**转换类型**下拉列表中，单击**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**。  
  
    4.  在**TransportName**下拉列表中，单击**文件**。  
  
4.  在工具箱中，单击**连接器**。 将从连接**ReceiveNAOrder**到模型元素**MapNAOrderToCNOrder**模型元素。  
  
5.  从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**MapNAOrderToCNOrder**模型元素。 在**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SendCNOrder**。  
  
    2.  在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 服务扩展**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。  
  
6.  从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**MapNAOrderToCNOrder**模型元素和**SendCNOrder**模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SendPortFilter**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**关闭负载增加路线服务扩展**。  
  
    3.  在**关闭负载增加**下拉列表中，展开**SendCNOrder**，然后单击**发送处理程序**。  
  
7.  右键单击**冲突解决程序**集合**SendPortFilter**模型元素，并依次**添加新解析程序**。 在**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**ConfigureFolderSettings**。  
  
    2.  在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。  
  
    3.  在**传输名称**下拉列表中，单击**文件**。  
  
    4.  单击**传输位置**属性，再然后键入**C:\HowTos\Out\BAM%MessageID%.xml**  
  
        > [!NOTE]
        >  每个关闭提升将具有与之; 关联的路线服务路线服务属性和关闭负载增加的属性的组合定义动态发送端口的订阅。  
  
8.  在工具箱中，单击**连接器**。 将从连接**MapNAOrderToCNOrder**到模型元素**SendPortFilter**模型元素。  
  
9. 在工具箱中，单击**连接器**。 将从连接**SendPortFilter**到模型元素**SendCNOrder**模型元素。  
  
10. 保存所有项目。  
  
## <a name="steps"></a>步骤  
  
#### <a name="to-modify-the-itinerary"></a>若要修改路线  
  
1.  在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器中，双击**BamTracking.itinerary**。  
  
3.  单击**MapNAOrderToCNOrder**路线服务元素。  
  
4.  在**MapNAOrderToCNOrder**属性窗口中，单击**True**中**启用跟踪**下拉列表。  
  
5.  单击**SendPortFilter**路线服务元素。  
  
6.  在**SendPortFilter**属性窗口中，单击**True**中**启用跟踪**下拉列表。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>若要导出与路线测试客户端一起使用的模型  
  
1.  在 Visual Studio 中，右键单击的设计图面**BamTracking**路线，，然后单击**导出模型**。  
  
    > [!NOTE]
    >  在 Visual Studio 中打开的 XML 版本的路线。  
  
2.  保存所有项目。  
  
3.  在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries，并注意你路线 XML (BamTracking.xml) 创建。  
  
#### <a name="to-test-the-itinerary"></a>若要测试路线  
  
1.  打开路线测试客户端示例应用程序使用期间创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。  
  
2.  在路线测试客户端中，清除**使用 WCF 服务**复选框，并依次**负载路线**。  
  
3.  在**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。 选择**BamTracking.xml**，然后单击**打开**加载路线。  
  
4.  单击**确定**清除**成功加载路线**消息。  
  
5.  在路线测试客户端上，单击旁边的省略号按钮 （...）**负载消息**框。  
  
6.  在**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。 选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。  
  
7.  单击**提交请求**按钮。 在测试完成后，单击**确定**关闭出现的确认。  
  
8.  在 Windows 资源管理器，浏览到 C:\HowTos\Out。验证 BAM%MessageID%.xml 消息已写入到目录。  
  
#### <a name="to-verify-message-tracking"></a>若要验证邮件跟踪  
  
1.  单击**启动**在任务栏中，指向**所有程序**，指向[!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]，然后单击**SQL Server Management Studio**。  
  
2.  单击 **“新建查询”**。  
  
3.  在查询窗格中，键入以下命令：  
  
    ```  
    SELECT *  
    FROM [BAMPrimaryImport].[dbo].[bam_ItineraryServiceActivity_Completed]  
    GO  
    ```  
  
4.  单击 **“执行”**。  
  
5.  在结果窗格中，使用**时间戳**列找到最新条目。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [开发活动](../esb-toolkit/development-activities.md)  
  
-   [消息路由模式](../esb-toolkit/message-routing-patterns.md)  
  
-   [使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)