---
title: 使用平面文件序列化引擎 |Microsoft Docs
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
ms.openlocfilehash: d9a854a440dda25c822b923f7ca17ef8e80ccc34
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396031"
---
# <a name="using-the-flat-file-serializing-engine"></a><span data-ttu-id="96793-102">使用平面文件序列化引擎</span><span class="sxs-lookup"><span data-stu-id="96793-102">Using the Flat File Serializing Engine</span></span>
<span data-ttu-id="96793-103">通过调用来调用平面文件序列化引擎**Serialize**方法**IFFDocumentSpec**接口。</span><span class="sxs-lookup"><span data-stu-id="96793-103">The flat file serializing engine is invoked by calling the **Serialize** method of the **IFFDocumentSpec** interface.</span></span> <span data-ttu-id="96793-104">通过提供自定义**XmlReader**作为方法自变量，您可以控制最终获取序列化的数据。</span><span class="sxs-lookup"><span data-stu-id="96793-104">By providing a customized **XmlReader** as the argument to the method, you can control the final data that gets serialized.</span></span> <span data-ttu-id="96793-105">数据可能是任何格式，或可能只创建读取器的关闭 XmlDocument。</span><span class="sxs-lookup"><span data-stu-id="96793-105">Data could be in any format, or could simply be a reader created of off an XmlDocument.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96793-106">示例</span><span class="sxs-lookup"><span data-stu-id="96793-106">Example</span></span>  
  
```  
Stream stm = docspec.Serialize(new MyXmlReader(originalXmlReader), Encoding.Unicode);  
```  
  
## <a name="see-also"></a><span data-ttu-id="96793-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="96793-107">See Also</span></span>  
 <span data-ttu-id="96793-108">[Microsoft.BizTalk.Component.Interop.IFFDocumentSpec](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.iffdocumentspec.aspx) </span><span class="sxs-lookup"><span data-stu-id="96793-108">[Microsoft.BizTalk.Component.Interop.IFFDocumentSpec](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.iffdocumentspec.aspx) </span></span>  
 [<span data-ttu-id="96793-109">使用平面文件解析引擎</span><span class="sxs-lookup"><span data-stu-id="96793-109">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)