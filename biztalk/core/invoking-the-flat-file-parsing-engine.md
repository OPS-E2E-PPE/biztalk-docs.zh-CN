---
title: 调用平面文件解析引擎 |Microsoft Docs
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
ms.openlocfilehash: 66142e4d70f317d0baeba75cae6b1f1bcb528140
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380854"
---
# <a name="invoking-the-flat-file-parsing-engine"></a><span data-ttu-id="14673-102">调用平面文件解析引擎</span><span class="sxs-lookup"><span data-stu-id="14673-102">Invoking the Flat File Parsing Engine</span></span>
<span data-ttu-id="14673-103">可以通过调用来调用平面文件解析引擎**分析**方法**IFFDocumentSpec**接口，在进行类型转换`IDocumentSpec Interface`从检索**PipelineContext**。</span><span class="sxs-lookup"><span data-stu-id="14673-103">The flat file parsing engine can be invoked by calling the **Parse** method of the **IFFDocumentSpec** interface, which in turn is typecast from the `IDocumentSpec Interface` retrieved from the **PipelineContext**.</span></span> <span data-ttu-id="14673-104">因为**XmlReader**返回从**分析**方法允许客户端一次检索一个节点，这是一个很好的机会，以自定义分析器。</span><span class="sxs-lookup"><span data-stu-id="14673-104">Because the **XmlReader** returned from the **Parse** method allows clients to retrieve one node at a time, this is a good opportunity to customize the parser.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14673-105">示例</span><span class="sxs-lookup"><span data-stu-id="14673-105">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="14673-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="14673-106">See Also</span></span>  
 [<span data-ttu-id="14673-107">使用平面文件解析引擎</span><span class="sxs-lookup"><span data-stu-id="14673-107">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)