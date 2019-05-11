---
title: Windows Sharepoint Services 适配器配置属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- code samples, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, properties
- receive locations, adapters
- Windows SharePoint Services adapters, code sample
- Windows SharePoint Services adapters, send ports
- Windows SharePoint Services adapters, receive locations
- Windows SharePoint Services adapters
- send ports, adapters
ms.assetid: 20b08959-75d3-4613-9cea-582ac2813415
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd4d9afc512b99815ca5a7ea862ac45868e99edf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240329"
---
# <a name="windows-sharepoint-services-adapter-configuration-properties"></a>Windows Sharepoint Services 适配器配置属性
下表列出了可以为 Windows Sharepoint Services 适配器设置的配置属性接收位置：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|SiteUrl|VT_BSTR|指定 Windows SharePoint Services 网站的完整 URL。|URI 发送端口或接收位置不能超过 256 个字符。|None|  
|WssLocation|VT_BSTR|指定 Windows SharePoint Services 文档库中，相对于 SharePoint 站点，在其中检索文档的 URL。|无法从 SharePoint 列表或文件夹接收消息。|有时，SharePoint 文档库是不同于该项目的名称。 请查看 Internet Explorer 以发现正确的 URL 中的地址栏。|  
|ViewName|VT_BSTR|指定 Windows SharePoint Services 视图用于筛选适配器处理的文档。|None|将处理平面视图中的所有消息。|  
|ArchiveLocation|VT_BSTR|指定 Windows SharePoint Services 文件夹 URL，相对于 SharePoint 站点，其中存档已处理的文件。|None|有时 SharePoint 文档库中或文件夹的 URL 是不同于该项目的名称。 请查看 Internet Explorer 以发现正确的 URL 中的地址栏。|  
|NamespaceAliases|VT_BSTR|指定以逗号或分号分隔的命名空间别名定义列表。|None|None|  
|ArchiveFileName|VT_BSTR|指定存档的文件 Windows SharePoint Services 文件名。|此字段不支持"%sendingorchestrationid%"和"%sendingorchestrationtype%"宏。|None|  
|Overwrite|VT_BSTR|指定是否覆盖存档中的现有文件。|有效值为<br /><br /> -是<br />-   no|默认值是没有。|  
|ErrorThreshold|VT_BSTR|指定禁用接收位置时适配器遇到的连续轮询失败的最大数目。|有效值为从 0 到 2147483647 之间。|若要永不禁用接收位置，此属性设置为 0。<br /><br /> 默认值为 10。|  
|PollingInterval|VT_BSTR|指定以秒为单位，以查看是否可用于处理任何新消息的适配器由执行两次连续查询之间的时间间隔。|有效值为从 1 到 2147483647 之间。|指定较低的值可以提高适配器的吞吐量和响应时间。<br /><br /> 默认值为 60。|  
|BatchSize|VT_BSTR|指定为一批的最大 Windows SharePoint Services 消息传送适配器 Web 服务将处理的文档数。|有效值为从 1 到 2147483647 之间。|已处理的批次可能包含较少的消息定义的批大小;但是，它将永远不会包含更多的消息。<br /><br /> 默认值为 20。|  
|OfficeIntegration|VT_BSTR|指定 Office 集成级别。|有效值为<br /><br /> -   **可选**-尝试删除 InfoPath 处理指令，如果可能，或作为处理是如果不可能。<br />-   **不**-处理的文档"按原样。"<br />-   **是**-删除 InfoPath 处理指令或跳过发生错误时该消息。|默认值是可选的。|  
|超时|VT_BSTR|指定的超时值 （毫秒），对 Windows SharePoint Services 适配器 Web services 的适配器运行时 Web 服务调用。|有效值从 1000年到 2147483647 之间。|默认值为 100000。|  
|AdapterWSPort|VT_BSTR|指定安装 Windows SharePoint Services 适配器 Web services 的 IIS 网站的 HTTP 端口。|None|默认值为 80。|  
|uri|VT_BSTR|指定 Windows SharePoint Services 文档库的完整路径。|URI 发送端口或接收位置不能超过 256 个字符。|None|  
  
 下面的代码显示了使用设置的属性的字符串的格式：  
  
```  
<CustomProps><AdapterConfig vt="8"><ReceiveLocation xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><SiteUrl>http://BTS2006/sites/BASSite/</SiteUrl><WssLocation>Shared Docs</WssLocation><ViewName>Approved</ViewName><ArchiveLocation>Archive</ArchiveLocation><NamespaceAliases>po='http://POProcess/POrder'</NamespaceAliases><ArchiveFileName>PurchaseOrder0001.xml</ArchiveFileName><Overwrite>no</Overwrite><ErrorThreshold>10</ErrorThreshold><PollingInterval>60</PollingInterval><BatchSize>20</BatchSize><OfficeIntegration>optional</OfficeIntegration><Timeout>100000</Timeout><AdapterWSPort>80</AdapterWSPort><uri>wss://bts2006:80/sites/BASSite/Shared+Docs?ViewName=Approved</uri></ReceiveLocation></AdapterConfig></CustomProps>  
```  
  
 下表列出了可以为 Windows Sharepoint Services 适配器发送端口设置的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|SiteUrl|VT_BSTR|指定 Windows SharePoint Services 网站的完整 URL|URI 发送端口或接收位置不能超过 256 个字符。|None|  
