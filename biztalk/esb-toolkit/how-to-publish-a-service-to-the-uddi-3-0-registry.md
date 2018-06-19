---
title: 如何： 将服务发布到 UDDI 3.0 注册表 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2c3bd0ed-e5f1-43eb-98d1-e3247a565ba2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da3d2dc400c031ab5febda1568cb18ce5180366b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009910"
---
# <a name="how-to-publish-a-service-to-the-uddi-30-registry"></a>如何： 将服务发布到 UDDI 3.0 注册表
## <a name="goal"></a>目的  
 本部分演示如何使用 UDDI 服务网站发布内就能解决从为了 ESB 消息路由路线的 Web 服务终结点。 将复制现有 PurchaseOrderSubmitOrderService 服务目前发布到注册表。  
  
 在本操作方法主题中，你将完成以下步骤：  
  
-   将服务发布到通用、 描述、 发现和集成 (UDDI) 3 使用 UDDI 发行者工具的注册表。  
  
-   测试使用解析使用 UDDI3 解析程序的服务终结点路线路由滑动服务发布。  
  
## <a name="prerequisites"></a>先决条件  
 此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)和 （你可以安装它在 %esb 安装 Folder%\Bin\ UDDI 发行者工具的执行Microsoft.Practices.ESB.UDDIPublisher.exe)。  
  
## <a name="steps"></a>步骤  
  
#### <a name="to-create-the-newposervice-in-the-uddi-registry"></a>在发布的 UDDI 注册表中创建 NewPOService  
  
1.  在 Internet Explorer 中，浏览到 UDDI 服务网站 （默认情况下，此 URL 为 http://localhost/uddi）。  
  
2.  上**uddi 服务**页上，单击**发布**。  
  
3.  在发布窗格中，右键单击**Microsoft.Practices.ESB**，然后单击**添加服务**。  
  
4.  在以下页面上，选择**指定要使用的密钥**，然后单击**继续**。  
  
5.  在以下页上，单击**esb**密钥分区。 在**密钥后缀**框中，键入**newposervice**，然后单击**继续**。  
  
6.  在以下页面中下, 一步 (**新的服务名称**)，单击**编辑**。 将服务**NewPOService**，然后单击**更新**。  
  
7.  单击**添加说明**，键入服务的说明 (例如，**示例服务**)，然后单击**更新**。  
  
#### <a name="to-add-a-binding-for-the-newposervice"></a>若要将绑定添加为 NewPOService  
  
1.  单击**绑定**选项卡上，并依次**添加绑定**。  
  
2.  选择**指定要使用的密钥**，然后单击**继续**。  
  
3.  在以下页上，单击**esb**密钥分区。 在**密钥后缀**框中，键入**newposervicebinding**，然后单击**继续**。  
  
4.  下**接入点**，单击**编辑**，然后完成以下：  
  
    1.  在**接入点**框中，键入**http://localhost/ESB.CanadianServices/SubmitPOService.asmx**。  
  
    2.  在**使用类型**下拉列表中，单击**终结点**，然后单击**更新**。  
  
#### <a name="to-configure-the-binding-instance-information"></a>若要配置的绑定实例信息  
  
1.  单击**实例信息**选项卡上，并依次**添加实例信息**。  
  
2.  在**搜索 tModel 名称中包含**框中，键入 **%esb%** ，然后单击**搜索**。  
  
3.  找到并单击**tModel**为**transporttype**。  
  
    > [!NOTE]
    >  若要完成此过程中的剩余步骤，你可能需要第 1 页和第 2 页之间发生更改。  
  
4.  在**说明**部分中，单击**添加说明**。  
  
5.  在**说明**框中，键入**ESB 路线使用的传输类型**，然后单击**更新**。  
  
6.  单击**实例详细信息**选项卡上，并依次**编辑**。  
  
7.  在**实例参数**框中，键入**WCF BasicHttp**，然后单击**更新**。  
  
8.  在**说明**部分中，单击**添加说明**。  
  
9. 在**说明**框中，键入**WCF 基本 HTTP 传输**，然后单击**更新**。  
  
10. 在发布窗格中，在**NewPOService**，单击**http://localhost/esb.canadianservices/submitposervice.asmx**。  
  
