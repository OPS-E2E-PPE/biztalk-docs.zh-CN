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
# <a name="using-the-flat-file-serializing-engine"></a>使用平面文件序列化引擎
通过调用来调用平面文件序列化引擎**Serialize**方法**IFFDocumentSpec**接口。 通过提供自定义**XmlReader**作为方法自变量，您可以控制最终获取序列化的数据。 数据可能是任何格式，或可能只创建读取器的关闭 XmlDocument。  
  
## <a name="example"></a>示例  
  
```  
Stream stm = docspec.Serialize(new MyXmlReader(originalXmlReader), Encoding.Unicode);  
```  
  
## <a name="see-also"></a>请参阅  
 [Microsoft.BizTalk.Component.Interop.IFFDocumentSpec](http://msdn.microsoft.com/library/microsoft.biztalk.component.interop.iffdocumentspec.aspx)   
 [使用平面文件解析引擎](../core/using-the-flat-file-parsing-engine.md)