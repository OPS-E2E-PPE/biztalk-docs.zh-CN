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
ms.openlocfilehash: 78548238da2a07a0fdadfa787c02ab97bb2e337b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022187"
---
# <a name="how-to-configure-a-windows-sharepoint-services-receive-location"></a>如何配置 Windows SharePoint Services 接收位置
本主题介绍如何通过使用 BizTalk Server 管理控制台来创建和配置 Windows SharePoint Services 接收位置。  

### <a name="to-create-and-configure-a-windows-sharepoint-services-receive-location"></a>创建和配置 Windows SharePoint Services 接收位置  

1. 确保已正确配置了接收端口。 有关如何创建和配置接收端口的信息，请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。  

2. 在中**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组 [GroupName]**，展开**应用程序**，然后展开要在其中创建接收位置的应用程序。  

3. 右键单击**接收位置**，单击**新建**，然后单击**单向接收位置**。  

4. 选择接收端口，包含此接收位置，然后单击**确定**。  

5. 在中**接收位置属性**对话框中的**传输**，在**类型**下拉列表框中，选择**Windows SharePoint Services**.  

6. 单击**配置**。  

7. 在中**Windows SharePoint Services 传输属性**对话框框中，执行以下操作：  


   |           使用此选项           |                                                                                                                                                                                                                                                                                                                                    执行的操作                                                                                                                                                                                                                                                                                                                                    |
   |------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   适配器 Web Services 端口   |                                                                                                                                                                      安装 Windows SharePoint Services 适配器 Web Services 的 IIS 网站的 HTTP 端口。 默认情况下，这是端口 80 上配置默认 Web 站点。 如果已在默认网站以外任何 IIS Web 站点上配置 Windows SharePoint Services Web 服务，您将必须更新此值。                                                                                                                                                                       |
   |           超时            |                                                                                                                                                                                                        对 Windows SharePoint Services 适配器 Web Services 进行的适配器运行时 Web Services 调用的超时值（以毫秒计）。 如果消息或批的大小超过适配器预期的平均大小，则可能需要增加此值。                                                                                                                                                                                                        |
   |       存档文件名       |                （可选）存档的文件的 Windows SharePoint Services 文件名。 您可以键入如“PurchaseOrder0001.xml”之类的文本值，也可以键入表达式。 表达式可以包括文本、宏和 XPATH 查询的任意组合。 例如，“PurchOrd-%XPATH=//po:PurchaseOrderId%-%MessageID%.xml”。 如果没有提供文件名，则会使用源文件的名称。 有关表达式的详细信息，请参阅[Windows SharePoint Services 适配器表达式](../core/windows-sharepoint-services-adapter-expressions.md)。 **注意：** 按此字段不支持"%sendingorchestrationid%"和"%sendingorchestrationtype%"宏。                |
   |     存档位置 URL     |                                                                                                  Windows SharePoint Services 文件夹 URL（相对于用来对所处理的文件进行存档的 SharePoint 站点）。 例如，存档或 /shared Documents/Processed Orders /。 如果未指定存档位置，该适配器进行处理之后被删除该文档。 **注意：** 有时，SharePoint 文档库中或文件夹的 URL 是不同于该项目的名称。 请查看 Internet Explorer 的地址栏以确定正确的 URL。                                                                                                   |
   |      存档覆盖       |                              确定是否覆盖存档中的现有文件。 选择“是”将覆盖现有文件。 如果选择“否”，当存档位置中已经存在具有相同名称的文件时，存档将失败。 在这种情况下，文件将保持签出状态，必须对其进行手动存档。 **注意：** 时存档文件，我们建议你使用的存档文件名值使用宏以使文件名唯一。 为此，可以使用类似于 PO-%MessageID%.xml 或 PO-%XPATH=//ns0:PurchaseOrder/ns0:ID%.xml（其中 ID 是采购订单的唯一 ID）这样的存档文件名。                              |
   |          批大小          |                                                                                                                                                                                                              最大 Windows SharePoint Services 消息传送适配器 Web 服务将处理作为批处理的文档数。 已处理的批次可能包含较少的消息定义的批大小;但是，它将永远不会包含更多的消息。                                                                                                                                                                                                               |
   |       错误阈值        |                                                                                                                                                                                                                                            适配器允许遇到的最大连续轮询失败次数，到达最大次数后将禁用该接收位置。 若要永不禁用该接收位置，请将此字段设置为 0。                                                                                                                                                                                                                                             |
   |      命名空间别名      |                                                                                                                                                              （可选）以逗号或分号分隔的命名空间别名定义列表。 使用此字段可以定义由存档文件名字段中引入的 XPATH 查询的命名空间别名。 例如，po ='<http://OrderProcess/POrder>'，conf ='<http://OrderProcess/Confirmation>ipsol = {D8217CF1-4EF7-4bb5-A30D-765ECB09E0D9}                                                                                                                                                               |
   |       轮询间隔       |                                                                                                                                                                                                                 时间间隔，以秒为单位，以查看是否可用于处理任何新消息的适配器由执行两次连续查询之间。 **注意：** 指定较低的值可以提高适配器的吞吐量和响应时间。                                                                                                                                                                                                                  |
   |     SharePoint 站点 URL      |                                                                                                                                                                                                                                       Windows SharePoint Services 网站的完整 URL。 例如， http://BizTalkServer/sites/TestSite。 **注意：** 的 URI 发送端口或接收位置不能超过 256 个字符。                                                                                                                                                                                                                                       |
   | 源文档库 URL  | 这是 Windows SharePoint Services 文档库的 URL（相对于在其中检索文档的 SharePoint 站点）。 例如，/Shared Documents/ 或 /New Purchase Orders/。 **注意：** 无法接收来自 SharePoint 列表的消息。 除非使用显示所有文件夹中的消息的视图，否则您无法从 SharePoint 文件夹接收消息。 若要这样做您设置**文件夹**属性的值**没有文件夹的情况下显示的所有文档**创建视图时。 **注意：** 有时，SharePoint 文档库是不同于该项目的名称。 请查看 Internet Explorer 的地址栏以确定正确的 URL。 |
   |          视图名称           |                                                                            这是 Windows SharePoint Services 视图用于筛选适配器处理的文档。 例如，已批准的订单。 将此字段留空，来处理源文档库中的所有现有文档。 该适配器将不处理文件夹显示在一个视图，并在这些文件夹中包含的消息。 可以创建平面视图将包括子文件夹中现有的文档的平面结构中显示的所有文档。 **注意：** 将处理平面视图中的所有消息。                                                                            |
   | Microsoft Office 集成 |                                                                                                                                                        选择“可选”将尽可能尝试删除 InfoPath 处理指令，如果不能删除（例如，二进制文档），则按原样处理。 选择“是”将删除 InfoPath 处理指令，如果出现错误，则跳过该消息。 选择“否”将按原样处理文档。 对于二进制消息，必须使用“否”或“可选”值。                                                                                                                                                         |


8. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
 [如何配置 Windows SharePoint Services 发送处理程序](../core/how-to-configure-a-windows-sharepoint-services-send-handler.md)   
 [如何配置 Windows SharePoint Services 发送端口](../core/how-to-configure-a-windows-sharepoint-services-send-port.md)   
 [如何创建发送端口](../core/how-to-create-a-send-port2.md)   
 [Windows SharePoint Services 适配器属性参考](../core/windows-sharepoint-services-adapter-properties-reference.md)   
 [Windows SharePoint Services 适配器表达式](../core/windows-sharepoint-services-adapter-expressions.md)   
 [支持的 Windows SharePoint Services 栏类型](../core/supported-windows-sharepoint-services-column-types.md)