|WssLocation|VT_BSTR|指定 Windows SharePoint Services 目标文件夹 URL，相对于 SharePoint 站点。|None|有时，SharePoint 文档库、 列表或文件夹 URL 是不同于该项目的名称。 请查看 Internet Explorer 查找正确的 URL 中的地址栏。|  
|Overwrite|VT_BSTR|指定是否覆盖现有文件。|有效值为<br /><br /> -   no<br />-业务流程<br />-   rename<br />-是|默认值是没有。|  
|NamespaceAliases|VT_BSTR|指定以逗号或分号分隔的命名空间别名定义列表。|None|使用此字段可以定义在字段中引入的 XPATH 查询使用的命名空间别名。<br /><br /> 此属性不会覆盖 WSS。业务流程定义 ConfigNamespacesAliases 消息上下文属性。 而是将合并两个值。|  
|FileName|VT_BSTR|指定 Windows SharePoint Services 文件的名称|None|时向列表发送消息，Filename 属性中指定的值将被忽略，并将不会保存在任何 SharePoint 栏。 SharePoint 列表中没有文件名列。 而是更新使用其中一个 16 可用列的标题列。|  
|OfficeIntegration|VT_BSTR|指定要更改文档，以便在 InfoPath 等 Office 应用程序中自动打开或保存文档，因为是如果找到任何 InfoPath 解决方案。|有效值为<br /><br /> -   no<br />-可选<br />-业务流程<br />-是<br />-yesformlibrary|默认值是可选的。|  
|TemplatesDocLib|VT_BSTR|指定存储 InfoPath 解决方案的 SharePoint 文档库的名称。|此属性必须包含一个值，如果 TemplatesNamespaceCol 属性包含的值。|文档库必须具有至少一个类型的单行文本填充与命名空间和可用此 InfoPath 解决方案中，打开的 XML 文档的根节点或只具有根节点的 SharePoint 栏。|  
|TemplatesNamespaceCol|VT_BSTR|指定存储 InfoPath 解决方案命名空间的模板后备文档库 SharePoint 列的名称。|此属性必须包含一个值，如果 TemplatesDocLib 属性包含的值。<br /><br /> 此字段是区分大小写。|None|  
|CustomTemplatesDocLib|VT_BSTR|指定存储 InfoPath 解决方案的 SharePoint 文档库的名称。|此属性必须包含一个值，如果 CustomTemplatesNamespaceCol 属性包含的值。<br /><br /> 此字段是区分大小写。|None|  
|CustomTemplatesNamespaceCol|VT_BSTR|指定存储 InfoPath 解决方案命名空间的模板文档库 SharePoint 栏的名称。|此属性必须包含一个值，如果 CustomTemplatesDocLib 属性包含的值。<br /><br /> 此字段是区分大小写。|None|  
|PropertyName(n)|VT_BSTR|指定目标文档库中存在的 Windows SharePoint Services 栏的名称。|此字段是区分大小写。|可以指定最多 16 个列。|  
|PropertySource(n)|VT_BSTR|指定要为此消息设置的栏值。|None|可以指定最多 16 个列的值。|  
|超时|VT_BSTR|指定超时，以毫秒为单位，用于对 Windows SharePoint Services 适配器 Web services 的适配器运行时 Web 服务调用。|有效值从 1000年到 2147483647 之间。|默认值为 100000。|  
|AdapterWSPort|VT_BSTR|指定安装 Windows SharePoint Services 适配器 Web services 的 IIS 网站的 HTTP 端口。|None|默认值为 80。|  
|uri|VT_BSTR|指定 Windows SharePoint Services 目标文件夹 URL 的完整路径。|URI 发送端口或接收位置不能超过 256 个字符。|None|  
  
 下面的代码显示了使用设置的属性的字符串的格式：  
  
> [!NOTE]
>  此字符串中省略了 PropertyName2 和 PropertySource2 到 PropertyName16 和 PropertySource16 的定义。  
  
```  
<CustomProps><AdapterConfig vt="8"><SendPort xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><SiteUrl>http://BizTalkServer/sites/BASSite/</SiteUrl><WssLocation>Shared Documents/Purchase Orders</WssLocation><Overwrite>yes</Overwrite><NamespaceAliases>po='http://OrderProcess/POrder'</NamespaceAliases><FileName>PurchaseOrder0001.xml</FileName><OfficeIntegration>yesformlibrary</OfficeIntegration><TemplatesDocLib>Templates</TemplatesDocLib><TemplatesNamespaceCol>NamespaceFallback</TemplatesNamespaceCol><CustomTemplatesDocLib>Shared Documents</CustomTemplatesDocLib><CustomTemplatesNamespaceCol>Namespace</CustomTemplatesNamespaceCol><PropertyName1>Column1</PropertyName1><PropertySource1>Column1 Value</PropertySource1><Timeout>100000</Timeout><AdapterWSPort>80</AdapterWSPort><uri>wss://biztalkserver:80/sites/BASSite/Shared%20Documents/Purchase%20Orders</uri></SendPort></AdapterConfig></CustomProps>  
```  
  
> [!NOTE]
>  当指定为使用适配器框架生成的适配器的 TransportTypeData 配置数据，使用的名称/值对必须全部存储到\<AdapterConfig\>元素。 由于\<AdapterConfig\>元素指定 VT_BSTR (vt ="8") 数据类型则\<\>必须对数据中的字符进行转义。