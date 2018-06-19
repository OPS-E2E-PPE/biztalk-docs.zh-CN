---
title: Windows SharePoint Services 适配器属性参考 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ConfigCustomTemplatesDocLib property [Windows SharePoint Services adapters]
- InFileSize property [Windows SharePoint Services adapters]
- InIconUrl property [Windows SharePoint Services adapters]
- InOfficeIntegration property [Windows SharePoint Services adapters]
- code samples, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, properties
- ConfigCustomTemplatesNamespaceCol property [Windows SharePoint Services adapters]
- configuring [Windows SharePoint Services adapters], properties
- ConfigTemplatesDocLib property [Windows SharePoint Services adapters]
- InPropertiesXml property [Windows SharePoint Services adapters]
- InItemId property [Windows SharePoint Services adapters]
- InListName property [Windows SharePoint Services adapters]
- InArchivedMsgUrl property [Windows SharePoint Services adapters]
- Filename property [Windows SharePoint Services adapters]
- InListUrl property [Windows SharePoint Services adapters]
- ConfigTemplatesNamespaceCol property [Windows SharePoint Services adapters]
- InLastModifiedBy property [Windows SharePoint Services adapters]
- ConfigOverwrite property [Windows SharePoint Services adapters]
- ConfigPropertiesXml property [Windows SharePoint Services adapters]
- TransmittedFileLocation property [Windows SharePoint Services adapters]
- InTitle property [Windows SharePoint Services adapters]
- Windows SharePoint Services adapters, code samples
- InCreated property [Windows SharePoint Services adapters]
- InCreatedBy property [Windows SharePoint Services adapters]
- InLastModified property [Windows SharePoint Services adapters]
- URL property [Windows SharePoint Services adapters]
- InEditUrl property [Windows SharePoint Services adapters]
- ConfigOfficeIntegration property [Windows SharePoint Services adapters]
- ConfigTimeout property [Windows SharePoint Services adapters]
- ConfigNamespaceAliases property [Windows SharePoint Services adapters]
- ConfigAdapterWSPort property [Windows SharePoint Services adapters]
ms.assetid: c64c43ac-05bb-427c-987a-71663ae8e43d
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 691708378d778eb0c91be73fe2b775d5bfd27cfd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22291749"
---
# <a name="windows-sharepoint-services-adapter-properties-reference"></a>Windows SharePoint Services 适配器属性参考
以下 Windows SharePoint Services 适配器属性已升级到 BizTalk Server 中，或可用来为传出消息指定发送端口配置选项。 这些属性可用于访问消息的 Windows SharePoint Services 信息，或用于在业务流程中向 Windows SharePoint Services 适配器提供信息。  
  
## <a name="message-property-precedence"></a>消息属性优先级  
 在替代业务流程和发送端口中定义的消息属性时，存在一个优先级规则。  
  
 以下为相应的规则：  
  
1.  在 PropertiesXML 内部的业务流程中定义的属性  
  
2.  在业务流程中定义的属性  
  
3.  在属性名称/或属性源集合内部的发送端口级别上定义的属性  
  
4.  在发送端口级别上定义的属性  
  
## <a name="considerations-and-known-issues"></a>注意事项和已知问题  
 以下为 Windows SharePoint Services 适配器属性的注意事项：  
  
-   下面所列的业务流程属性将根据属性位置与端口定义的属性进行合并。 如果存在冲突，则业务流程属性将覆盖发送端口属性。  
  
## <a name="property-types"></a>属性类型  
  
|属性类型|Description|  
|-------------------|-----------------|  
|**IN**|IN 属性是从 Windows SharePoint Services 获取值的 BizTalk Server 属性。 **注意：** 不应修改这些属性的业务流程中。|  
|**配置**|CONFIG 属性是从 BizTalk 业务流程或自定义管道获取值的属性。 此值由 Windows SharePoint Services 适配器在确定传出消息的目标时使用。 使用 CONFIG 属性，您可以在业务流程或自定义管道中指定一些需要在发送端口上定义的属性的值。 除 URL 属性之外，不以 IN 或 CONFIG 开头的属性都是 IN 和 CONFIG 属性。|  
|**提升**|PROMOTED 属性可由基于内容的路由 (CBR) 使用。 CBR 不能使用没有标记为 PROMOTED 的属性。 **注意：** 虽然所有适配器属性将都显示在 CBR 筛选器编辑器中，可以为 CBR 使用提升的属性。|  
|**特殊**|N/A|  
  
> [!NOTE]
>  所有属性都位于 http://schemas.microsoft.com/BizTalk/2006/WindowsSharePointServices-properties 命名空间中，并可通过使用 `WSS.<WSS_Property_Name>` 语法从业务流程或发送端口筛选器进行访问。  
  
## <a name="property-list"></a>属性列表  
  
