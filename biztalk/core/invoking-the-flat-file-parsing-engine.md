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
# <a name="invoking-the-flat-file-parsing-engine"></a><span data-ttu-id="5d8df-102">调用分析引擎的平面文件</span><span class="sxs-lookup"><span data-stu-id="5d8df-102">Invoking the Flat File Parsing Engine</span></span>
<span data-ttu-id="5d8df-103">可以通过调用调用平面文件分析引擎**分析**方法**IFFDocumentSpec**接口，反过来转换从`IDocumentSpec Interface`从检索到**PipelineContext**。</span><span class="sxs-lookup"><span data-stu-id="5d8df-103">The flat file parsing engine can be invoked by calling the **Parse** method of the **IFFDocumentSpec** interface, which in turn is typecast from the `IDocumentSpec Interface` retrieved from the **PipelineContext**.</span></span> <span data-ttu-id="5d8df-104">因为**XmlReader**从返回**分析**方法允许客户端一次检索一个节点，这是自定义解析程序的最佳时机。</span><span class="sxs-lookup"><span data-stu-id="5d8df-104">Because the **XmlReader** returned from the **Parse** method allows clients to retrieve one node at a time, this is a good opportunity to customize the parser.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d8df-105">示例</span><span class="sxs-lookup"><span data-stu-id="5d8df-105">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5d8df-106">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d8df-106">See Also</span></span>  
 [<span data-ttu-id="5d8df-107">使用平面文件分析引擎</span><span class="sxs-lookup"><span data-stu-id="5d8df-107">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)