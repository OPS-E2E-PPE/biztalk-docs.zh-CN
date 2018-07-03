---
title: 适配器本地化问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d200ce9-1a60-455b-88b0-6ec86092a786
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c829ce496c124f3333c353f481eb3958e29d5c77
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996334"
---
# <a name="adapter-localization-issues"></a>适配器本地化问题
下列主题涉及您在开发自定义适配器时可能遇到的本地化问题。  
  
## <a name="xsd-issues"></a>XSD 问题  
 通过使用适配器框架，适配器开发人员可以实现具有 XML 架构定义 (XSD) 架构的适配器属性页。  
  
 如果您的适配器没有全球化或本地化的要求，则您可以将内部的 XSD 架构字符串硬编码 **: Getconfigschema**函数。  
  
 如果您的适配器具有全球化或本地化方面的要求，则可以采用以下两种方式之一实现 XSD 架构。  
  
- 在设计时二进制文件之外使用单独的 XSD 文件。 将架构的全部文本作为清单资源。  
  
- 动态替换资源中的属性名称和说明：  
  
  -   将 _locID 添加到要本地化的每个元素。  
  
  -   使用 xpath 拖回架构中具有 _locID 属性的所有节点。  
  
  -   在资源中查找使用 _locID 值作为索引的字符串。  
  
  -   用结果替换节点文本。  
  
  以下为第二个选项的示例代码：  
  
```  
string mySchema = GetSchemaFromResource(“mySchema”);  
string myLocalizedSchema = LocalizeSchemaDOM (mySchema, resourceManager);  
//  where…  
protected string GetSchemaFromResource (string name)  
{  
Assembly assem = this.GetType().Assembly;  
Stream stream = assem.GetManifestResourceStream(name);  
StreamReader reader = new StreamReader(stream);  
string schema = reader.ReadToEnd();  
return schema;  
}  
  
protected XmlDocument LocalizeSchemaDOM (string schema, ResourceManager resourceManager)  
{  
XmlDocument document = new XmlDocument();  
document.LoadXml(schema);  
XmlNodeList nodes = document.SelectNodes  
("/descendant::*[@_locID]");  
foreach (XmlNode node in nodes)  
{  
string locID = node.Attributes["_locID"].Value;  
node.InnerText = resourceManager.GetString(locID);  
}  
return document;  
}  
```