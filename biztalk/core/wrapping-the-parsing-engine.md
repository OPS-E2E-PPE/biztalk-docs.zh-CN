---
title: 包装解析引擎 |Microsoft Docs
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
ms.openlocfilehash: 7605c6d05e4e948a443025afe26429fd049bc469
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313256"
---
# <a name="wrapping-the-parsing-engine"></a><span data-ttu-id="bcf0b-102">包装解析引擎</span><span class="sxs-lookup"><span data-stu-id="bcf0b-102">Wrapping the Parsing Engine</span></span>
<span data-ttu-id="bcf0b-103">可以创建你自己**XmlReader**嵌入返回的读取器**分析**方法，并提供自定义项。</span><span class="sxs-lookup"><span data-stu-id="bcf0b-103">You can create your own **XmlReader** that embeds the reader returned by the **Parse** method and provides customization.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcf0b-104">示例</span><span class="sxs-lookup"><span data-stu-id="bcf0b-104">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bcf0b-105">请参阅</span><span class="sxs-lookup"><span data-stu-id="bcf0b-105">See Also</span></span>  
 [<span data-ttu-id="bcf0b-106">使用平面文件解析引擎</span><span class="sxs-lookup"><span data-stu-id="bcf0b-106">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)