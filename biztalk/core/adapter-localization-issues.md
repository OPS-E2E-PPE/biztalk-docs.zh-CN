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
ms.openlocfilehash: d5ebd852d51671d0b3b2312db74433f0af10a974
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361398"
---
# <a name="adapter-localization-issues"></a>适配器本地化问题
以下主题介绍了开发自定义适配器时可能遇到的本地化问题。  
  
## <a name="xsd-issues"></a>XSD 问题  
 通过使用适配器框架，适配器开发人员可以实现与 XML 架构定义 (XSD) 架构的适配器属性页。  
  
 如果您的适配器没有全球化或本地化的要求，则您可以将内部的 XSD 架构字符串硬编码 **: Getconfigschema**函数。  
  
 如果您的适配器具有全球化或本地化的要求，可以按两种方式之一实现 XSD 架构。  
  
- 使用设计时二进制文件之外的单独 XSD 文件。 请在架构的整个文本清单资源。  
  
- 动态资源从替换属性名称和说明：  
  
  -   将 _locID 添加到要本地化的每个元素。  
  
  -   使用 xpath 拖回架构中具有 _locID 属性的所有节点。  
  
  -   查找使用 _locID 值索引的字符串的资源。  
  
  -   用结果替换节点文本。  
  
  以下是第二个选项的示例代码：  
  
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