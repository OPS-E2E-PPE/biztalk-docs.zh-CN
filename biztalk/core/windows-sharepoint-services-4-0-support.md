---
title: "Windows SharePoint Services 4.0 支持 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 84be7aa0-2ff2-4e40-9c39-5cb89549c636
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45f3fedbdc4217ef5379b5e890568346a565a235
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="windows-sharepoint-services-40-support"></a>Windows Sharepoint Services 4.0 支持
用于 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 的 Windows SharePoint Services 适配器提供与用于 [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] 的 Windows SharePoint Services 适配器相同的功能。 Windows SharePoint Services 适配器[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]还支持适用于 Windows SharePoint Services 4.0 的以下功能：  
  
-   将消息发送到 Windows SharePoint Services 4.0 博客网站。  
  
-   消息发送到和来自 Windows SharePoint Services 4.0 Wiki 站点接收消息。  
  
 Windows SharePoint Services 适配器[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]不是 Windows SharePoint Services 4.0 中提供以下功能提供支持：  
  
-   **回收站**： 用于 Windows SharePoint Services adapter[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]适配器不支持接收，或者从/到回收站显式发送消息。  
  
-   **列出文件夹**： 用于 Windows SharePoint Services adapter[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]可以将消息发送到列表，但它不能从列表中接收消息。 Windows SharePoint Services 4.0 支持文件夹中列表，但其的 Windows SharePoint Services 适配器[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]不支持此功能。 因此，用于 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 的 Windows SharePoint Services 适配器无法在根文件夹之外的列表文件夹中创建列表项。  
  
-   下列各节更详细地描述了如何使用的 Windows SharePoint Services 适配器[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]将消息发送到 Windows SharePoint Services 4.0 博客网站以及如何将消息发送到和从 Windows SharePoint 接收消息服务 4.0 Wiki 站点。  
  
## <a name="sending-to-a-windows-sharepoint-services-40-blog-site"></a>将发送到 Windows SharePoint Services 4.0 博客网站  
 在 Windows SharePoint Services 4.0 博客网站中，文章存储在**文章**列表和 post 类别中定义**类别**列表。  
  
 若要发布到 Windows SharePoint Services 4.0 博客站点的消息，输入以下值在适配器中**传输属性**对话框中配置使用 Windows SharePoint Services 适配器发送端口时：  
  
|属性|值|  
|--------------|-----------|  
|目标文件夹 URL|相对于 SharePoint 网站的发布内容列表的目标文件夹 URL，如“Lists/Posts”。|  
|SharePoint 站点 URL|Windows SharePoint Services 4.0 博客站点，例如 http:// URL*\<servername >*/站点/博客/其中 *\<servername >*是实际名称的占位符Web 服务器。|  
  
 然后设置的值**类别**，**已发布**，**标题**，和**正文**博客发布设置相应的属性WSS 中的值。ConfigPropertiesXml 消息上下文属性。 可通过自定义管道或者在业务流程中实现此操作。 例如，业务流程中的下列表达式将设置 Message_Out 消息的 WSS.ConfigPropertiesXml 上下文属性中的值。  
  
```  
int_Category = 1;  
str_Published = Microsoft.SharePoint.Utilities.SPUtility.CreateISO8601DateTimeFromSystemDateTime(System.DateTime.Now);  
// requires a reference to Microsoft.SharePoint.dll  
str_Title = "This is the title of the post from the WSS adapter";  
str_Body = "This is the body of the post from the WSS adapter";  
  
Message_Out(WSS.ConfigPropertiesXml) = “<ConfigPropertiesXml>  
<PropertyName1>Category</PropertyName1>  
<PropertySource1>” + int_Category + “</PropertySource1>  
<PropertyName2>Published</PropertyName2>  
<PropertySource2>” + str_Published + “</PropertySource2>  
<PropertyName3>Title</PropertyName3>  
<PropertySource3>” + str_Title + “</PropertySource3>  
<PropertyName4>Body</PropertyName4>  
<PropertySource4>” + str_Body + “</PropertySource4>  
</ConfigPropertiesXml>”;  
```  
  
 此表达式中的各变量将采用以下类型：  
  
|变量名称|类型|  
|-------------------|----------|  
|int_Category|System.Int32|  
|str_Published|System.String|  
|str_Title|System.String|  
|str_Body|System.String|  
  
 这种方法创建一个帖子将设置为的状态**未获批准**，这将需要由博客所有者批准之前在站点上是可见。  
  
 可在列表的设置页上查看列表支持的列类型。 有关由 Windows SharePoint Services 适配器支持的 Windows SharePoint Services 列类型的详细信息，请参阅[Windows SharePoint Services 适配器属性参考](../core/windows-sharepoint-services-adapter-properties-reference.md)。  
  
## <a name="sending-to-and-receiving-from-a-windows-sharepoint-services-40-wiki-document-library"></a>发送到和接收来自 Windows SharePoint Services 4.0 Wiki 文档库  
 在 Windows SharePoint Services 4.0 网站中，Wiki 站点使用**Wiki 页**文档库。 Wiki 页文档库存储中的 Wiki 页面文本**Wiki 内容**使用 UI 类型的列**多行文本**。 **多行文本**UI 类型与容量相关联**SPFieldType.Note** SharePoint 对象模型类型。 有关由 Windows SharePoint Services 适配器支持的 Windows SharePoint Services 列类型的详细信息请参阅[Windows SharePoint Services 适配器属性参考](../core/windows-sharepoint-services-adapter-properties-reference.md)。  
  
