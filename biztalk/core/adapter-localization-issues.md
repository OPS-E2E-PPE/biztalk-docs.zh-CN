---
title: 适配器本地化问题 |Microsoft 文档
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
ms.openlocfilehash: 8862318547f2a7b8b4fa5dc7291e1673f1b9ba29
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22229861"
---
# <a name="adapter-localization-issues"></a><span data-ttu-id="02dcb-102">适配器本地化问题</span><span class="sxs-lookup"><span data-stu-id="02dcb-102">Adapter Localization Issues</span></span>
<span data-ttu-id="02dcb-103">下列主题涉及您在开发自定义适配器时可能遇到的本地化问题。</span><span class="sxs-lookup"><span data-stu-id="02dcb-103">The following topics cover localization issues that you may encounter when developing custom adapters.</span></span>  
  
## <a name="xsd-issues"></a><span data-ttu-id="02dcb-104">XSD 问题</span><span class="sxs-lookup"><span data-stu-id="02dcb-104">XSD Issues</span></span>  
 <span data-ttu-id="02dcb-105">通过使用适配器框架，适配器开发人员可以实现具有 XML 架构定义 (XSD) 架构的适配器属性页。</span><span class="sxs-lookup"><span data-stu-id="02dcb-105">By using the Adapter Framework, adapter developers can implement adapter property pages with XML Schema Definition (XSD) schemas.</span></span>  
  
 <span data-ttu-id="02dcb-106">如果你的适配器具有没有全球化或本地化的要求，则你可以将硬编码内的 XSD 架构字符串**IDynamicAdapterConfig:GetConfigSchema**函数。</span><span class="sxs-lookup"><span data-stu-id="02dcb-106">If your adapter has no globalization or localization requirements, then you can hard code the XSD schema string inside the **IDynamicAdapterConfig:GetConfigSchema** function.</span></span>  
  
 <span data-ttu-id="02dcb-107">如果您的适配器具有全球化或本地化方面的要求，则可以采用以下两种方式之一实现 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="02dcb-107">If your adapter has globalization or localization requirements, you can implement the XSD schema in one of two ways.</span></span>  
  
-   <span data-ttu-id="02dcb-108">在设计时二进制文件之外使用单独的 XSD 文件。</span><span class="sxs-lookup"><span data-stu-id="02dcb-108">Use separate XSD files outside the design-time binary.</span></span> <span data-ttu-id="02dcb-109">将架构的全部文本作为清单资源。</span><span class="sxs-lookup"><span data-stu-id="02dcb-109">Make the whole text of the schema a manifest resource.</span></span>  
  
-   <span data-ttu-id="02dcb-110">动态替换资源中的属性名称和说明：</span><span class="sxs-lookup"><span data-stu-id="02dcb-110">Dynamically replace the Property Names and Description from the resource:</span></span>  
  
    -   <span data-ttu-id="02dcb-111">将 _locID 添加到要本地化的每个元素。</span><span class="sxs-lookup"><span data-stu-id="02dcb-111">Add a _locID to each element that you want to localize.</span></span>  
  
    -   <span data-ttu-id="02dcb-112">使用 xpath 拖回架构中具有 _locID 属性的所有节点。</span><span class="sxs-lookup"><span data-stu-id="02dcb-112">Use an xpath to pull back all the nodes in the schema that have a _locID attribute.</span></span>  
  
    -   <span data-ttu-id="02dcb-113">在资源中查找使用 _locID 值作为索引的字符串。</span><span class="sxs-lookup"><span data-stu-id="02dcb-113">Look up the resources for a string indexed by the value of the _locID.</span></span>  
  
    -   <span data-ttu-id="02dcb-114">用结果替换节点文本。</span><span class="sxs-lookup"><span data-stu-id="02dcb-114">Replace the node text with the result.</span></span>  
  
 <span data-ttu-id="02dcb-115">以下为第二个选项的示例代码：</span><span class="sxs-lookup"><span data-stu-id="02dcb-115">The following is sample code for the second option:</span></span>  
  
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