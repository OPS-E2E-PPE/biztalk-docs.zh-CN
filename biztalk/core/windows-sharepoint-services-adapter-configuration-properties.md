---
title: "Windows Sharepoint Services 适配器配置属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e6e26d51914211c5c51dfa232be4383d54f5e3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="windows-sharepoint-services-adapter-configuration-properties"></a>Windows Sharepoint Services 适配器配置属性
下表列出了可为 Windows Sharepoint Services 适配器接收位置设置的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|SiteUrl|VT_BSTR|指定 Windows SharePoint Services 网站的完整 URL。|发送端口或接收位置的 URI 不能超过 256 个字符。|无|  
|WssLocation|VT_BSTR|指定在其中检索文档的 Windows SharePoint Services 文档库的 URL（相对于 SharePoint 站点）。|无法从 SharePoint 列表或文件夹接收消息。|有时，SharePoint 文档库与相应项的名称并不相同。 请查看 Internet Explorer 的地址栏以确定正确的 URL。|  
|视图名|VT_BSTR|指定用于筛选适配器所处理的文档的 Windows SharePoint Services 视图。|无|将处理平面视图中的所有消息。|  
|ArchiveLocation|VT_BSTR|指定在其中存档已处理文件的 Windows SharePoint Services 文件夹的 URL（相对于 SharePoint 站点）。|无|有时，SharePoint 文档库、或文件夹的 URL 与相应项的名称并不相同。 请查看 Internet Explorer 的地址栏以确定正确的 URL。|  
|NamespaceAliases|VT_BSTR|指定以逗号或分号分隔的命名空间别名定义列表。|无|无|  
|ArchiveFileName|VT_BSTR|指定 Windows SharePoint Services 存档文件的名称。|此字段不支持“%SendingOrchestrationID%”和“%SendingOrchestrationType%”宏。|无|  
|Overwrite|VT_BSTR|指定是否覆盖存档位置中的现有文件。|有效值为<br /><br /> -是<br />-没有|默认值为“否”。|  
|ErrorThreshold|VT_BSTR|指定禁用接收位置时适配器可遇到的连续轮询失败的最大允许数目。|有效值为从 0 到 2147483647 之间。|若要永不禁用接收位置，请将此属性设置为 0。<br /><br /> 默认值为 10。|  
|PollingInterval|VT_BSTR|指定适配器为了确定是否有任何可以处理的新消息而执行的两次连续查询之间的时间间隔（以秒计）。|有效值为从 1 到 2147483647 之间。|指定较低的值会缩短适配器的吞吐量和响应时间。<br /><br /> 默认值为 60。|  
|BatchSize|VT_BSTR|指定 Windows SharePoint Services 消息传送适配器 Web Services 将按一批进行处理的最大文档数。|有效值为从 1 到 2147483647 之间。|处理批次可能包含比定义的批处理大小; 较少消息但是，它将永远不会包含更多的消息。<br /><br /> 默认值为 20。|  
|OfficeIntegration|VT_BSTR|指定 Office 集成级别。|有效值为<br /><br /> -   **可选**-尝试尽可能删除 InfoPath 处理指令或作为处理是如果不可能。<br />-   **不**-处理文档"按原样。"<br />-   **是**-删除 InfoPath 处理指令或跳过发生错误时消息。|默认值为“可选”。|  
|超时|VT_BSTR|指定超时，以毫秒为单位，用于对 Windows SharePoint Services 适配器 Web 服务适配器运行时 Web 服务调用。|有效值从 1000年到 2147483647 之间。|默认值为 100000。|  
|AdapterWSPort|VT_BSTR|指定安装 Windows SharePoint Services 适配器 Web Services 的 IIS 网站的 HTTP 端口。|无|默认值为 80。|  
|URI|VT_BSTR|指定 Windows SharePoint Services 文档库的完整路径。|发送端口或接收位置的 URI 不能超过 256 个字符。|无|  
  
 以下代码显示用于设置这些属性的字符串的格式：  
  
```  
<CustomProps><AdapterConfig vt="8"><ReceiveLocation xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><SiteUrl>http://BTS2006/sites/BASSite/</SiteUrl><WssLocation>Shared Docs</WssLocation><ViewName>Approved</ViewName><ArchiveLocation>Archive</ArchiveLocation><NamespaceAliases>po='http://POProcess/POrder'</NamespaceAliases><ArchiveFileName>PurchaseOrder0001.xml</ArchiveFileName><Overwrite>no</Overwrite><ErrorThreshold>10</ErrorThreshold><PollingInterval>60</PollingInterval><BatchSize>20</BatchSize><OfficeIntegration>optional</OfficeIntegration><Timeout>100000</Timeout><AdapterWSPort>80</AdapterWSPort><uri>wss://bts2006:80/sites/BASSite/Shared+Docs?ViewName=Approved</uri></ReceiveLocation></AdapterConfig></CustomProps>  
```  
  
 下表列出了可为 Windows Sharepoint Services 适配器发送端口设置的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|SiteUrl|VT_BSTR|指定 Windows SharePoint Services 网站的完整 URL|发送端口或接收位置的 URI 不能超过 256 个字符。|无|  
