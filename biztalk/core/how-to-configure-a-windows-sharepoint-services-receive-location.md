---
title: 如何配置 Windows SharePoint Services 接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, Windows SharePoint Services adapters
- configuring [Windows SharePoint Services adapters], receive locations
- Windows SharePoint Services adapters, receive locations
ms.assetid: 5db3d5cf-4a77-4985-bd03-307c520247ec
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25a075502cf67c406f5b611792c8f09f32ea0823
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386554"
---
# <a name="how-to-configure-a-windows-sharepoint-services-receive-location"></a>如何配置 Windows SharePoint Services 接收位置
本主题介绍如何创建和配置 Windows SharePoint Services 接收位置使用 BizTalk Server 管理控制台。  

### <a name="to-create-and-configure-a-windows-sharepoint-services-receive-location"></a>若要创建和配置 Windows SharePoint Services 接收位置  

1. 请确保已正确配置的接收端口。 有关如何创建和配置接收端口的信息，请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。  

2. 在中**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组 [GroupName]**，展开**应用程序**，然后展开要在其中创建接收位置的应用程序。  

3. 右键单击**接收位置**，单击**新建**，然后单击**单向接收位置**。  

4. 选择接收端口，包含此接收位置，然后单击**确定**。  

5. 在中**接收位置属性**对话框中的**传输**，在**类型**下拉列表框中，选择**Windows SharePoint Services**.  

6. 单击**配置**。  

