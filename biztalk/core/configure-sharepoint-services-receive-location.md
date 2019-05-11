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
ms.openlocfilehash: 0c8ddd05b16ac6d42ace09d5bb9a56a758858ccf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356429"
---
# <a name="configure-sharepoint-services-receive-location"></a>配置 SharePoint Services 接收位置
本主题列出了创建步骤[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]接收位置。  

## <a name="create-a-receive-location"></a>创建接收位置  
 在创建接收位置时，接收位置将使用默认值与传输类型关联的接收处理程序。 使用时[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]适配器，则默认的接收处理程序是**BizTalkServerApplication**。 对于要添加新的接收处理程序的步骤，请转到[如何创建适配器处理程序](http://go.microsoft.com/fwlink/p/?LinkId=263646)。  

 创建接收位置：  

1. 在中**BizTalk Server 管理**控制台中，展开**BizTalk 组 [*GroupName*]**，展开**应用程序**，然后展开要包含接收位置的应用程序。  

2. 创建**单向接收端口**。 [如何创建接收端口](../core/how-to-create-a-receive-port.md)列出的步骤。  

   > [!IMPORTANT]
   >  一个**请求响应接收位置**不是可配置为[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]适配器。  

    其他接收端口配置选项包括：  

    [如何添加接收位置接收端口](../core/how-to-add-a-receive-location-to-a-receive-port.md):下一步中添加接收位置。  

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
   |   适配器 Web 服务端口   |                                                                                                                                                                                                                                                                                                                                   **所需**。 承载的 IIS web 站点上配置的端口[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]适配器 web 服务。<br /><br /> 默认端口为端口**80**，这是标准 HTTP 端口。 如果使用非 80 的端口，请更新此值。                                                                                                                                                                                                                                                                                                                                    |
   |           超时            |                                                                                                                                                                                                                                                                                                                                                    **所需**。 以毫秒为单位，此值确定适配器从 web 服务收到响应的时间。<br /><br /> 默认值是**100000 毫秒**（100 秒）。<br /><br /> 如果消息或批大小高于预期，请增大此值。                                                                                                                                                                                                                                                                                                                                                     |
   |        使用客户端 OM         | **所需**。 确定是否使用 SharePoint 客户端对象模型 (CSOM) 或服务端对象模型 (SSOM)。<br /><br /> 默认值是**是**。 设置为**是**上使用 SharePoint CSOM [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 在没有任何要求[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]计算机。<br /><br /> 设置为**否**若要使用 SharePoint SSOM，包括 web 服务上安装[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]计算机。<br /><br /> [附录 b:安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)上使用的 SSOM 和 CSOM 组件提供的特定信息[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]适配器。 |
   |       存档文件名       |                                                                                                 **可选**。 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Web 服务可以从 SharePoint 库的文档存档。 输入存档文件的名称。<br /><br /> 输入文件名称，如**PurchaseOrder0001.xml**或表达式。 表达式包括文本、 宏和 XPATH 查询的任意组合。 例如，"PurchOrd-%XPATH=//po:PurchaseOrderId%-%MessageID%.xml"。 如果不提供任何文件名称，则使用源文件的文件名。 请参阅[Windows SharePoint Services 适配器表达式](../core/windows-sharepoint-services-adapter-expressions.md)有关详细信息。 **注意：** 此字段不支持"%sendingorchestrationid%"和"%sendingorchestrationtype%"宏。                                                                                                  |
   |     存档位置 URL     |                                                                                                                                                                                                                       **可选**。 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]文件夹 URL，以存储存档的文档。 输入 SharePoint 站点的相对路径。 例如，**存档**或 **/shared Documents/Processed Orders /**。 如果未指定存档位置，由适配器处理后删除文档。 **注意：** SharePoint 文档库或文件夹 URL 可以与其名称不同。 获取正确的 URL 检查 web 浏览器中的地址。                                                                                                                                                                                                                        |
   |      存档覆盖       |                                                                                                                                                                                                                                  **所需**。 指定覆盖现有文件。<br /><br /> 默认值是**否**，如果存档中存在具有相同名称的文件则无法存档。 在此方案中，该文件已签出，必须手动存档。 **注意：** 当存档文件，使用存档文件名值使用宏的文件的名称是唯一的。 例如，如使用存档文件名**PO-%MessageID%.xml 或 PO-%XPATH=//ns0:PurchaseOrder/ns0:*ID*%.xml**，其中 ID 是唯一的采购订单 id。                                                                                                                                                                                                                                  |
   |          批大小          |                                                                                                                                                                                                                                                                                                                                                **所需**。 最大处理 web 服务作为一批处理的文档数。 已处理的批次可能包含较少的消息定义的批大小。 它不包含更多的消息。<br /><br /> 默认值是**20**并且必须至少具有值为**1**。                                                                                                                                                                                                                                                                                                                                                |
   |       错误阈值        |                                                                                                                                                                                                                                                                                                                                                                       **所需**。 禁用接收位置时适配器的连续轮询失败的最大数目。<br /><br /> 默认值是**10**。 若要停止接收位置被禁用，请将此设置为**0**。                                                                                                                                                                                                                                                                                                                                                                        |
   |      命名空间别名      |                                                                                                                                                                                                                                                                                           **可选**。 以逗号或分号分隔的命名空间别名定义列表。<br /><br /> 使用此字段可以定义在上面列出的存档文件名字段中引入的 XPATH 查询所使用的命名空间别名。 例如，输入**po ='<http://OrderProcess/POrder>'，conf ='<http://OrderProcess/Confirmation>ipsol = {D8217CF1-4EF7-4bb5-A30D-765ECB09E0D9}**。                                                                                                                                                                                                                                                                                            |
   |       轮询间隔       |                                                                                                                                                                                                                                                                                                                                               **所需**。 以秒为单位，执行的适配器在等待新消息的两个连续查询之间的时间。<br /><br /> 默认值是**60**并且必须至少具有值为**1**。 **注意：** 若要提高适配器吞吐量和响应时间，请输入较低的值。                                                                                                                                                                                                                                                                                                                                               |
   |     SharePoint 站点 URL      |                                                                                                                                                                                                                                                                                                                                                **可选**。 完整 URL [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] web 站点。 例如， http:// *SharePointServer*/sites/testsite。 **注意：** 一个发送端口或接收位置的 URI 不能超过 256 个字符。                                                                                                                                                                                                                                                                                                                                                 |
   | 源文档库 URL  |                                                                                                                                                                                                                                                                                        **可选**。 URL 相对路径[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]其中检索文档的文档库。 例如， **/Shared Documents /** 或 **/new Purchase Orders /**。 **注意：** SharePoint 文档库可以与其名称不同。 获取正确的 URL 检查 web 浏览器中的地址。                                                                                                                                                                                                                                                                                        |
   |          视图名称           |                                                                                                                                                                                                                              **可选**。 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]用来筛选文档视图适配器所处理的。 例如，**已批准的订单**。<br /><br /> 若要处理源文档库中的所有现有文档，请将此字段留空。 视图中的文件夹和这些文件夹中的消息不是由适配器处理。 创建在平面结构，包括位于子文件夹中的文档中显示的所有文档的平面视图。                                                                                                                                                                                                                              |
   | Microsoft Office 集成 |                                                                                                                                                                                                   **所需**。 对于二进制消息，必须使用"否"或"可选"值。<br /><br /> 默认值是**可选**。<br /><br /> 选项包括：<br /><br /> -   **不**:处理文档"按原样"。 对于二进制消息，可以使用此选项。<br />-   **可选**:尝试删除 InfoPath 处理指令。 如果未删除处理指令，"按原样"处理文档。 对于二进制消息，可以使用此选项。<br />-   **是**:删除 InfoPath 处理指令。 如果发生错误，则跳过该消息。                                                                                                                                                                                                    |
   |  SharePoint Online 密码  |                                                                                                                                                                                                                                                                                                                                                                                                                                                      **可选**。 SharePoint online 帐户的密码。                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
   |  SharePoint Online 用户名  |                                                                                                                                                                                                                                                                                                                                                                                                                                                      **可选**。 SharePoint online 帐户的用户名。                                                                                                                                                                                                                                                                                                                                                                                                                                                       |


8. 单击**确定**保存设置。  

9. 接收位置的其他配置选项包括：  

     [如何配置计划的接收位置](../core/how-to-configure-scheduling-for-a-receive-location.md)  

10. 单击**确定**保存设置。  

    其他接收端口和接收位置主题：  

    [管理接收端口](../core/managing-receive-ports.md)  

    [管理接收位置](../core/managing-receive-locations.md)  

    接下来，创建[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]发送端口：  

    [配置 SharePoint Services 发送端口](../core/configure-sharepoint-services-send-port.md)  

## <a name="see-also"></a>请参阅  
 [配置 SharePoint Services 发送端口](../core/configure-sharepoint-services-send-port.md)   
 [SharePoint Services 适配器故障排除](../core/troubleshooting-sharepoint-services-adapter.md)   
 [CSOM:SharePoint Services Adapter](../core/csom-sharepoint-services-adapter.md)