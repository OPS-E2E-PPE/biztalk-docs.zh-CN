---
title: 调用平面文件分析引擎 |Microsoft 文档
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
ms.assetid: 9c5d325e-2fae-4291-af13-3fb06657ec0e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90108ff2ade354c51f87499a388ae54135f14c7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261837"
---
# <a name="invoking-the-flat-file-parsing-engine"></a>调用分析引擎的平面文件
可以通过调用调用平面文件分析引擎**分析**方法**IFFDocumentSpec**接口，反过来转换从`IDocumentSpec Interface`从检索到**PipelineContext**。 因为**XmlReader**从返回**分析**方法允许客户端一次检索一个节点，这是自定义解析程序的最佳时机。  
  
## <a name="example"></a>示例  
  
```  
XmlReader xr = docspec.Parse(new DataReader());  
while (xr.Read())  
{  
   switch(xr.NodeType)  
   {  
      case XmlNodeType.Element :  
         // Customize the element  
         //   
         break;  
      case XmlNodeType.Attribute :  
         // Customize the attribute  
         //   
         break;  
      // Customize other types of nodes  
      //   
   }  
}  
```  
  
## <a name="see-also"></a>另请参阅  
 [使用平面文件分析引擎](../core/using-the-flat-file-parsing-engine.md)