### <a name="sending-to-a-windows-sharepoint-services-40-wiki-document-library"></a>将发送到 Windows SharePoint Services 4.0 Wiki 文档库  
 将消息发送给 Windows SharePoint Services 4.0 Wiki 站点，Wiki 页的内容存储在名为的 Windows SharePoint Services adapter 上下文属性**WSS。ConfigPropertiesXml**。 若要发布到 Windows SharePoint Services 4.0 Wiki 站点的消息，输入以下值在适配器中**传输属性**对话框中配置使用 Windows SharePoint Services 适配器发送端口时：  
  
|属性|值|  
|--------------|-----------|  
|目标文件夹 URL|相对于 SharePoint 网站的 Wiki 网站主页的 URL，如“wikiSP”。|  
|SharePoint 站点 URL|Windows SharePoint Services 4.0 Wiki 站点，例如 http:// URL*\<servername >*/站点/wiki/其中 *\<servername >*是实际名称的占位符web 服务器。|  
  
 然后将的值设置**Wiki 内容**Wiki 页 WSS 中设置相应的值的属性。ConfigPropertiesXml 消息上下文属性。 可通过自定义管道或者在业务流程中实现此操作。 例如，业务流程中的下列表达式将设置 Message_Out 消息的 WSS.ConfigPropertiesXml 上下文属性中的值：  
  
```  
str_Wiki = "This is a sample Wiki page entry.";  
Message_Out(WSS.ConfigPropertiesXml) = “<ConfigPropertiesXml>  
<PropertyName1>Wiki Content</PropertyName1>  
<PropertySource1>” + str_Wiki + “</PropertySource1>  
</ConfigPropertiesXml>”;  
```  
  
 将此表达式中的 str_Wiki 变量**System.String**数据类型。  
  
> [!IMPORTANT]
>  Windows SharePoint Services 4.0 Wiki 文档库支持版本控制，但是，BizTalk Server 2010does 的 Windows SharePoint Services 适配器不支持版本控制。 因此，通过用于 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 的 Windows SharePoint Services 适配器更新的 Wiki 网页将丢失其以前的版本。 鉴于此限制，通过用于 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 的 Windows SharePoint Services 适配器接收并在其他不同 Wiki 文档库中存档的 Wiki 网页将只保留其最后一个版本，并删除所有其他版本。  
  
### <a name="receiving-from-a-windows-sharepoint-services-40-wiki-document-library"></a>接收从 Windows SharePoint Services 4.0 Wiki 文档库  
 在从 Windows SharePoint Services 4.0 Wiki 站点接收消息时, Wiki 页的内容存储在名为的 Windows SharePoint Services adapter 上下文属性**WSS。InPropertiesXml**。  
  
 若要从 Windows SharePoint Services 4.0 Wiki 页接收一条消息，可在适配器中输入以下值**传输属性**对话框中配置使用 Windows SharePoint Services 适配器接收位置时：  
  
|属性|值|  
|--------------|-----------|  
|SharePoint 站点 URL|相对于 SharePoint 网站的 Wiki 网站主页的 URL，如“wiki”。|  
|源文档库 URL|相对于 SharePoint 网站的 Wiki 网站主页的 URL，如“wikiRL”。|  
  
 然后检索 wiki 页面内容从**Wiki 内容**节点**WSS。InPropertiesXml**收到的消息的上下文属性。 可通过自定义管道或者在业务流程中实现此操作。 例如，在下面的业务流程表达式**str_Wiki**变量会使用的值填充**Wiki 内容**节点从**WSS。InPropertiesXml** context 属性**Message_In**消息。 然后， **Wiki 内容**属性**WSS。ConfigPropertiesXml** context 属性**Message_Out**消息设置的值为**str_Wiki**变量：  
  
```  
str_PropertiesXml = Message_In(WSS.InPropertiesXml);  
doc = doc.LoadXml(str_PropertiesXml);  
node = doc.SelectSingleNode("InPropertiesXml/Property[@name='Wiki Content']);  
str_Wiki = node.InnerText;  
Message_Out(WSS.ConfigPropertiesXml) = “<ConfigPropertiesXml>  
<PropertyName1>Wiki Content</PropertyName1>  
<PropertySource1>” + str_Wiki + “</PropertySource1>  
</ConfigPropertiesXml>”;  
```  
  
 此表达式中的各变量将采用以下类型：  
  
|变量名称|类型|  
|-------------------|----------|  
|str_PropertiesXml|System.Xml.XmlDocument|  
|doc|System.Xml.XmlDocument|  
|节点|System.Xml.XmlNode|  
|str_Wiki|System.String|  
  
## <a name="see-also"></a>另请参阅  
 [Windows SharePoint Services 适配器](../core/windows-sharepoint-services-adapter.md)