11. 上**实例信息**选项卡上，单击**添加实例信息**。  
  
12. 使用前面所述的步骤，添加以下实例的信息，根据下表中显示的值。  
  
    |tModel|Description|参数|参数说明|  
    |------------|-----------------|---------------|---------------------------|  
    |microsoft-com:esb:runtimeresolution:messageexchangepattern|消息交换模式|双向|双向操作|  
    |microsoft-com:esb:runtimeresolution:cachetimeout|缓存超时值|-1|当前已禁用|  
    |microsoft-com:esb:runtimeresolution:jaxrpcresponse|JaxRpcResponse|false||  
    |microsoft-com:esb:runtimeresolution:action|服务操作|将订单|指定要调用的服务方法|  
    |microsoft-com:esb:runtimeresolution:targetnamespace|服务 Namespace|http://globalbank.esb.dynamicresolution.com/canadianservices|目标命名空间|  
  
#### <a name="to-configure-the-binding-categorization"></a>若要配置的绑定分类  
  
1.  在发布窗格中，在**NewPOService**，单击**http://localhost/esb.canadianservices/submitposervice.asmx**。  
  
2.  上**类别**选项卡上，单击**添加自定义类别**。  
  
3.  在**搜索**框中，键入 **%esb%** ，然后单击**搜索**。  
  
4.  找到并单击**microsoft-com:esb:runtimeresolution:biztalkapplication** tModel。  
  
5.  在**密钥名称**框中，键入**BizTalk 应用程序**。  
  
6.  在**键值**框中，键入**Microsoft.Practices.ESB**，然后单击**添加类别**。  
  
7.  使用前面所述的步骤，添加以下自定义类别中，根据下表中显示的值。  
  
    |tModel|项名|密钥值|  
    |------------|--------------|---------------|  
    |microsoft-com:esb:runtimeresolution:portname|端口名称|NewPOService|  
    |microsoft-com:esb:runtimeresolution:transporttype|传输类型|WCF-BasicHttp|  
  
#### <a name="to-locate-the-service-in-the-uddi-registry"></a>若要查找 UDDI 注册表中的服务  
  
1.  在 Internet Explorer 中，在**uddi 服务**页上，单击**搜索**。  
  
2.  单击**服务**选项卡。  
  
3.  在**服务名称**框中，键入 **%PO%**，然后单击**搜索**。  
  
4.  在**搜索**窗格中，在**结果**选项卡上，单击**NewPOService**。  
  
    > [!NOTE]
    >  这样会确认服务已成功发布到注册表。  
  
#### <a name="to-create-an-itinerary-model-to-test-the-uddi-service-publication"></a>若要创建路线模型来测试 UDDI 服务发布  
  
1.  在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器，右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。  
  
3.  在**添加新项**对话框中，在**名称**框中，键入**NewBindingKeySearch**，然后单击**添加**。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>若要配置路线的属性  
  
1.  在 Visual Studio 中，单击的设计图面**NewBindingKeySearch.itinerary**。 在**NewBindingKeySearch**属性窗口中，配置以下属性：  
  
    1.  在**是请求响应**下拉列表中，单击**True**。  
  
    2.  在**模型导出程序**下拉列表中，单击**XML 路线导出程序**。  
  
    3.  在**扩展程序设置**部分，旁边**路线 XML 文件**属性，单击省略号按钮 （…）。  
  
    4.  在**选择 XML 文件**对话框中，键入**C:\HowTos\Itineraries\NewBindingKeySearch**中**文件名**框中，并依次**保存**.  
  
        > [!NOTE]
        >  此步骤允许您路线作为 XML 导出到本地文件位置。 通过到路线的数据库，而不导出到本地文件的位置，一条路线使测试路线使用 ESB 测试客户端应用程序。 你将完成本操作方法主题中后面此过程。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>若要定义路线的结构  
  
1.  从工具箱中，拖动**上负载增加**到设计图面上的模型元素。 在**OnRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**ReceiveNAOrder**。  
  
    2.  在**扩展程序**下拉列表中，单击**上负载增加 ESB 扩展程序**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
    4.  在**接收端口**下拉列表中，单击**OnRamp.Itinerary.Response**。  
  