7. 在中**Windows SharePoint Services 传输属性**对话框框中，执行以下操作：  


   |           使用此选项           |                                                                                                                                                                                                                                                                                                                                    执行的操作                                                                                                                                                                                                                                                                                                                                    |
   |------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   适配器 Web 服务端口   |                                                                                                                                                                      安装 Windows SharePoint Services 适配器 Web services 的 IIS 网站的 HTTP 端口。 默认情况下，这是端口 80 上配置默认 Web 站点。 如果已在默认网站以外任何 IIS Web 站点上配置 Windows SharePoint Services Web 服务，您将必须更新此值。                                                                                                                                                                       |
   |           超时            |                                                                                                                                                                                                        以毫秒为单位，用于对 Windows SharePoint Services 适配器 Web services 的适配器运行时 Web 服务调用的超时。 您可能需要增加此值，如果消息或批大小超过适配器预期的平均值。                                                                                                                                                                                                        |
   |       存档文件名       |                （可选）存档的文件的 Windows SharePoint Services 文件名。 您可以键入如 purchaseorder0001.xml 之类或表达式的文本值。 表达式可以包括文本、 宏和 XPATH 查询的任意组合。 例如，"PurchOrd-%XPATH=//po:PurchaseOrderId%-%MessageID%.xml"。 如果不提供任何文件名称使用源代码文件的文件名。 有关表达式的详细信息，请参阅[Windows SharePoint Services 适配器表达式](../core/windows-sharepoint-services-adapter-expressions.md)。 **注意：** 此字段不支持"%sendingorchestrationid%"和"%sendingorchestrationtype%"宏。                |
   |     存档位置 URL     |                                                                                                  Windows SharePoint Services 文件夹 URL，相对于 SharePoint 站点，其中存档已处理的文件。 例如，存档或 /shared Documents/Processed Orders /。 如果未指定存档位置，该适配器进行处理之后被删除该文档。 **注意：** 有时 SharePoint 文档库中或文件夹的 URL 是不同于该项目的名称。 请查看 Internet Explorer 以发现正确的 URL 中的地址栏。                                                                                                   |
   |      存档覆盖       |                              确定是否覆盖存档中的现有文件。 选择"是"覆盖现有文件。 选择"否"以进行存档来存档中已存在具有相同名称的文件失败。 在这种情况下，该文件将保持签出，它将需要进行手动存档。 **注意：** 时存档文件，我们建议你使用的存档文件名值使用宏以使文件名唯一。 为此，您可以使用如 PO-%MessageID%.xml 或 PO-%XPATH=//ns0:PurchaseOrder/ns0:ID%.xml，其中 ID 是采购订单的唯一 ID 存档文件名。                              |
   |          批大小          |                                                                                                                                                                                                              最大 Windows SharePoint Services 消息传送适配器 Web 服务将处理作为批处理的文档数。 已处理的批次可能包含较少的消息定义的批大小;但是，它将永远不会包含更多的消息。                                                                                                                                                                                                               |
   |       错误阈值        |                                                                                                                                                                                                                                            禁用接收位置时适配器遇到的连续轮询失败的最大数目。 若要永不禁用接收位置，此字段设置为 0。                                                                                                                                                                                                                                             |
   |      命名空间别名      |                                                                                                                                                              （可选）以逗号或分号分隔的命名空间别名定义列表。 使用此字段可以定义由存档文件名字段中引入的 XPATH 查询的命名空间别名。 例如，po ='<http://OrderProcess/POrder>'，conf ='<http://OrderProcess/Confirmation>ipsol = {D8217CF1-4EF7-4bb5-A30D-765ECB09E0D9}                                                                                                                                                               |
   |       轮询间隔       |                                                                                                                                                                                                                 时间间隔，以秒为单位，以查看是否可用于处理任何新消息的适配器由执行两次连续查询之间。 **注意：** 指定较低的值可以提高适配器的吞吐量和响应时间。                                                                                                                                                                                                                  |
   |     SharePoint 站点 URL      |                                                                                                                                                                                                                                       Windows SharePoint Services 网站的完整的 URL。 例如， http://BizTalkServer/sites/TestSite。 **注意：** URI 发送端口或接收位置不能超过 256 个字符。                                                                                                                                                                                                                                       |
   | 源文档库 URL  | 这是 Windows SharePoint Services 文档库中，相对于 SharePoint 站点，在其中检索文档的 URL。 例如，/Shared Documents / 或 /new Purchase Orders /。 **注意：** 从 SharePoint 列表，不能接收消息。 无法从 SharePoint 文件夹接收消息，除非使用的所有文件夹中显示的消息的视图。 若要这样做您设置**文件夹**属性的值**没有文件夹的情况下显示的所有文档**创建视图时。 **注意：** 有时，SharePoint 文档库是不同于该项目的名称。 请查看 Internet Explorer 以发现正确的 URL 中的地址栏。 |
   |          视图名称           |                                                                            这是 Windows SharePoint Services 视图用于筛选适配器处理的文档。 例如，已批准的订单。 将此字段留空，来处理源文档库中的所有现有文档。 该适配器将不处理文件夹显示在一个视图，并在这些文件夹中包含的消息。 可以创建平面视图将包括子文件夹中现有的文档的平面结构中显示的所有文档。 **注意：** 将处理平面视图中的所有消息。                                                                            |
   | Microsoft Office 集成 |                                                                                                                                                        "可选"来尝试删除 InfoPath 处理指令，如果可能还可以按原样处理如果不可能的 （例如，二进制文档）。 选择"是"以删除 InfoPath 处理指令或跳过发生错误时该消息。 选择"否"来处理文档"按原样。" 对于二进制消息，必须使用"否"或"可选"值。                                                                                                                                                         |


8. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
 [如何配置 Windows SharePoint Services 发送处理程序](../core/how-to-configure-a-windows-sharepoint-services-send-handler.md)   
 [如何配置 Windows SharePoint Services 发送端口](../core/how-to-configure-a-windows-sharepoint-services-send-port.md)   
 [如何创建发送端口](../core/how-to-create-a-send-port2.md)   
 [Windows SharePoint Services 适配器属性参考](../core/windows-sharepoint-services-adapter-properties-reference.md)   
 [Windows SharePoint Services 适配器表达式](../core/windows-sharepoint-services-adapter-expressions.md)   
 [支持的 Windows SharePoint Services 栏类型](../core/supported-windows-sharepoint-services-column-types.md)