|Windows SharePoint Services 标准栏|Windows SharePoint Services 属性名称和类型|类型|Description|属性类型|  
|-------------------------------------------------|--------------------------------------------------------|----------|-----------------|-------------------|  
|Name|Filename|xs:string|具有 Windows SharePoint Services 文件扩展名的文件名。 文件名（包括扩展名）在文档库中是唯一的。|IN/CONFIG/ PROMOTED|  
|N/A|Url|xs:string|文件的 URL。|IN/PROMOTED|  
|N/A|TransmittedFileLocation|N/A|此属性由业务活动监视 (BAM) 用于集成，在业务流程中不可用。|SPECIAL|  
|N/A|InArchivedMsgUrl|xs:string|存档文档库中的文件的 URL。 如果接收位置没有对消息进行存档，则此属性不可用。|IN/PROMOTED|  
|类型|InIconUrl|xs:string|用于表示文档的 Windows SharePoint Services 图标的 URL。|IN|  
|Title|InTitle|xs:string|Windows SharePoint Service 文件的标题。 这与文件名不同。 标题在文档库中不必是唯一的。|IN/PROMOTED|  
|修改时间|InLastModified|xs:dateTime|Windows SharePoint Service 的上次修改日期。|IN/PROMOTED|  
|修改者|InLastModifiedBy|xs:string|上次修改该文件的用户的姓名。|IN/PROMOTED|  
|ID|InItemId|xs:int|文件的 ID。 这是一个在文档库中唯一的整数，可用于访问该文件。|IN|  
|编辑|InEditUrl|xs:string|可访问以编辑文件属性的 URL。|IN|  
|创建时间|InCreated|xs:dateTime|创建 Windows SharePoint Service 文件的日期。|IN/PROMOTED|  
|创建者|InCreatedBy|xs:string|创建文件的用户。|IN/PROMOTED|  
|文件大小|InFileSize|xs:int|Windows SharePoint Services 文件的大小。|IN|  
|N/A|InListName|xs:string|此文件所在的文档库的名称。|IN/PROMOTED|  
|N/A|InListUrl|xs:string|此文件所在的文档库或文档库文件夹的 URL。|IN|  
|N/A|InPropertiesXml|xs:string|包含所有标准和用户定义的 Windows SharePoint Services 栏的平面 XML 文档。 使用该文档可以在业务流程中访问所有 Windows SharePoint Services 栏值，包括用户定义的栏的值。 **注意：** 它不具有 16 列限制。 **注意：** 请参阅本主题的下一节中的示例 InPropertiesXml 值。|IN|  
|N/A|InOfficeIntegration|xs:string|取决于接收位置的值。 这是 `yes`、`no`，或 `optional`。|IN|  
|N/A|ConfigOverwrite|xs:string|如果值为“是”，则覆盖具有相同名称的现有文件。 如果值为“否”，当存在具有相同名称的文件时将会出现错误。 如果值为“重命名”，则通过为文件名附加一个唯一的序列来将文件更改为唯一的名称。 **注意：** 它类似于物理发送端口覆盖字段。 **注意：** Orchestration 不是此字段的有效值。|CONFIG|  
|N/A|ConfigNamespaceAliases|xs:string|XPATH 的别名定义。|CONFIG|  
|N/A|ConfigOfficeIntegration|xs:string|如果应调用 OfficeImporters，则值为“是”。 如果值为“否”，则按原样处理消息。 如果选择“可选”，则当找到 IP 解决方案时为“是”，否则为“否”。 **注意：** 它类似于物理发送端口的 Microsoft Office 集成字段。 **注意：** Orchestration 不是此字段的有效值。|CONFIG|  
|N/A|ConfigTemplatesDocLib|xs:string|后备文档库名称。 这是辅助搜索位置。 **注意：** 它类似于物理发送端口的模板回退文档库字段。|CONFIG|  
|N/A|ConfigTemplatesNamespaceCol|xs:string|后备文档库的命名空间栏名称。 **注意：** 它类似于物理发送端口模板回退 Namespace 列字段。|CONFIG|  
|N/A|ConfigCustomTemplatesDocLib|xs:string|主文档库名称。 这是首选搜索位置。 **注意：** 它类似于物理发送端口的模板文档库字段。|CONFIG|  
|N/A|ConfigCustomTemplatesNamespaceCol|xs:string|主文档库的命名空间栏名称。 **注意：** 它类似于物理发送端口的模板 Namespace 列字段。|CONFIG|  
|N/A|ConfigPropertiesXml|xs:string|包含所有要在 Windows SharePoint Services 中更新的 Windows SharePoint Services 栏名称和值的平面 XML 文档。 使用该文档，业务流程开发人员可以为要在 SharePoint 中创建的后续消息设置 SharePoint 栏值。 **注意：** 这是类似于通过列 n 提供的功能和列 n 的值字段，而实现的物理发送端口。 **注意：** 它有一个 16 列限制。 **注意：** 请参阅本主题中后面的示例 ConfigPropertiesXml 值。|CONFIG|  
|N/A|ConfigTimeout|xs:int|Web Services 调用的超时值（毫秒）。|CONFIG|  
|N/A|ConfigAdapterWSPort|xs:int|安装和配置适配器的端口或 IIS 网站。 **注意：** 业务流程中的无效的端口配置值将会挂起消息，即使物理发送端口值将重写业务流程定义值。|CONFIG|  
  
