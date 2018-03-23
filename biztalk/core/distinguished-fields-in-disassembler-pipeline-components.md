---
title: 反汇编程序中的可分辨的字段管道组件 |Microsoft 文档
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64e4c8f15d167f5343089c11b92b0f373aa45576
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="distinguished-fields-in-disassembler-pipeline-components"></a><span data-ttu-id="fe8f2-102">反汇编程序中的可分辨的字段管道组件</span><span class="sxs-lookup"><span data-stu-id="fe8f2-102">Distinguished Fields in Disassembler Pipeline Components</span></span>
<span data-ttu-id="fe8f2-103">通过 XML 拆装器管道组件、BizTalk 框架拆装器管道组件或平面文件拆装器管道组件，可将架构中定义的可分辨字段写入消息上下文中，格式如下：</span><span class="sxs-lookup"><span data-stu-id="fe8f2-103">Distinguished fields defined in a schema are written to the message context by the XML Disassembler, BizTalk Framework Disassembler, or Flat File Disassembler pipeline components in the following format:</span></span>  
  
 <span data-ttu-id="fe8f2-104">*使用名称* 是 XPath 中的可分辨的字段</span><span class="sxs-lookup"><span data-stu-id="fe8f2-104">*name used* is the distinguished field in XPath</span></span>  
  
 <span data-ttu-id="fe8f2-105">*命名空间 URI*是"http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields"</span><span class="sxs-lookup"><span data-stu-id="fe8f2-105">*namespace URI* is "http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields"</span></span>  
  
 <span data-ttu-id="fe8f2-106">属性的值是 **System.String** 指定从 XML 文档使用提取的值的 XPath。</span><span class="sxs-lookup"><span data-stu-id="fe8f2-106">The value of the property is the **System.String** value extracted from the XML document using specified XPath.</span></span>  
  
 <span data-ttu-id="fe8f2-107">下面的示例架构具有可分辨字段 Price：</span><span class="sxs-lookup"><span data-stu-id="fe8f2-107">The following example schema has a distinguished field Price.</span></span>  
  
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
  
 <span data-ttu-id="fe8f2-108">对于文档实例</span><span class="sxs-lookup"><span data-stu-id="fe8f2-108">For the document instance</span></span>  
  
```  
<PO>  
            <Item>Bolt</Item>  
            <Price>10</Price>  
<PO>  
```  
  
 <span data-ttu-id="fe8f2-109">XML 拆装器在消息上下文中写入可分辨字段，如下如示：</span><span class="sxs-lookup"><span data-stu-id="fe8f2-109">the XML Disassembler writes a distinguished field on a message context as follows:</span></span>  
  
 <span data-ttu-id="fe8f2-110">在上下文的属性名称:"/ * [本地名称 （) = PO 和 namespace-uri() =http://SendHtmlMessage.PO'] /\*[本地名称 （) = 价格和 namespace-uri() =']"</span><span class="sxs-lookup"><span data-stu-id="fe8f2-110">Name of the property on the context: "/*[local-name()='PO' and namespace-uri()='http://SendHtmlMessage.PO']/\*[local-name()='Price' and namespace-uri()='']"</span></span>  
  
 <span data-ttu-id="fe8f2-111">属性的 Namespace: http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields</span><span class="sxs-lookup"><span data-stu-id="fe8f2-111">Namespace of the property: http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields</span></span>  
  
 <span data-ttu-id="fe8f2-112">属性值︰ 10</span><span class="sxs-lookup"><span data-stu-id="fe8f2-112">Value of the property: 10</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe8f2-113">如果任何 XML 文档元素值的大小超过 85 KB，则处理这些文档时性能可能会降低。</span><span class="sxs-lookup"><span data-stu-id="fe8f2-113">If the size of any XML document element values exceeds 85KB, a degradation in the performance of processing those documents may occur.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe8f2-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe8f2-114">See Also</span></span>  
 <span data-ttu-id="fe8f2-115">[平面文件反汇编程序管道组件](../core/flat-file-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="fe8f2-115">[Flat File Disassembler Pipeline Component](../core/flat-file-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="fe8f2-116">如何配置平面文件反汇编程序管道组件</span><span class="sxs-lookup"><span data-stu-id="fe8f2-116">How to Configure the Flat File Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)