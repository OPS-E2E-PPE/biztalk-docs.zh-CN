---
title: "如何： 解决使用绑定密钥搜索 UDDI 服务终结点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a685641-2beb-4153-a9ba-c766679ce48e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23e73ecbc5d1ef88fe2b8bdc7f19f56f6f2ae207
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search"></a>如何： 解决使用绑定密钥搜索 UDDI 服务终结点
## <a name="goal"></a>目的  
 本部分演示如何使用 ESB 设计器域特定语言 (DSL) 来创建使用的通用的说明，发现，基于路线的路由滑动和集成 (UDDI) 3 冲突解决程序来查找服务终结点使用的绑定密钥搜索。 在此方案中，服务终结点将在 UDDI 中发布一个文件终结点。  
  
 在本操作方法主题中，你将完成以下步骤：  
  
-   创建路线的路由滑动，若要解决的服务终结点。  
  
-   配置路线后，若要将消息路由到服务终结点使用 UDDI 3 冲突解决程序。  
  
-   测试路线使用路线测试客户端示例应用程序。  
  
## <a name="prerequisites"></a>先决条件  
 此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。  
  
## <a name="steps"></a>步骤  
  
#### <a name="to-create-an-itinerary-model"></a>若要创建路线模型  
  
1.  在[!INCLUDE[vs2010](../includes/vs2010-md.md)]，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器，右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。  
  
3.  在**添加新项**对话框中，在**名称**框中，键入**UDDI3BindingKeySearch**，然后单击**添加**。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>若要配置路线的属性  
  
1.  在 Visual Studio 中，单击的设计图面**UDDI3BindingKeySearch.itinerary**。 在**UDDI3BindingKeySearch**属性窗口中，配置以下属性：  
  
    1.  在**模型导出程序**下拉列表中，单击**XML 路线导出程序**。  
  
    2.  下**扩展程序设置**部分，旁边**路线 XML 文件**属性，单击省略号按钮 （…）。  
  
    3.  在**选择 XML 文件**对话框中，键入**C:\HowTos\Itineraries\UDDI3BindingKeySearch**中**文件名**框中，并依次**保存**.  
  
        > [!NOTE]
        >  此步骤允许您路线作为 XML 导出到本地文件位置。 通过到路线的数据库，而不导出到本地文件的位置，一条路线使测试路线使用 ESB 测试客户端应用程序。 你将完成本操作方法主题中后面此过程。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>若要定义路线的结构  
  
1.  从工具箱中，拖动**上负载增加**到设计图面上的模型元素。 在**OnRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**ReceiveNAOrder**。  
  
    2.  在**扩展程序**下拉列表中，单击**上负载增加 ESB 扩展程序**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
    4.  在**接收端口**下拉列表中，单击**OnRamp.Itinerary**。  
  
2.  从工具箱中，拖动**路线服务**到设计图面上的模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**BindingKeyRoute**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**消息传送扩展程序**。  
  
    3.  在**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。  
  
    4.  在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。  
  
3.  右键单击**冲突解决程序**集合**BindingKeyRoute**模型元素，并依次**添加新解析程序**。 在**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**BindingKeySearch**。  
  
    2.  在**解析程序实现**下拉列表中，单击**Uddi3 冲突解决程序扩展**。  
  
    3.  在**冲突解决程序名字对象**下拉列表中，单击**UDDI3**。  
  
    4.  单击**绑定密钥**属性，再然后键入**uddi:esb:orderfileservicev3.1**。  
  
4.  右键单击**BindingKeySearch**冲突解决程序，，然后单击**测试解析程序配置**。  
  
    > [!NOTE]
    >  验证显示在输出窗口中的输出。  
  
5.  在工具箱中，单击**连接器**。 将从连接**ReceiveNAOrder**到模型元素**BindingKeyRoute**模型元素。  
  
6.  从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**BindingKeyRoute**模型元素。 在**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SendNAOrder**。  
  
    2.  在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 扩展程序**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。  
  
7.  从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**BindingKeyRoute**模型元素和**SendNAOrder**模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SendPortFilter**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**关闭负载增加扩展程序**。  
  
    3.  在**关闭负载增加**下拉列表中，展开**SendNAOrder**，然后单击**发送处理程序**。  
  
8.  在工具箱中，单击**连接器**。 将从连接**BindingKeyRoute**到模型元素**SendPortFilter**模型元素。  
  
9. 在工具箱中，单击**连接器**。 将从连接**SendPortFilter**到模型元素**SendNAOrder**模型元素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>若要导出与路线测试客户端一起使用的模型  
  
1.  在 Visual Studio 中，右键单击的设计图面**UDDI3BindingKeySearch**路线，，然后单击**导出模型**。  
  
    > [!NOTE]
    >  在 Visual Studio 中打开的 XML 版本的路线。  
  
2.  保存所有项目。  
  
3.  在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries，并注意你路线 XML (UDDI3BindingKeySearch.xml) 创建。  
  
#### <a name="to-test-the-itinerary"></a>若要测试路线  
  
1.  打开路线测试客户端示例应用程序使用期间创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。  
  
2.  在路线测试客户端中，清除**使用 WCF 服务**复选框，并依次**负载路线**。  
  
3.  在打开路线文件对话框中，浏览到 C:\HowTos\Itineraries。 选择 UDDI3BindingKeySearch.xml，，然后单击打开加载路线。  
  
4.  单击**确定**清除**成功加载路线**消息。  
  
5.  在路线测试客户端上，单击旁边的省略号按钮 （...）**负载消息**框。  
  
6.  在**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。 选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。  
  
7.  单击**提交请求**按钮。 在测试完成后，单击**确定**关闭出现的确认。  
  
8.  在 Windows 资源管理器，浏览到 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out。验证 %MessageID%.xml 消息已写入到目录。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [如何： 解决使用 UDDI 类别搜索的服务终结点](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  
  
-   [开发活动](../esb-toolkit/development-activities.md)  
  
-   [使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)