|WssLocation|VT_BSTR|指定 Windows SharePoint Services 目标文件夹 URL，该 URL 是相对于 SharePoint 站点的相对位置。|无|有时，SharePoint 文档库、列表或文件夹的 URL 与相应项的名称并不相同。 请查看 Internet Explorer 的地址栏以查找正确的 URL。|  
|Overwrite|VT_BSTR|指定是否改写现有文件。|有效值为<br /><br /> -没有<br />-业务流程<br />-重命名<br />-是|默认值为“否”。|  
|NamespaceAliases|VT_BSTR|指定以逗号或分号分隔的命名空间别名定义列表。|无|使用此字段可以定义在字段中引入的 XPATH 查询所使用的命名空间别名。<br /><br /> 此属性不会替代业务流程定义的 WSS.ConfigNamespacesAliases 消息上下文属性。 相反，这两个值将合并。|  
|FileName|VT_BSTR|指定 Windows SharePoint Services 文件名。|无|在向列表发送消息时，将忽略在“文件名”属性中指定的值，也不会将该值保存在任何 SharePoint 栏中。 SharePoint 列表不具有“文件名”栏。 而是使用可用的 16 个栏之一更新“标题”栏。|  
|OfficeIntegration|VT_BSTR|指定是否更改文档，以便在 InfoPath 等 Office 应用程序中自动打开该文档，如果未找到 InfoPath 解决方案，则将按原样保存文档。|有效值为<br /><br /> -没有<br />-可选<br />-业务流程<br />-是<br />-yesformlibrary|默认值为“可选”。|  
|TemplatesDocLib|VT_BSTR|指定存储 InfoPath 解决方案的 SharePoint 文档库的名称。|如果 TemplatesNamespaceCol 属性包含一个值，则此属性必须包含某一值。|文档库必须至少具有一个用命名空间填充的单行文本类型的 SharePoint 栏以及可用此 InfoPath 解决方案打开的 XML 文档的根节点，或者只具有根节点。|  
|TemplatesNamespaceCol|VT_BSTR|指定存储 InfoPath 解决方案命名空间的模板后备文档库 SharePoint 栏的名称。|如果 TemplatesDocLib 属性包含一个值，则此属性必须包含某一值。<br /><br /> 此字段区分大小写。|无|  
|CustomTemplatesDocLib|VT_BSTR|指定存储 InfoPath 解决方案的 SharePoint 文档库的名称。|如果 CustomTemplatesNamespaceCol 属性包含一个值，则此属性必须包含某一值。<br /><br /> 此字段区分大小写。|无|  
|CustomTemplatesNamespaceCol|VT_BSTR|指定存储 InfoPath 解决方案命名空间的模板文档库 SharePoint 栏的名称。|如果 CustomTemplatesDocLib 属性包含一个值，则此属性必须包含某一值。<br /><br /> 此字段区分大小写。|无|  
|PropertyName(n)|VT_BSTR|指定目标文档库中存在的 Windows SharePoint Services 栏的名称。|此字段区分大小写。|最多可以指定 16 栏。|  
|PropertySource(n)|VT_BSTR|指定要为此消息设置的栏值。|无|最多可以指定 16 个栏值。|  
|超时|VT_BSTR|为对 Windows SharePoint Services 适配器 Web Services 进行的适配器运行时 Web Services 调用指定超时值（以毫秒计）。|有效值从 1000年到 2147483647 之间。|默认值为 100000。|  
|AdapterWSPort|VT_BSTR|指定安装 Windows SharePoint Services 适配器 Web Services 的 IIS 网站的 HTTP 端口。|无|默认值为 80。|  
|URI|VT_BSTR|指定 Windows SharePoint Services 目标文件夹 URL 的完整路径。|发送端口或接收位置的 URI 不能超过 256 个字符。|无|  
  
 以下代码显示用于设置这些属性的字符串的格式：  
  
> [!NOTE]
>  此字符串中省略了 PropertyName2 和 PropertySource2 到 PropertyName16 和 PropertySource16 的定义。  
  
```  
<CustomProps><AdapterConfig vt="8"><SendPort xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><SiteUrl>http://BizTalkServer/sites/BASSite/</SiteUrl><WssLocation>Shared Documents/Purchase Orders</WssLocation><Overwrite>yes</Overwrite><NamespaceAliases>po='http://OrderProcess/POrder'</NamespaceAliases><FileName>PurchaseOrder0001.xml</FileName><OfficeIntegration>yesformlibrary</OfficeIntegration><TemplatesDocLib>Templates</TemplatesDocLib><TemplatesNamespaceCol>NamespaceFallback</TemplatesNamespaceCol><CustomTemplatesDocLib>Shared Documents</CustomTemplatesDocLib><CustomTemplatesNamespaceCol>Namespace</CustomTemplatesNamespaceCol><PropertyName1>Column1</PropertyName1><PropertySource1>Column1 Value</PropertySource1><Timeout>100000</Timeout><AdapterWSPort>80</AdapterWSPort><uri>wss://biztalkserver:80/sites/BASSite/Shared%20Documents/Purchase%20Orders</uri></SendPort></AdapterConfig></CustomProps>  
```  
  
> [!NOTE]
>  在指定的适配器，使用适配器框架构建的 TransportTypeData 配置数据时，使用的名称/值对必须全部存储到\<AdapterConfig > 元素。 由于\<AdapterConfig > 元素指定 VT_BSTR (vt ="8") 数据类型则\<> 数据中的字符必须进行转义。