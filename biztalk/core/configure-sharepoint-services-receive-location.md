---
title: 配置 SharePoint Services 接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9afed0e4-0f72-4df4-a2cb-d999c6fbbc86
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e57bf0971a42c78ac40a9f7fafcd359c13098ef9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007846"
---
# <a name="configure-sharepoint-services-receive-location"></a>配置 SharePoint Services 接收位置
本主题列出了创建 [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] 接收位置的步骤。  

## <a name="create-a-receive-location"></a>创建接收位置  
 创建接收位置时，接收位置使用与传输类型关联的默认接收处理程序。 使用时[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]适配器，则默认的接收处理程序是**BizTalkServerApplication**。 对于要添加新的接收处理程序的步骤，请转到[如何创建适配器处理程序](http://go.microsoft.com/fwlink/p/?LinkId=263646)。  

 创建接收位置：  

1. 在中**BizTalk Server 管理**控制台中，展开**BizTalk 组 [*GroupName*]**，展开**应用程序**，然后展开要包含接收位置的应用程序。  

2. 创建**单向接收端口**。 [如何创建接收端口](../core/how-to-create-a-receive-port.md)列出的步骤。  

   > [!IMPORTANT]
   >  一个**请求响应接收位置**不是可配置为[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]适配器。  

    其他接收端口配置选项包括：  

    [如何将接收位置添加到接收端口](../core/how-to-add-a-receive-location-to-a-receive-port.md)： 下一步中添加接收位置。  

    [如何配置入站的映射接收端口](../core/how-to-configure-inbound-maps-for-a-receive-port.md)  

    [如何配置跟踪的接收端口](../core/how-to-configure-tracking-for-a-receive-port.md)  

3. 单击**确定**以保存设置。  

4. 右键单击**接收位置**，单击**新建**，然后单击**单向接收位置**。  

   > [!IMPORTANT]
   >  一个**请求响应接收位置**不是可配置为[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]适配器。  

5. 选择接收端口，然后单击**确定**。  

6. 在中**属性**，输入**名称**并**管道**属性。 在中**类型**下拉列表中，单击**Windows SharePoint Services** ，然后选择**接收处理程序**属性。  

7. 单击**配置**。 在中**属性**，配置以下各项：  


   |                              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
   |------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   适配器 Web Services 端口   |                                                                                                                                                                                                                                                                                                                                   **所需**。 在 IIS 网站上配置的托管 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 适配器 Web Services 的端口。<br /><br /> 默认端口为端口**80**，这是标准 HTTP 端口。 如果使用除 80 以外的端口，请更新此值。                                                                                                                                                                                                                                                                                                                                    |
   |           超时            |                                                                                                                                                                                                                                                                                                                                                    **所需**。 单位为毫秒，此值用于确定适配器从 Web 服务收到响应的时间。<br /><br /> 默认值是**100000 毫秒**（100 秒）。<br /><br /> 如果消息或批大小大于预期值，请增大此值。                                                                                                                                                                                                                                                                                                                                                     |
   |        使用客户端 OM         | **所需**。 确定是使用 SharePoint 客户端对象模型 (CSOM) 还是服务端对象模型 (SSOM)。<br /><br /> 默认值是**是**。 设置为**是**上使用 SharePoint CSOM [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 对 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 计算机没有任何要求。<br /><br /> 设置为**否**若要使用 SharePoint SSOM，包括 web 服务上安装[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]计算机。<br /><br /> [附录 b： 安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)上使用的 SSOM 和 CSOM 组件提供的特定信息[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]适配器。 |
   |       存档文件名       |                                                                                                 **可选**。 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Web 服务可对来自 SharePoint 库的文档存档。 输入存档文件的名称。<br /><br /> 输入文件名称，如**PurchaseOrder0001.xml**或表达式。 表达式包括文本、宏和 XPATH 查询的任意组合。 例如，“PurchOrd-%XPATH=//po:PurchaseOrderId%-%MessageID%.xml”。 如果没有提供文件名，则会使用源文件的文件名。 请参阅[Windows SharePoint Services 适配器表达式](../core/windows-sharepoint-services-adapter-expressions.md)有关详细信息。 **注意：** 按此字段不支持"%sendingorchestrationid%"和"%sendingorchestrationtype%"宏。                                                                                                  |
   |     存档位置 URL     |                                                                                                                                                                                                                       **可选**。 用于存储存档文档的 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 文件夹 URL。 输入 SharePoint 站点的相对路径。 例如，**存档**或 **/shared Documents/Processed Orders /**。 如果未指定存档位置，则适配器处理文档之后将删除文档。 **注意：** SharePoint 文档库或文件夹 URL 可以与其名称不同。 查看 Web 浏览器中的地址以获取正确的 URL。                                                                                                                                                                                                                        |
   |      存档覆盖       |                                                                                                                                                                                                                                  **所需**。 指定是否覆盖现有文件。<br /><br /> 默认值是**否**，如果存档中存在具有相同名称的文件则无法存档。 在此情况下，文件将被签出，必须手动存档。 **注意：** 文件名称时存档文件，使用宏使用存档文件名值是唯一的。 例如，如使用存档文件名**PO-%MessageID%.xml 或 PO-%XPATH=//ns0:PurchaseOrder/ns0:*ID*%.xml**，其中 ID 是唯一的采购订单 id。                                                                                                                                                                                                                                  |
   |          批大小          |                                                                                                                                                                                                                                                                                                                                                **所需**。 由 Web 服务作为一批处理的最大文档数。 所处理的批包含的消息数可能会少于定义的批大小， 但不会多于该值。<br /><br /> 默认值是**20**并且必须至少具有值为**1**。                                                                                                                                                                                                                                                                                                                                                |
   |       错误阈值        |                                                                                                                                                                                                                                                                                                                                                                       **所需**。 适配器允许的最大连续轮询失败次数，到达最大次数后将禁用该接收位置。<br /><br /> 默认值是**10**。 若要停止接收位置被禁用，请将此设置为**0**。                                                                                                                                                                                                                                                                                                                                                                        |
   |      命名空间别名      |                                                                                                                                                                                                                                                                                           **可选**。 以逗号或分号分隔的命名空间别名定义列表。<br /><br /> 使用此字段可以定义在上面所列的“存档文件名”字段中引入的 XPATH 查询所使用的命名空间别名。 例如，输入**po ='<http://OrderProcess/POrder>'，conf ='<http://OrderProcess/Confirmation>ipsol = {D8217CF1-4EF7-4bb5-A30D-765ECB09E0D9}**。                                                                                                                                                                                                                                                                                            |
   |       轮询间隔       |                                                                                                                                                                                                                                                                                                                                               **所需**。 适配器在等待新消息时执行的两次连续查询之间的时间（以秒计）。<br /><br /> 默认值是**60**并且必须至少具有值为**1**。 **注意：** 若要提高适配器吞吐量和响应时间，请输入较低的值。                                                                                                                                                                                                                                                                                                                                               |
   |     SharePoint 站点 URL      |                                                                                                                                                                                                                                                                                                                                                **可选**。 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 网站的完整 URL。 例如，http:// *SharePointServer*/sites/testsite。 **注意：** 一个发送端口或接收位置的 URI 不能超过 256 个字符。                                                                                                                                                                                                                                                                                                                                                 |
   | 源文档库 URL  |                                                                                                                                                                                                                                                                                        **可选**。 从中检索文档的 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 文档库的 URL 相对路径。 例如， **/Shared Documents /** 或 **/new Purchase Orders /**。 **注意：** SharePoint 文档库可以与其名称不同。 查看 Web 浏览器中的地址以获取正确的 URL。                                                                                                                                                                                                                                                                                        |
   |          视图名称           |                                                                                                                                                                                                                              **可选**。 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]用来筛选文档视图适配器所处理的。 例如，**已批准的订单**。<br /><br /> 要处理源文档库中的所有现有文档，请将此字段保留为空。 适配器将不处理视图中的文件夹以及这些文件夹中的消息。 创建平面视图以按平面结构显示所有文档，包括位于子文件夹中的文档。                                                                                                                                                                                                                              |
   | Microsoft Office 集成 |                                                                                                                                                                                                   **所需**。 对于二进制消息，必须使用“否”或“可选”值。<br /><br /> 默认值是**可选**。<br /><br /> 选项包括：<br /><br /> -   **不**： 处理的文档"按原样"。 二进制消息可以使用此选项。<br />-   **可选**： 尝试删除 InfoPath 处理指令。 如果未删除处理指令，则按原样处理文档。 二进制消息可以使用此选项。<br />-   **是**： 删除 InfoPath 处理指令。 如果出现错误，则跳过该消息。                                                                                                                                                                                                    |
   |  SharePoint Online 密码  |                                                                                                                                                                                                                                                                                                                                                                                                                                                      **可选**。 SharePoint Online 帐户的密码。                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
   |  SharePoint Online 用户名  |                                                                                                                                                                                                                                                                                                                                                                                                                                                      **可选**。 SharePoint Online 帐户的用户名。                                                                                                                                                                                                                                                                                                                                                                                                                                                       |


8. 单击**确定**保存设置。  

9. 其他接收位置配置选项包括：  

     [如何配置计划的接收位置](../core/how-to-configure-scheduling-for-a-receive-location.md)  

10. 单击**确定**保存设置。  

    其他接收端口和接收位置主题：  

    [管理接收端口](../core/managing-receive-ports.md)  

    [管理接收位置](../core/managing-receive-locations.md)  

    接下来，创建一个 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 发送端口：  

    [配置 SharePoint Services 发送端口](../core/configure-sharepoint-services-send-port.md)  

## <a name="see-also"></a>请参阅  
 [配置 SharePoint Services 发送端口](../core/configure-sharepoint-services-send-port.md)   
 [SharePoint Services 适配器故障排除](../core/troubleshooting-sharepoint-services-adapter.md)   
 [CSOM：SharePoint Services 适配器](../core/csom-sharepoint-services-adapter.md)