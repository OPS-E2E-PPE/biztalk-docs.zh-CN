---
title: 如何使用表达式来动态转换消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48387d97-9312-4df5-b614-727ea9035bf8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 084d8144aae37f3036d17f574a7fb663755e0b26
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333468"
---
# <a name="how-to-use-expressions-to-dynamic-transform-messages"></a>如何使用表达式来动态转换消息
您可以在业务流程中使用表达式来动态转换消息。 XLANG 公开一个可从内部调用的转换方法**消息赋值**形状的内部**构造消息**形状。 这是相同时，将调用的方法**转换**形状，但允许您以编程方式转换消息使用您在业务流程内指定的映射。 执行类型未知的消息处理时，这是非常有用。 例如，如果需要从一系列映射中选择转换基于接收的入站消息所提供的参数的入站的消息的业务流程，您可以实现此目的通过在表达式形状中同时使用 transform 方法维护整体业务流程保持不变。  
  
## <a name="transforming-messages"></a>转换消息  
 可以使用下面的示例代码以编程方式转换中的消息**消息赋值**形状：  
  
```  
MyMapType = typeof(MyMapName);  
transform(MyOutputMsg) = MyMapType(MyInputMsg);  
```  
  
 在此示例中，MyMapType 声明为类型的变量**System.Type**业务流程中。 MyMapName 是已在 BizTalk 项目中创建映射的名称。 如果你想要引用位于单独的 BizTalk 程序集中某一映射，需要引用该程序集在 BizTalk 项目中。 MyInputMsg 是源消息，MyOutputMsg 是目标消息。 如果您的映射采用多个源消息，则可以使用下面的示例代码以转换消息：  
  
```  
MyMapType = typeof(MyMapName);  
transform(MyOutputMsg) = MyMapType(MyInputMsg1, MyInputMsg2);  
```  
  
> [!NOTE]
>  如果有多个源消息，必须将它们放在顺序中相对于在映射中指示的输入的消息部件号的表达式中。  
  
> [!IMPORTANT]
>  时动态转换消息在表达式形状中的，我们建议在用于缓存已编译的映射，用户代码中编写一个缓存，然后使用表达式形状中的缓存转换消息前检索这些映射。 如果您没有缓存映射，则可能会发现公共语言运行时 (CLR) 内存会显著增长。 动态映射要求.NET 运行时执行的代码访问检查，这会导致.NET Evidence 对象放置在每个转换大型对象堆和此对象未释放的直到在业务流程完成。 因此，当存在大量的这些类型的同时发生的转换时，可能会看到内存使用率显著增加，这也会导致内存不足异常。  
  
## <a name="see-also"></a>请参阅  
 [业务流程形状](../core/orchestration-shapes.md)   
 [使用 BizTalk 映射器创建映射](../core/creating-maps-using-biztalk-mapper.md)