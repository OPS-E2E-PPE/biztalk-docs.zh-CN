---
title: Windows SharePoint Services 4.0 支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84be7aa0-2ff2-4e40-9c39-5cb89549c636
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6920de947165f7f3065f190d077d55dcbef30c7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971030"
---
# <a name="windows-sharepoint-services-40-support"></a>Windows Sharepoint Services 4.0 支持
用于 BizTalk Server 的 Windows SharePoint Services 适配器提供相同的功能用于 Windows SharePoint Services adapter [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]。 用于 BizTalk Server 的 Windows SharePoint Services 适配器还支持以下功能，可与 Windows SharePoint Services 4.0:  

- 将消息发送到 Windows SharePoint Services 4.0 博客站点。  

- 发送消息和来自 Windows SharePoint Services 4.0 Wiki 站点接收消息。  

  用于 BizTalk Server 的 Windows SharePoint Services 适配器不支持在 Windows SharePoint Services 4.0 中可用的下列功能：  

- **回收站**： 用于 BizTalk Server 适配器的 Windows SharePoint Services 适配器不支持接收，或从/向回收站显式发送消息。  

- **列出文件夹**： 用于 BizTalk Server 的 Windows SharePoint Services 适配器可向列表发送消息，但它不能接收来自列表的消息。 Windows SharePoint Services 4.0 支持在列表中的文件夹，但用于 BizTalk Server 的 Windows SharePoint Services 适配器不支持此功能。 因此，BizTalk Server 的 Windows SharePoint Services 适配器不能在根文件夹之外的列表文件夹中创建列表项。  

- 以下各节介绍了更详细地介绍如何使用 BizTalk Server 的 Windows SharePoint Services 适配器向 Windows SharePoint Services 4.0 博客网站发送消息以及如何将消息发送到和从 Windows SharePoint Services 接收消息4.0 Wiki 网站。  

## <a name="sending-to-a-windows-sharepoint-services-40-blog-site"></a>将发送到 Windows SharePoint Services 4.0 博客站点  
 在 Windows SharePoint Services 4.0 博客网站中，发布内容存储在**发**中定义列表和 post 类别**类别**列表。  

 若要将消息发布到 Windows SharePoint Services 4.0 博客网站，可在适配器中输入以下值**传输属性**对话框中配置使用 Windows SharePoint Services 适配器的发送端口时：  


|        “属性”        |                                                                                            ReplTest1                                                                                            |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 目标文件夹 URL |                                            相对于 SharePoint 网站的发布内容列表的目标文件夹 URL，如“Lists/Posts”。                                            |
|  SharePoint 站点 URL   | Windows SharePoint Services 4.0 博客站点，例如 http:// URL<em>\<servername\></em>/站点/博客/位置*\<servername\>* 是Web 服务器的实际名称的占位符。 |

 然后设置为值**类别**，**已发布**， **Title**，并**正文**属性设置相应发布的博客WSS 中的值。ConfigPropertiesXml 消息上下文属性。 可通过自定义管道或者在业务流程中实现此操作。 例如，业务流程中的下列表达式将设置 Message_Out 消息的 WSS.ConfigPropertiesXml 上下文属性中的值。  

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

 这种方法创建的帖子将设置为的状态**未获批准**，这将需要的博客所有者批准之前在站点上为可见。  

 可在列表的设置页上查看列表支持的列类型。 有关 Windows SharePoint Services 适配器支持的 Windows SharePoint Services 列类型的详细信息，请参阅[Windows SharePoint Services 适配器属性参考](../core/windows-sharepoint-services-adapter-properties-reference.md)。  

## <a name="sending-to-and-receiving-from-a-windows-sharepoint-services-40-wiki-document-library"></a>向发送和接收来自 Windows SharePoint Services 4.0 Wiki 文档库  
 在 Windows SharePoint Services 4.0 站点中，Wiki 网站使用**Wiki 页面**文档库。 Wiki 网页文档库将 Wiki 网页中的文本存储**Wiki 内容**使用的 UI 类型的列**多行文本**。 **多行文本**UI 类型与相关联**SPFieldType.Note** SharePoint 对象模型类型。 有关 Windows SharePoint Services 适配器支持的 Windows SharePoint Services 列类型的详细信息请参阅[Windows SharePoint Services 适配器属性参考](../core/windows-sharepoint-services-adapter-properties-reference.md)。  

