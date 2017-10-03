---
title: "如何配置 Windows SharePoint Services 发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters, send ports
- configuring [Windows SharePoint Services adapters], send ports
- send ports, Windows SharePoint Services adapters
ms.assetid: 7713d3cc-cd8d-43db-8dac-2a7442632b87
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7e41aca0c55170de7f8e1514e5a4c77796f48cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-windows-sharepoint-services-send-port"></a>如何配置 Windows SharePoint Services 发送端口
本主题介绍如何通过使用 BizTalk Server 管理控制台来创建和配置 Windows SharePoint Services 发送端口。  
  
### <a name="to-create-and-configure-a-windows-sharepoint-services-send-port"></a>创建和配置 Windows SharePoint Services 发送端口  
  
1.  在 BizTalk Server 管理控制台中，创建新的发送端口或双击现有发送端口以对其进行修改。 有关详细信息，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 配置所有发送端口选项并指定**Windows SharePoint Services 传输属性**为**类型**选项**传输**部分**常规**选项卡。  
  
2.  上**常规**选项卡上，在**传输**部分，旁边**类型**，单击**配置**。  
  
3.  在**Windows SharePoint Services 传输属性**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |适配器 Web Services 端口|安装 Windows SharePoint Services 适配器 Web Services 的 IIS 网站的 HTTP 端口。 默认情况下，这是默认的网站在端口 80 上配置。 如果在任何其他 IIS 网站比默认网站上配置了 Windows SharePoint Services Web 服务，你将需要更新此值。|  
    |超时|对 Windows SharePoint Services 适配器 Web Services 进行的适配器运行时 Web Services 调用的超时值（以毫秒计）。 如果消息或批的大小超过适配器预期的平均大小，则可能需要增加此值。|  
    |目标文件夹 URL|Windows SharePoint Services 目标文件夹 URL，相对于 SharePoint 站点。 例如，Shared Documents、Shared Documents/Purchase Orders/ 或 Lists/Tasks。 您可以通过指定 SharePoint 列表的 URL（例如 Lists/Tasks）向该列表发送消息。 如果指定列表作为目标，则消息正文将不与列表项一起保存，但从消息中提取的值仍将升级到 SharePoint 栏中。 **注意：**有时 SharePoint 文档库、 列表或文件夹 URL 是不同于项的名称。 请查看 Internet Explorer 的地址栏以查找正确的 URL。|  
    |Filename|（可选）Windows SharePoint Services 文件名。 您可以键入如“PurchaseOrder0001.xml”之类的文本值，也可以键入表达式。 表达式可以包含文字、 宏和 XPATH 查询的任何组合，例如:"PurchOrd-%XPATH=//po:PurchaseOrderId%-%MessageID%.xml"。 如果未提供文件名，并且业务流程也未定义文件名，则该文件名将为原始文件的名称、业务流程提供的值或“Msg-%MessageID%.xml”。 **注意：** Filename 属性中指定的值如果将消息发送到列表中，会忽略，并且将不会保存任何 SharePoint 列中。 SharePoint 列表不具有“文件名”栏。 相反，更新使用可用的 16 列之一的标题列。 <br /><br /> 有关表达式的详细信息，请参阅[Windows SharePoint Services 适配器表达式](../core/windows-sharepoint-services-adapter-expressions.md)。|  
    |命名空间别名|（可选）以逗号或分号分隔的命名空间别名定义列表。 使用此字段可以定义在诸如“文件名”或“栏值”之类的字段中引入的 XPATH 查询所使用的命名空间别名。 例如，po='http://OrderProcess/POrder', conf='http://OrderProcess/Confirmation' xmlns=""; ipsol='{D8217CF1-4EF7-4bb5-A30D-765ECB09E0D9}'。 **注意：**此属性不会覆盖 WSS。ConfigNamespacesAliases 消息上下文属性定义的业务流程。 相反，这两个值将合并。|  
    |Overwrite|确定是否覆盖现有文件。 选择是将覆盖现有文件。 选择“否”将在已存在同名文件时引发错误，并挂起消息。 选择“重命名”可重命名该文件。 选择“业务流程”将使用业务流程定义的值。 **注意：**发送大量消息具有相同名称覆盖属性设置为 Yes 时可能会导致 SharePoint 错误被记录在事件查看器。 这些错误并不影响适配器的功能。 将重试所有失败的消息。|  
    |SharePoint 站点 URL|Windows SharePoint Services 网站的完整 URL。 例如，http://BizTalkServer/sites/TestSite。 **注意：**对要发送的 URI 端口或接收位置不能超过 256 个字符。|  
    |Microsoft Office 集成|选择“可选”将更改文档，以便在 InfoPath 等 Office 应用程序中自动打开该文档，如果未找到 InfoPath 解决方案，则将按原样保存文档。 选择“是”将更改文档，以便在 InfoPath 等 Office 应用程序中自动打开该文档，如果未找到 InfoPath 解决方案，则将挂起消息。 选择“是(InfoPath 表单库)”将更改文档，以便在将消息发送到 Windows SharePoint Services InfoPath 表单库时，在 InfoPath 等 Office 应用程序中使用在表单库中找到的 InfoPath 解决方案自动打开该文档。 如果该表单库中没有 InfoPath 解决方案，则将挂起消息。 选择“否”将按原样保存文档，不进行任何更改。 Orchestration 若要使用业务流程所定义的值。 对于二进制消息，否，否则必须使用可选的值。 **注意：**至少一个属性对模板文档库和 Microsoft Office 集成设置为是时，模板 Namespace 列或模板回退文档库和模板回退 Namespace 列是必需。|  
    |模板文档库|输入存储 InfoPath 解决方案的 SharePoint 文档库的名称。  例如， `My Solutions`。 这是适配器将在其中查找匹配的 InfoPath 解决方案的第一个位置。 如果找不到解决方案，适配器将在模板后备文档库中查找。 **注意：**模板 Namespace 列字段不为空时，此字段是必填。 **注意：**文档库必须具有至少一个 SharePoint 列的类型单个文本行具有命名空间填充该字段并可以使用此 InfoPath 解决方案中，打开 XML 文档的根节点或只是在根节点。 有关详细信息，请参阅[演练： 模块 2-将与 Windows SharePoint Services Adapter 集成 Office](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)。|  
    |模板后备文档库|输入存储 InfoPath 解决方案的 SharePoint 文档库的名称。  例如，“模板”。 如果在模板文档库中找不到解决方案，适配器将只在此文档库中搜索匹配的 InfoPath 解决方案。 “模板后备文档库”和“模板文档库”字段可用于两组 InfoPath 解决方案。 InfoPath 解决方案包括适合于所有通用目的的通用 InfoPath 解决方案，以及只用于特定合作伙伴的专用 InfoPath 解决方案。 “模板后备文档库”字段应指向通用解决方案，“模板文档库”字段应指向该特定合作伙伴的专用解决方案。 **注意：**模板回退 Namespace 列字段不为空时，此字段是必填。 **注意：**文档库必须具有至少一个 SharePoint 列的类型单个文本行具有命名空间填充该字段并可以使用此 InfoPath 解决方案中，打开 XML 文档的根节点或只是在根节点。 有关详细信息，请参阅[演练： 模块 2-将与 Windows SharePoint Services Adapter 集成 Office](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)。|  
    |模板后备命名空间栏|这是存储 InfoPath 解决方案命名空间的模板后备文档库 SharePoint 栏的名称。 例如，“命名空间”。 **注意：**模板回退文档库字段不为空时，此字段是必填。 **注意：**此字段是区分大小写。|  
    |模板命名空间栏|这是存储 InfoPath 解决方案命名空间的模板文档库 SharePoint 栏的名称。 例如，“命名空间”。 **注意：**模板文档库字段不为空时，此字段是必填。 **注意：**此字段是区分大小写。|  
    |列 `n`|这是目标文档库中存在的 Windows SharePoint Services 栏的名称。 应使用从消息中提取的值或在“栏值”字段中指定的值来更新此栏。 **注意：**还可以指定最多包含 16 列。 **注意：**此字段是区分大小写。|  
    |列 `n` 值|输入要为此消息设置的栏值。 你可以键入文本值（例如“Purchase Order”），也可以键入表达式。 表达式可以包括文本、宏和 XPATH 查询的任意组合。 例如，“%XPATH=//po:POAmount%”、“%SendingOrchestrationID%”。 **注意：**可以指定最多 16 个列的值。|  
  
4.  单击**确定**和**确定**再次以保存设置。  
  
## <a name="see-also"></a>另请参阅  
 [如何配置 Windows SharePoint Services 接收位置](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md)   
 [如何配置 Windows SharePoint Services 发送处理程序](../core/how-to-configure-a-windows-sharepoint-services-send-handler.md)   
 [如何创建发送端口](../core/how-to-create-a-send-port2.md)   
 [Windows SharePoint Services 适配器属性参考](../core/windows-sharepoint-services-adapter-properties-reference.md)   
 [Windows SharePoint Services 适配器表达式](../core/windows-sharepoint-services-adapter-expressions.md)   
 [支持的 Windows SharePoint Services 列类型](../core/supported-windows-sharepoint-services-column-types.md)