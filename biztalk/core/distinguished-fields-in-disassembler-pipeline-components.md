---
title: 可分辨的字段在拆装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, distinquished fields
- Flat File Disassembler [pipeline component], distinquished fields
- BizTalk Framework Disassembler [pipeline component], distinquished fields
- XML Disassembler [pipeline component], distinquished fields
ms.assetid: 7e51d2fe-0004-4a7b-9055-bd41e8a4b7ab
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63f3fd2dd8948e880af7b2135e8b4fef64f1b39d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389357"
---
# <a name="distinguished-fields-in-disassembler-pipeline-components"></a><span data-ttu-id="325f7-102">可分辨的字段在拆装器管道组件</span><span class="sxs-lookup"><span data-stu-id="325f7-102">Distinguished Fields in Disassembler Pipeline Components</span></span>
<span data-ttu-id="325f7-103">在架构中定义的可分辨的字段写入消息上下文由 XML 拆装器、 BizTalk 框架拆装器或采用以下格式的平面文件拆装器管道组件：</span><span class="sxs-lookup"><span data-stu-id="325f7-103">Distinguished fields defined in a schema are written to the message context by the XML Disassembler, BizTalk Framework Disassembler, or Flat File Disassembler pipeline components in the following format:</span></span>  
  
 <span data-ttu-id="325f7-104">*使用名称*是 XPath 中的可分辨的字段</span><span class="sxs-lookup"><span data-stu-id="325f7-104">*name used* is the distinguished field in XPath</span></span>  
  
 <span data-ttu-id="325f7-105">*命名空间 URI*是"<http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields>"</span><span class="sxs-lookup"><span data-stu-id="325f7-105">*namespace URI* is "<http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields>"</span></span>  
  
 <span data-ttu-id="325f7-106">属性的值是**System.String**指定从 XML 文档使用提取的值的 XPath。</span><span class="sxs-lookup"><span data-stu-id="325f7-106">The value of the property is the **System.String** value extracted from the XML document using specified XPath.</span></span>  
  
 <span data-ttu-id="325f7-107">下面的示例架构具有可分辨的字段 Price。</span><span class="sxs-lookup"><span data-stu-id="325f7-107">The following example schema has a distinguished field Price.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16" ?>   
<xs:schema xmlns="http://SendHtmlMessage.PO" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" targetNamespace="http://SendHtmlMessage.PO xmlns:xs="http://www.w3.org/2001/XMLSchema">  
   <xs:element name="PO">  
      <xs:annotation>  
         <xs:appinfo>  
            <b:properties>  
               <b:property distinguished="true" xpath="/*[local-name()='PO' and namespace-uri()='http://SendHtmlMessage.PO']/*[local-  
               name()='Price' and namespace-uri()='']" />   
            </b:properties>  
         </xs:appinfo>  
      </xs:annotation>  
      <xs:complexType>  
         <xs:sequence>  
            <xs:element name="Item" type="xs:string" />   
            <xs:element name="Price" type="xs:string" />   
         </xs:sequence>  
      </xs:complexType>  
   </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="325f7-108">对于文档实例</span><span class="sxs-lookup"><span data-stu-id="325f7-108">For the document instance</span></span>  
  
```  
<PO>  
            <Item>Bolt</Item>  
            <Price>10</Price>  
<PO>  
```  
  
 <span data-ttu-id="325f7-109">XML 拆装器按如下所示将可分辨的字段写入消息上下文：</span><span class="sxs-lookup"><span data-stu-id="325f7-109">the XML Disassembler writes a distinguished field on a message context as follows:</span></span>  
  
 <span data-ttu-id="325f7-110">在上下文属性的名称： `"/*[local-name()='PO' and namespace-uri()='http://SendHtmlMessage.PO']/\*[local-name()='Price' and namespace-uri()='']"`</span><span class="sxs-lookup"><span data-stu-id="325f7-110">Name of the property on the context: `"/*[local-name()='PO' and namespace-uri()='http://SendHtmlMessage.PO']/\*[local-name()='Price' and namespace-uri()='']"`</span></span>  
  
 <span data-ttu-id="325f7-111">属性的 Namespace: http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields</span><span class="sxs-lookup"><span data-stu-id="325f7-111">Namespace of the property: http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields</span></span>  
  
 <span data-ttu-id="325f7-112">属性的值：10</span><span class="sxs-lookup"><span data-stu-id="325f7-112">Value of the property: 10</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="325f7-113">如果任何 XML 文档元素值的大小超过 85 KB，处理这些文档的性能下降可能会发生。</span><span class="sxs-lookup"><span data-stu-id="325f7-113">If the size of any XML document element values exceeds 85KB, a degradation in the performance of processing those documents may occur.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="325f7-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="325f7-114">See Also</span></span>  
 <span data-ttu-id="325f7-115">[平面文件拆装器管道组件](../core/flat-file-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="325f7-115">[Flat File Disassembler Pipeline Component](../core/flat-file-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="325f7-116">如何配置平面文件拆装器管道组件</span><span class="sxs-lookup"><span data-stu-id="325f7-116">How to Configure the Flat File Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)
