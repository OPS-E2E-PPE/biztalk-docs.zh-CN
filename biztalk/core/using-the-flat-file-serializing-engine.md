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
# <a name="using-the-flat-file-serializing-engine"></a><span data-ttu-id="f76b1-102">使用序列化引擎的平面文件</span><span class="sxs-lookup"><span data-stu-id="f76b1-102">Using the Flat File Serializing Engine</span></span>
<span data-ttu-id="f76b1-103">通过调用调用序列化引擎的平面文件**序列化**方法**IFFDocumentSpec**接口。</span><span class="sxs-lookup"><span data-stu-id="f76b1-103">The flat file serializing engine is invoked by calling the **Serialize** method of the **IFFDocumentSpec** interface.</span></span> <span data-ttu-id="f76b1-104">通过提供自定义**XmlReader**作为方法自变量，您可以控制最后获取序列化的数据。</span><span class="sxs-lookup"><span data-stu-id="f76b1-104">By providing a customized **XmlReader** as the argument to the method, you can control the final data that gets serialized.</span></span> <span data-ttu-id="f76b1-105">数据可能采用何种格式，或无法只需将创建的读取器的关闭 XmlDocument。</span><span class="sxs-lookup"><span data-stu-id="f76b1-105">Data could be in any format, or could simply be a reader created of off an XmlDocument.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f76b1-106">示例</span><span class="sxs-lookup"><span data-stu-id="f76b1-106">Example</span></span>  
  
```  
Stream stm = docspec.Serialize(new MyXmlReader(originalXmlReader), Encoding.Unicode);  
```  
  
## <a name="see-also"></a><span data-ttu-id="f76b1-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f76b1-107">See Also</span></span>  
 <span data-ttu-id="f76b1-108">[Microsoft.BizTalk.Component.Interop.IFFDocumentSpec](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.iffdocumentspec.aspx) </span><span class="sxs-lookup"><span data-stu-id="f76b1-108">[Microsoft.BizTalk.Component.Interop.IFFDocumentSpec](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.iffdocumentspec.aspx) </span></span>  
 [<span data-ttu-id="f76b1-109">使用平面文件分析引擎</span><span class="sxs-lookup"><span data-stu-id="f76b1-109">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)