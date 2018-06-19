---
title: 使用架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- pipeline components [custom], code samples
- pipeline components [custom], schemas
ms.assetid: 07e60532-1032-422d-865e-0bd65c45dab6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a7cb71319fef61d3b6cb854b04b41e3815a6129
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287237"
---
# <a name="using-schemas"></a>使用架构
本部分包含的代码示例的与使用架构相关联的常见任务。  
  
## <a name="using-xsd-schemas"></a>使用 XSD 架构  
 `IDocumentSpec Interface`接口表示一个文档形状定义 XML 架构定义语言 (XSD) 架构; 形状已取得 root 权限通过 XSD 的顶级元素。 它通过调用安装架构后，可以进行检索`IPipelineContext.GetDocumentSpecByType Method`或`IPipelineContext.GetDocumentSpecByName Method`中的方法**IPipelineContext**接口。  
  
```  
IDocumentSpec docspec = pipeineContext.GetDocumentSpecByType("myschema#root");  
```  
  
## <a name="using-xsd-flat-file-schemas"></a>使用 XSD 平面文件架构  
 这两个**GetDocumentSpecByType**和**GetDocumentSpecByName**方法返回**IDocumentSpec**接口。 如果架构，则实际的平面文件架构 （一个包含其他平面文件特定批注），可以转换**IDocumentSpec**到**IFFDocumentSpec**并启动分析和序列化从该处的序列。  
  
```  
IFFDocumentSpec docspec = (IFFDocumentSpec) pipeineContext.GetDocumentSpecByType("myschema#root");  
```  
  
## <a name="see-also"></a>另请参阅  

[使用了分析和序列化引擎](../core/using-the-parsing-and-serializing-engines.md)