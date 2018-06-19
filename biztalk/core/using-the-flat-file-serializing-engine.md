---
title: 使用平面文件序列化引擎 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], code samples
- IFFDocumentSpec interface
- pipeline components [custom], flat file documents
- pipeline components [custom], engines
ms.assetid: 0a519f0f-392b-4fa3-ab08-f09012d033af
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb4f39f42c3513932b54a92946e448d821ee362a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287565"
---
# <a name="using-the-flat-file-serializing-engine"></a>使用序列化引擎的平面文件
通过调用调用序列化引擎的平面文件**序列化**方法**IFFDocumentSpec**接口。 通过提供自定义**XmlReader**作为方法自变量，您可以控制最后获取序列化的数据。 数据可能采用何种格式，或无法只需将创建的读取器的关闭 XmlDocument。  
  
## <a name="example"></a>示例  
  
```  
Stream stm = docspec.Serialize(new MyXmlReader(originalXmlReader), Encoding.Unicode);  
```  
  
## <a name="see-also"></a>另请参阅  
 [Microsoft.BizTalk.Component.Interop.IFFDocumentSpec](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.iffdocumentspec.aspx)   
 [使用平面文件分析引擎](../core/using-the-flat-file-parsing-engine.md)