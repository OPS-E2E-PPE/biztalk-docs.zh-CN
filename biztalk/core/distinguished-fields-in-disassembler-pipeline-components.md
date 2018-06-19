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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20a9c79050b4489238ed94444eaebf8c3dac79d9
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31008440"
---
# <a name="distinguished-fields-in-disassembler-pipeline-components"></a>反汇编程序中的可分辨的字段管道组件
通过 XML 拆装器管道组件、BizTalk 框架拆装器管道组件或平面文件拆装器管道组件，可将架构中定义的可分辨字段写入消息上下文中，格式如下：  
  
 *使用名称* 是 XPath 中的可分辨的字段  
  
 *命名空间 URI*是"http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields"  
  
 属性的值是 **System.String** 指定从 XML 文档使用提取的值的 XPath。  
  
 下面的示例架构具有可分辨字段 Price：  
  
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
  
 对于文档实例  
  
```  
<PO>  
            <Item>Bolt</Item>  
            <Price>10</Price>  
<PO>  
```  
  
 XML 拆装器在消息上下文中写入可分辨字段，如下如示：  
  
 在上下文的属性名称： `"/*[local-name()='PO' and namespace-uri()='http://SendHtmlMessage.PO']/\*[local-name()='Price' and namespace-uri()='']"`  
  
 属性的 Namespace: http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields  
  
 属性值︰ 10  
  
> [!NOTE]
>  如果任何 XML 文档元素值的大小超过 85 KB，则处理这些文档时性能可能会降低。  
  
## <a name="see-also"></a>另请参阅  
 [平面文件反汇编程序管道组件](../core/flat-file-disassembler-pipeline-component.md)   
 [如何配置平面文件反汇编程序管道组件](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)
