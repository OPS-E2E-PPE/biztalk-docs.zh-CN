---
title: "如何使用动态转换消息的表达式 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48387d97-9312-4df5-b614-727ea9035bf8
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b9d16c38fefb4e2732bd05f7c3489acaa8ca645
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-expressions-to-dynamic-transform-messages"></a>如何使用动态转换消息的表达式
可以在业务流程中使用表达式来动态转换消息。 XLANG 公开的转换方法，可以从调用**消息分配**形状内**构造消息**形状。 这是时，将调用的相同方法**转换**形状会使用，但是，可以以编程方式将转换使用业务流程中指定映射的消息。 在您执行与类型无关的消息处理时该方法会很有用。 例如，如果您具有需要从一系列映射中选择的业务流程，以便基于接收的入站消息提供的参数转换入站消息，则可以通过在表达式形状中使用该转换方法实现此要求，同时保持整体业务流程的完整性。  
  
## <a name="transforming-messages"></a>转换消息  
 你可以使用下面的示例代码要以编程方式转换中的消息**消息分配**形状：  
  
```  
MyMapType = typeof(MyMapName);  
transform(MyOutputMsg) = MyMapType(MyInputMsg);  
```  
  
 在此示例中，MyMapType 声明为类型的变量的**System.Type**业务流程中。 MyMapName 是已在您的 BizTalk 项目中创建的映射的名称。 如果您要在单独的 BizTalk 程序集中引用某一映射，将需要在您的 BizTalk 项目中引用该程序集。 MyInputMsg 是源消息，MyOutputMsg 是目标消息。 如果您的映射采用多个源消息，则可以使用以下代码示例来转换这些消息：  
  
```  
MyMapType = typeof(MyMapName);  
transform(MyOutputMsg) = MyMapType(MyInputMsg1, MyInputMsg2);  
```  
  
> [!NOTE]
>  如果您具有多个源消息，则必须根据在映射中指示的输入消息部分号在表达式中有序放置它们。  
  
> [!IMPORTANT]
>  在表达式形状中动态转换消息时，建议您在用户代码中编写一个缓存，以便缓存已编译的映射，然后在表达式形状中使用该缓存来在转换消息前检索这些映射。 如果您没有缓存映射，则可能会发现公共语言运行库 (CLR) 内存会显著增长。 动态映射要求 .NET 运行库执行代码访问检查，该检查将导致 .NET Evidence 对象放置于每个转换的大对象堆中，并且在业务流程完成前不处置此对象。 因此，当同时发生许多上述类型的转换时，您可能会看到内存使用率显著增加，从而还可能导致内存不足异常。  
  
## <a name="see-also"></a>另请参阅  
 [业务流程形状](../core/orchestration-shapes.md)   
 [创建使用 BizTalk 映射程序图](../core/creating-maps-using-biztalk-mapper.md)