2.  从工具箱中，拖动**路线服务**到设计图面上的模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**TransformNAOrder**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**消息传送扩展程序**。  
  
    3.  在**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。  
  
    4.  在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Transform**。  
  
3.  右键单击**冲突解决程序**集合**TransformNAOrder**模型元素，并依次**添加新解析程序**。 在**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**NAOrder_to_CNOrder**。  
  
    2.  在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。  
  
    3.  在**转换类型**下拉列表中，单击**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**。  
  
4.  在工具箱中，单击**连接器**。 将从连接**ReceiveNAOrder**到模型元素**TransformNAOrder**模型元素。  
  
5.  从工具箱中，拖动**路线服务**到设计图面上的模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**BindingKeyRoute**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**消息传送扩展程序**。  
  
    3.  在**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。  
  
    4.  在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。  
  
6.  右键单击**冲突解决程序**集合**BindingKeyRoute**模型元素，并依次**添加新解析程序**。 在**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**BindingKeySearch**。  
  
    2.  在**解析程序实现**下拉列表中，单击**Uddi3 冲突解决程序扩展**。  
  
    3.  在**冲突解决程序名字对象**下拉列表中，单击**UDDI3**。  
  
    4.  单击**绑定密钥**属性，再然后键入**uddi:esb:newposervicebinding**。 若要查找的键值，单击 UDDI 中的 http://localhost/ESB.CanadianServices/SubmitPOService.asmx 服务，然后单击更多详细信息。  
  
7.  右键单击**BindingKeySearch**冲突解决程序，，然后单击**测试解析程序配置**。  
  
    > [!NOTE]
    >  验证显示在输出窗口中的输出。  
  
8.  在工具箱中，单击**连接器**。 将从连接**TransformNAOrder**到模型元素**BindingKeyRoute**模型元素。  
  
9. 从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**BindingKeyRoute**模型元素。 在**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SendCNOrder**。  
  
    2.  在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 扩展程序**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在**发送端口**下拉列表中，单击**DynamicResolutionSolicitResp**。  
  
10. 从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**BindingKeyRoute**模型元素和**SendCNOrder**模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SendPortFilter**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**关闭负载增加扩展程序**。  
  
    3.  在**关闭负载增加**下拉列表中，展开**SendCNOrder**，然后单击**发送处理程序**。  
  
11. 在工具箱中，单击**连接器**。 将从连接**BindingKeyRoute**到模型元素**SendPortFilter**模型元素。  
  
12. 在工具箱中，单击**连接器**。 将从连接**SendPortFilter**到模型元素**SendNAOrder**模型元素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>若要导出与路线测试客户端一起使用的模型  
  
1.  在 Visual Studio 中，右键单击的设计图面**NewBindingKeySearch**路线，，然后单击**导出模型**。  
  
    > [!NOTE]
    >  在 Visual Studio 中打开的 XML 版本的路线。  
  
2.  保存所有项目。  
  
3.  在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries，并注意你路线 XML (NewBindingKeySearch.xml) 创建。  
  
#### <a name="to-test-the-itinerary"></a>若要测试路线  
  
1.  打开路线测试客户端示例应用程序使用期间创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。  
  
2.  在路线测试客户端，在**Web 服务选项**组中，清除**使用 WCF 服务**框中，然后选择**双向服务**复选框。  
  
3.  单击**负载路线**按钮。  
  
4.  在**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。 选择**NewBindingKeySearch.xml**，然后单击**打开**加载路线。  
  
5.  单击**确定**清除**成功加载路线**消息。  
  
6.  在路线测试客户端上，单击旁边的省略号按钮 （...）**负载消息**框。  
  
7.  在**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。 选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。  
  
8.  单击**提交请求**按钮。 在测试完成后，单击**确定**关闭出现的确认。  
  
9. 验证是否正确的响应消息出现在**结果**文本框**Itineray 测试客户端**。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [如何：使用 UDDI 绑定密钥搜索解析服务终结点](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search.md)  
  
-   [如何：使用 UDDI 类别搜索解析服务终结点](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  
  
-   [开发活动](../esb-toolkit/development-activities.md)