## <a name="sample-inpropertiesxml"></a>示例 InPropertiesXml  
 以下为 InPropertiesXml 的 XML 示例：  
  
```  
<InPropertiesXml>  
     <Property name="InItemId">2</Property>  
     <Property name="Created">12/14/2004 1:30:31 PM</Property>  
     <Property name="Author">3;#John Doe</Property>  
     <Property name="Modified">12/14/2004 1:30:31 PM</Property>  
     <Property name="Editor">3;#John Doe</Property>  
     <Property name="_ModerationStatus">0</Property>  
     <Property name="_ModerationComments" />  
     <Property name="FileRef">/sites/BASSite/SourceLibrary/PO1.xml</Property>  
     <Property name="FileDirRef">2;#sites/BASSite/SourceLibrary</Property>  
     <Property name="InLastModified">2004-12-14 13:30:31</Property>  
     <Property name="InCreated">2004-12-14 13:30:31</Property>  
     <Property name="InFileSize">7338</Property>  
     <Property name="FSObjType">0</Property>  
     <Property name="CheckedOutUserId">2;#3</Property>  
     <Property name="Filename">PO1.xml</Property>  
     <Property name="VirusStatus">2;#7338</Property>  
     <Property name="CheckedOutTitle">2;#John Doe</Property>  
     <Property name="LinkCheckedOutTitle">John Doe</Property>  
     <Property name="InLastModifiedBy">MyDomain\jdoe</Property>  
     <Property name="InCreatedBy">MyDomain\jdoe</Property>  
     <Property name="owshiddenversion">1</Property>  
     <Property name="File_x0020_Type">xml</Property>  
     <Property name="HTML_x0020_File_x0020_Type" />  
     <Property name="_SourceUrl" />  
     <Property name="_SharedFileIndex" />  
     <Property name="LinkFilenameNoMenu">PO1.xml</Property>  
     <Property name="LinkFilename">PO1.xml</Property>  
     <Property name="SelectTitle">2</Property>  
     <Property name="SelectFilename">2</Property>  
     <Property name="Edit">xml</Property>  
     <Property name="InIconUrl">/sites/BASSite/SourceLibrary/PO1.xml</Property>  
     <Property name="Url">http://localhost:80/sites/BASSite/SourceLibrary/PO1.xml</Property>  
     <Property name="EncodedAbsUrl">PO1</Property>  
     <Property name="BaseName">7338</Property>  
     <Property name="FileSizeDisplay" />  
     <Property name="InstanceID">200</Property>  
     <Property name="Order" />  
     <Property name="InTitle" />  
     <Property name="ColumnOne" />  
     <Property name="ColumnTwo" />  
     <Property name="ColumnThree" />  
     <Property name="ColumnFour" />  
     <Property name="InListName">SourceLibrary</Property>  
     <Property name="InListUrl">http://localhost:80/sites/BASSite/SourceLibrary</Property>  
     <Property name="InEditUrl">http://localhost:80/sites/BASSite/SourceLibrary/Forms/EditForm.aspx?ID=2</Property>  
     <Property name="InOfficeIntegration">yes</Property>  
</InPropertiesXml>  
```  
  
## <a name="sample-configpropertiesxml"></a>示例 ConfigPropertiesXml  
 以下为 ConfigPropertiesXml 的 XML 示例：  
  
```  
<ConfigPropertiesXml>  
     <PropertyName1>PO number</PropertyName1>  
     <PropertySource1>%XPATH=//orchns:PurchaseOrder/orchns:Header/orchns:ID%</PropertySource1>  
     <PropertyName2>Charge To</PropertyName2>  
     <PropertySource2>%XPATH=//orchns:PurchaseOrder/orchns:orderBody/orchns:chargeTo%</PropertySource2>  
     <PropertyName3>PO Priority</PropertyName3>  
     <PropertySource3>%XPATH=//orchns:PurchaseOrder/orchns:orderBody/orchns:priority%</PropertySource3>  
     <PropertyName4>Order Date</PropertyName4>  
     <PropertySource4>%XPATH=//orchns:PurchaseOrder/orchns:orderBody/orchns:dateOrdered%</PropertySource4>  
</ConfigPropertiesXml>  
```  
  
## <a name="see-also"></a>另请参阅  
 [如何配置 Windows SharePoint Services 接收位置](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md)   
 [如何配置 Windows SharePoint Services 发送处理程序](../core/how-to-configure-a-windows-sharepoint-services-send-handler.md)   
 [如何配置 Windows SharePoint Services 发送端口](../core/how-to-configure-a-windows-sharepoint-services-send-port.md)   
 [如何创建发送端口](../core/how-to-create-a-send-port2.md)   
 [Windows SharePoint Services 适配器表达式](../core/windows-sharepoint-services-adapter-expressions.md)   
 [支持的 Windows SharePoint Services 列类型](../core/supported-windows-sharepoint-services-column-types.md)