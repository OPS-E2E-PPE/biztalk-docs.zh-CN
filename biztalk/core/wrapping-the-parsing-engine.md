---
title: 包装分析引擎 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], wrapping
- pipeline components [custom], code samples
ms.assetid: e00994de-bb86-40c0-a891-3f202147b5fe
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99d6960ba2f5f795a37bb336dab227f23eb12353
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288589"
---
# <a name="wrapping-the-parsing-engine"></a>包装分析引擎
你可以创建自己**XmlReader**嵌入返回的读取器**分析**方法并提供自定义项。  
  
## <a name="example"></a>示例  
  
```  
class MyXmlReader : XmlReader  
{  
   public MyXmlReader(XmlReader xr)  
   {  
      _xr = xr;  
   }  
  
   // Overrides XmlReader and provides customized functionality of _xr  
   // ...  
}  
```  
  
## <a name="see-also"></a>另请参阅  
 [使用平面文件分析引擎](../core/using-the-flat-file-parsing-engine.md)