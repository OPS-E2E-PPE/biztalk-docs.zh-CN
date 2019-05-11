---
title: 如何：解析服务终结点使用 UDDI 类别搜索 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 61ac5d37-5529-4509-a948-415453944e01
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa3f0d054af872e0ac04338355c34c03b0139f5f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258422"
---
# <a name="how-to-resolve-a-service-endpoint-using-a-uddi-category-search"></a>如何：解析服务终结点使用 UDDI 类别搜索
## <a name="goal"></a>目的  
 本部分演示如何使用 ESB 设计器特定于域的语言 (DSL) 来创建基于路线的传送名单使用通用描述、 发现和集成 (UDDI) 3 解析程序找到服务终结点使用一个类别搜索。 在此方案中，服务终结点将是在 UDDI 中发布一个文件终结点。  
  
 在本操作指南主题中，您将完成以下步骤：  
  
-   创建路线传送名单以解析服务终结点。  
  
-   配置路线以便将消息路由到服务终结点使用 UDDI 3 冲突解决程序。  
  
-   测试使用路线测试客户端示例应用程序的路线。  
  
## <a name="prerequisites"></a>先决条件  
 本操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。  
  
## <a name="steps"></a>步骤  
  
#### <a name="to-create-an-itinerary-model"></a>若要创建路线模型  
  
1.  在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器中右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。  
  
3.  在中**添加新项**对话框中，键入**UDDI3CategorySearch**中**名称**框，并单击**添加**。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>若要配置的路线属性  
  
1.  在 Visual Studio 中，单击的设计图面**UDDI3CategorySearch.itinerary**。 在中**UDDI3CategorySearch**属性窗口中，配置以下属性：  
  
    1.  在中**模型导出程序**下拉列表中，单击**XML 路线导出程序**。  
  
    2.  下**扩展器设置**部分中下, 一步**路线 XML 文件**属性中，单击省略号按钮 （...）。  
  
    3.  在中**选择 XML 文件**对话框中，键入**C:\HowTos\Itineraries\UDDI3CategorySearch**中**文件名**框中，然后依次**保存**.  
  
        > [!NOTE]
        >  此步骤中，可将路线以 XML 形式导出到本地文件位置。 通过为行程数据库，而不导出到本地文件的位置，路线，路线使用 ESB 测试客户端应用程序的测试。 您将完成此过程更高版本的本操作指南主题。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>若要定义路线的结构  
  
1.  从工具箱拖动**接入点**至设计图面上的模型元素。 在中**OnRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**ReceiveNAOrder**。  
  
    2.  在中**Extender**下拉列表中，单击**接入点 ESB 扩展器**。  
  
    3.  在中**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
    4.  在中**接收端口**下拉列表中，单击**OnRamp.Itinerary**。  
  
2.  从工具箱拖动**路线服务**至设计图面上的模型元素。 在中**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**CategoryRoute**。  
  
    2.  在**路线服务 Extender**下拉列表中，单击**消息扩展器**。  
  
    3.  在中**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。  
  
    4.  在中**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**  
  
3.  右键单击**冲突解决程序**系列**CategoryRoute**模型元素，然后单击**添加新解析程序**。 在中**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**CategorySearch**。  
  
    2.  在中**解析程序实现**下拉列表中，单击**Uddi3 冲突解决程序扩展**。  
  
    3.  在中**冲突解决程序名字对象**下拉列表中，单击**UDDI3**。  
  
    4.  单击**类别搜索**属性，然后单击省略号按钮 （...）。  
  
    5.  在中**名称值属性编辑器**对话框中，单击**添加**。  
  
    6.  单击**名称**属性，并键入**uddi:esb:biztalkapplication**。  
  
    7.  单击**值**属性，并键入**GlobalBank.ESB**。  
  
    8.  在中**名称值属性编辑器**对话框中，单击**添加**。  
  
    9. 单击**名称**属性，并键入**uddi:esb:portname**。  
  
    10. 单击**值**属性，并键入**OrderFileServicev3**。  
  
    11. 在中**名称值属性编辑器**对话框中，单击**添加**。  
  
    12. 单击**名称**属性，并键入**uddi:esb:version**。  
  
    13. 单击**值**属性，并键入**1**。  
  
    14. 单击**确定**以关闭**名称值属性编辑器**对话框。  
  
4.  右键单击**CategorySearch**冲突解决程序，并单击**测试解析程序配置**。  
  
    > [!NOTE]
    >  验证显示在输出窗口中的输出。  
  
5.  在工具箱中，单击**连接器**。 将从连接**ReceiveNAOrder**到模型元素**CategoryRoute**模型元素。  
  
6.  从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**CategoryRoute**模型元素。 在中**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**SendNAOrder**。  
  
    2.  在**Extender**下拉列表中，单击**关闭负载增加 ESB 扩展器**。  
  
    3.  在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在中**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。  
  
7.  从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**CategoryRoute**模型元素和**SendNAOrder**模型元素。 在中**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**SendPortFilter**。  
  
    2.  在**路线服务 Extender**下拉列表中，单击**接入点关闭扩展器**。  
  
    3.  在中**关闭负载增加**下拉列表中，展开**SendNAOrder**，然后单击**发送处理程序**。  
  
8.  在工具箱中，单击**连接器**。 将从连接**CategoryRoute**到模型元素**SendPortFilter**模型元素。  
  
9. 在工具箱中，单击**连接器**。 将从连接**SendPortFilter**到模型元素**SendNAOrder**模型元素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>若要导出与路线测试客户端一起使用的模型  
  
1.  在 Visual Studio 中，右键单击设计图面的**UDDI3CategorySearch**路线，并单击**导出模型**。  
  
    > [!NOTE]
    >  在 Visual Studio 中打开的 XML 版本的路线。  
  
2.  保存项目的所有项目。  
  
3.  在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries 并请注意，您的路线 XML (UDDI3CategorySearch.xml) 创建。  
  
#### <a name="to-test-the-itinerary"></a>若要测试路线  
  
1.  打开路线测试客户端示例应用程序使用过程中创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。  
  
2.  在路线测试客户端，清除**使用 WCF 服务**复选框，然后依次**负载路线**。  
  
3.  在中**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。 选择**UDDI3CategorySearch.xml**，然后单击**打开**加载路线。  
  
4.  单击**确定**清除**成功加载路线**消息。  
  
5.  在路线测试客户端，单击下一步的省略号按钮 （...）**负载消息**框。  
  
6.  在中**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。 选择 NAOrderDoc.xml，，然后单击**打开**加载测试消息。  
  
7.  单击**提交请求**按钮。 测试完成后，单击**确定**若要消除出现的确认。  
  
8.  在 Windows 资源管理器，浏览到**C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out**并确认 **%MessageID%.xml**消息写入目录。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [如何：解析服务终结点使用 UDDI 绑定密钥搜索](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search.md)  
  
-   [开发活动](../esb-toolkit/development-activities.md)  
  
-   [使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)