### <a name="sending-to-a-windows-sharepoint-services-40-wiki-document-library"></a>将发送到 Windows SharePoint Services 4.0 Wiki 文档库  
 将消息发送给 Windows SharePoint Services 4.0 Wiki 网站，Wiki 网页的内容将存储在名为 Windows SharePoint Services 适配器上下文属性**WSS。ConfigPropertiesXml**。 若要将消息发布到 Windows SharePoint Services 4.0 Wiki 网站，可在适配器中输入以下值**传输属性**对话框中配置使用 Windows SharePoint Services 适配器的发送端口时：  


|        “属性”        |                                                                                            ReplTest1                                                                                            |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 目标文件夹 URL |                                                   相对于 SharePoint 网站的 Wiki 网站主页的 URL，如“wikiSP”。                                                    |
|  SharePoint 站点 URL   | Windows SharePoint Services 4.0 Wiki 网站，例如 http:// URL<em>\<servername\></em>/站点/wiki/位置*\<servername\>* 是web 服务器的实际名称的占位符。 |

 然后将设置为值**Wiki 内容**Wiki 页面通过 WSS 中设置相应的值的属性。ConfigPropertiesXml 消息上下文属性。 可通过自定义管道或者在业务流程中实现此操作。 例如，业务流程中的下列表达式将设置 Message_Out 消息的 WSS.ConfigPropertiesXml 上下文属性中的值：  

```  
str_Wiki = "This is a sample Wiki page entry.";  
Message_Out(WSS.ConfigPropertiesXml) = “<ConfigPropertiesXml>  
<PropertyName1>Wiki Content</PropertyName1>  
<PropertySource1>” + str_Wiki + “</PropertySource1>  
</ConfigPropertiesXml>”;  
```  

 在此表达式中的 str_Wiki 变量将使用**System.String**数据类型。  

> [!IMPORTANT]
>  Windows SharePoint Services 4.0 Wiki 文档库支持版本控制，但是，BizTalk Server 2010does 的 Windows SharePoint Services 适配器不支持版本控制。 因此，为 BizTalk Server 更新的 Windows SharePoint Services 适配器的 Wiki 网页将丢失其以前的版本。 鉴于此限制的是 Windows SharePoint Services 适配器接收的 BizTalk Server 和在不同的 Wiki 文档库中存档的 Wiki 页将只保留其最后一个版本，并删除所有其他版本。  

### <a name="receiving-from-a-windows-sharepoint-services-40-wiki-document-library"></a>接收来自 Windows SharePoint Services 4.0 Wiki 文档库  
 接收消息时从 Windows SharePoint Services 4.0 Wiki 站点，Wiki 网页的内容将存储在名为 Windows SharePoint Services 适配器上下文属性**WSS。InPropertiesXml**。  

 若要从 Windows SharePoint Services 4.0 Wiki 页接收一条消息，可在适配器中输入以下值**传输属性**对话框中配置使用 Windows SharePoint Services 适配器的接收位置时：  

|“属性”|ReplTest1|  
|--------------|-----------|  
|SharePoint 站点 URL|相对于 SharePoint 网站的 Wiki 网站主页的 URL，如“wiki”。|  
|源文档库 URL|相对于 SharePoint 网站的 Wiki 网站主页的 URL，如“wikiRL”。|  

 然后检索 wiki 网页的内容从**Wiki 内容**节点的**WSS。InPropertiesXml**接收到消息上下文属性。 可通过自定义管道或者在业务流程中实现此操作。 例如，在下面的业务流程表达式**str_Wiki**使用的值填充变量**Wiki 内容**节点从**WSS。InPropertiesXml**上下文属性**Message_In**消息。 然后，将**Wiki 内容**属性的**WSS。ConfigPropertiesXml**上下文属性**Message_Out**消息设置的值为**str_Wiki**变量：  

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

## <a name="see-also"></a>请参阅  
 [Windows SharePoint Services 适配器](../core/windows-sharepoint-services-adapter.md)