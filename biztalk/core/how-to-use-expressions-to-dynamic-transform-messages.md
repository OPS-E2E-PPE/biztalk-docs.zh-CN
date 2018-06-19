---
title: 如何使用动态转换消息的表达式 |Microsoft 文档
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
ms.openlocfilehash: 4b9d16c38fefb4e2732bd05f7c3489acaa8ca645
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256933"
---
# <a name="how-to-use-expressions-to-dynamic-transform-messages"></a><span data-ttu-id="6ae18-102">如何使用动态转换消息的表达式</span><span class="sxs-lookup"><span data-stu-id="6ae18-102">How to Use Expressions to Dynamic Transform Messages</span></span>
<span data-ttu-id="6ae18-103">可以在业务流程中使用表达式来动态转换消息。</span><span class="sxs-lookup"><span data-stu-id="6ae18-103">You can use expressions to dynamic transform messages in your orchestration.</span></span> <span data-ttu-id="6ae18-104">XLANG 公开的转换方法，可以从调用**消息分配**形状内**构造消息**形状。</span><span class="sxs-lookup"><span data-stu-id="6ae18-104">XLANG exposes a transform method that can be called from within a **Message Assignment** shape inside of a **Construct Message** shape.</span></span> <span data-ttu-id="6ae18-105">这是时，将调用的相同方法**转换**形状会使用，但是，可以以编程方式将转换使用业务流程中指定映射的消息。</span><span class="sxs-lookup"><span data-stu-id="6ae18-105">This is the same method that is called when a **Transform** shape is used, but allows you to programmatically transform the messages using the map you designated within the orchestration.</span></span> <span data-ttu-id="6ae18-106">在您执行与类型无关的消息处理时该方法会很有用。</span><span class="sxs-lookup"><span data-stu-id="6ae18-106">This is useful when you are doing type-agnostic message processing.</span></span> <span data-ttu-id="6ae18-107">例如，如果您具有需要从一系列映射中选择的业务流程，以便基于接收的入站消息提供的参数转换入站消息，则可以通过在表达式形状中使用该转换方法实现此要求，同时保持整体业务流程的完整性。</span><span class="sxs-lookup"><span data-stu-id="6ae18-107">For example, if you have a business process that needs to choose from a series of maps to transform inbound messages based on the parameters provided by the received inbound messages, you can achieve this by using the transform method in the Expression shape while maintaining your overall business process intact.</span></span>  
  
## <a name="transforming-messages"></a><span data-ttu-id="6ae18-108">转换消息</span><span class="sxs-lookup"><span data-stu-id="6ae18-108">Transforming messages</span></span>  
 <span data-ttu-id="6ae18-109">你可以使用下面的示例代码要以编程方式转换中的消息**消息分配**形状：</span><span class="sxs-lookup"><span data-stu-id="6ae18-109">You can use the following sample code to programmatically transform the messages in the **Message Assignment** shape:</span></span>  
  
```  
MyMapType = typeof(MyMapName);  
transform(MyOutputMsg) = MyMapType(MyInputMsg);  
```  
  
 <span data-ttu-id="6ae18-110">在此示例中，MyMapType 声明为类型的变量的**System.Type**业务流程中。</span><span class="sxs-lookup"><span data-stu-id="6ae18-110">In this example, MyMapType is declared as a variable of type **System.Type** in the orchestration.</span></span> <span data-ttu-id="6ae18-111">MyMapName 是已在您的 BizTalk 项目中创建的映射的名称。</span><span class="sxs-lookup"><span data-stu-id="6ae18-111">MyMapName is the name of a map that was already created in your BizTalk project.</span></span> <span data-ttu-id="6ae18-112">如果您要在单独的 BizTalk 程序集中引用某一映射，将需要在您的 BizTalk 项目中引用该程序集。</span><span class="sxs-lookup"><span data-stu-id="6ae18-112">If you would like to reference a map that is in a separate BizTalk assembly, you will need to reference that assembly in your BizTalk project.</span></span> <span data-ttu-id="6ae18-113">MyInputMsg 是源消息，MyOutputMsg 是目标消息。</span><span class="sxs-lookup"><span data-stu-id="6ae18-113">MyInputMsg is the source message and MyOutputMsg is the destination message.</span></span> <span data-ttu-id="6ae18-114">如果您的映射采用多个源消息，则可以使用以下代码示例来转换这些消息：</span><span class="sxs-lookup"><span data-stu-id="6ae18-114">If your map takes multiple source messages, then you can use the following sample code to transform the messages:</span></span>  
  
```  
MyMapType = typeof(MyMapName);  
transform(MyOutputMsg) = MyMapType(MyInputMsg1, MyInputMsg2);  
```  
  
> [!NOTE]
>  <span data-ttu-id="6ae18-115">如果您具有多个源消息，则必须根据在映射中指示的输入消息部分号在表达式中有序放置它们。</span><span class="sxs-lookup"><span data-stu-id="6ae18-115">If you have multiple source messages, they must be placed in order in the expression with respect to the input message part number indicated in the map.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6ae18-116">在表达式形状中动态转换消息时，建议您在用户代码中编写一个缓存，以便缓存已编译的映射，然后在表达式形状中使用该缓存来在转换消息前检索这些映射。</span><span class="sxs-lookup"><span data-stu-id="6ae18-116">When dynamic transforming messages in the Expression shape, we recommend that you write a cache in user code for caching the compiled maps, and then use the cache in the Expression shape to retrieve the maps before performing the message transformation.</span></span> <span data-ttu-id="6ae18-117">如果您没有缓存映射，则可能会发现公共语言运行库 (CLR) 内存会显著增长。</span><span class="sxs-lookup"><span data-stu-id="6ae18-117">If you are not caching the maps, it is possible to see Common Language Runtime (CLR) memory grow significantly.</span></span> <span data-ttu-id="6ae18-118">动态映射要求 .NET 运行库执行代码访问检查，该检查将导致 .NET Evidence 对象放置于每个转换的大对象堆中，并且在业务流程完成前不处置此对象。</span><span class="sxs-lookup"><span data-stu-id="6ae18-118">Dynamic mapping requires that the .NET Runtime perform code access check which results in a .NET Evidence object being placed in the Large Object Heap for each transformation and this object is not disposed of until the orchestration completes.</span></span> <span data-ttu-id="6ae18-119">因此，当同时发生许多上述类型的转换时，您可能会看到内存使用率显著增加，从而还可能导致内存不足异常。</span><span class="sxs-lookup"><span data-stu-id="6ae18-119">Therefore, when there are a lot of these types of transforms occurring simultaneously, you may see the memory usage increase substantially which can also lead to the out of memory exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ae18-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ae18-120">See Also</span></span>  
 <span data-ttu-id="6ae18-121">[业务流程形状](../core/orchestration-shapes.md) </span><span class="sxs-lookup"><span data-stu-id="6ae18-121">[Orchestration Shapes](../core/orchestration-shapes.md) </span></span>  
 [<span data-ttu-id="6ae18-122">创建使用 BizTalk 映射程序图</span><span class="sxs-lookup"><span data-stu-id="6ae18-122">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)