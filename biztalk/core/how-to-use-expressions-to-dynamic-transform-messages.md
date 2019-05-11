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
# <a name="how-to-use-expressions-to-dynamic-transform-messages"></a><span data-ttu-id="f0e10-102">如何使用表达式来动态转换消息</span><span class="sxs-lookup"><span data-stu-id="f0e10-102">How to Use Expressions to Dynamic Transform Messages</span></span>
<span data-ttu-id="f0e10-103">您可以在业务流程中使用表达式来动态转换消息。</span><span class="sxs-lookup"><span data-stu-id="f0e10-103">You can use expressions to dynamic transform messages in your orchestration.</span></span> <span data-ttu-id="f0e10-104">XLANG 公开一个可从内部调用的转换方法**消息赋值**形状的内部**构造消息**形状。</span><span class="sxs-lookup"><span data-stu-id="f0e10-104">XLANG exposes a transform method that can be called from within a **Message Assignment** shape inside of a **Construct Message** shape.</span></span> <span data-ttu-id="f0e10-105">这是相同时，将调用的方法**转换**形状，但允许您以编程方式转换消息使用您在业务流程内指定的映射。</span><span class="sxs-lookup"><span data-stu-id="f0e10-105">This is the same method that is called when a **Transform** shape is used, but allows you to programmatically transform the messages using the map you designated within the orchestration.</span></span> <span data-ttu-id="f0e10-106">执行类型未知的消息处理时，这是非常有用。</span><span class="sxs-lookup"><span data-stu-id="f0e10-106">This is useful when you are doing type-agnostic message processing.</span></span> <span data-ttu-id="f0e10-107">例如，如果需要从一系列映射中选择转换基于接收的入站消息所提供的参数的入站的消息的业务流程，您可以实现此目的通过在表达式形状中同时使用 transform 方法维护整体业务流程保持不变。</span><span class="sxs-lookup"><span data-stu-id="f0e10-107">For example, if you have a business process that needs to choose from a series of maps to transform inbound messages based on the parameters provided by the received inbound messages, you can achieve this by using the transform method in the Expression shape while maintaining your overall business process intact.</span></span>  
  
## <a name="transforming-messages"></a><span data-ttu-id="f0e10-108">转换消息</span><span class="sxs-lookup"><span data-stu-id="f0e10-108">Transforming messages</span></span>  
 <span data-ttu-id="f0e10-109">可以使用下面的示例代码以编程方式转换中的消息**消息赋值**形状：</span><span class="sxs-lookup"><span data-stu-id="f0e10-109">You can use the following sample code to programmatically transform the messages in the **Message Assignment** shape:</span></span>  
  
```  
MyMapType = typeof(MyMapName);  
transform(MyOutputMsg) = MyMapType(MyInputMsg);  
```  
  
 <span data-ttu-id="f0e10-110">在此示例中，MyMapType 声明为类型的变量**System.Type**业务流程中。</span><span class="sxs-lookup"><span data-stu-id="f0e10-110">In this example, MyMapType is declared as a variable of type **System.Type** in the orchestration.</span></span> <span data-ttu-id="f0e10-111">MyMapName 是已在 BizTalk 项目中创建映射的名称。</span><span class="sxs-lookup"><span data-stu-id="f0e10-111">MyMapName is the name of a map that was already created in your BizTalk project.</span></span> <span data-ttu-id="f0e10-112">如果你想要引用位于单独的 BizTalk 程序集中某一映射，需要引用该程序集在 BizTalk 项目中。</span><span class="sxs-lookup"><span data-stu-id="f0e10-112">If you would like to reference a map that is in a separate BizTalk assembly, you will need to reference that assembly in your BizTalk project.</span></span> <span data-ttu-id="f0e10-113">MyInputMsg 是源消息，MyOutputMsg 是目标消息。</span><span class="sxs-lookup"><span data-stu-id="f0e10-113">MyInputMsg is the source message and MyOutputMsg is the destination message.</span></span> <span data-ttu-id="f0e10-114">如果您的映射采用多个源消息，则可以使用下面的示例代码以转换消息：</span><span class="sxs-lookup"><span data-stu-id="f0e10-114">If your map takes multiple source messages, then you can use the following sample code to transform the messages:</span></span>  
  
```  
MyMapType = typeof(MyMapName);  
transform(MyOutputMsg) = MyMapType(MyInputMsg1, MyInputMsg2);  
```  
  
> [!NOTE]
>  <span data-ttu-id="f0e10-115">如果有多个源消息，必须将它们放在顺序中相对于在映射中指示的输入的消息部件号的表达式中。</span><span class="sxs-lookup"><span data-stu-id="f0e10-115">If you have multiple source messages, they must be placed in order in the expression with respect to the input message part number indicated in the map.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f0e10-116">时动态转换消息在表达式形状中的，我们建议在用于缓存已编译的映射，用户代码中编写一个缓存，然后使用表达式形状中的缓存转换消息前检索这些映射。</span><span class="sxs-lookup"><span data-stu-id="f0e10-116">When dynamic transforming messages in the Expression shape, we recommend that you write a cache in user code for caching the compiled maps, and then use the cache in the Expression shape to retrieve the maps before performing the message transformation.</span></span> <span data-ttu-id="f0e10-117">如果您没有缓存映射，则可能会发现公共语言运行时 (CLR) 内存会显著增长。</span><span class="sxs-lookup"><span data-stu-id="f0e10-117">If you are not caching the maps, it is possible to see Common Language Runtime (CLR) memory grow significantly.</span></span> <span data-ttu-id="f0e10-118">动态映射要求.NET 运行时执行的代码访问检查，这会导致.NET Evidence 对象放置在每个转换大型对象堆和此对象未释放的直到在业务流程完成。</span><span class="sxs-lookup"><span data-stu-id="f0e10-118">Dynamic mapping requires that the .NET Runtime perform code access check which results in a .NET Evidence object being placed in the Large Object Heap for each transformation and this object is not disposed of until the orchestration completes.</span></span> <span data-ttu-id="f0e10-119">因此，当存在大量的这些类型的同时发生的转换时，可能会看到内存使用率显著增加，这也会导致内存不足异常。</span><span class="sxs-lookup"><span data-stu-id="f0e10-119">Therefore, when there are a lot of these types of transforms occurring simultaneously, you may see the memory usage increase substantially which can also lead to the out of memory exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0e10-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0e10-120">See Also</span></span>  
 <span data-ttu-id="f0e10-121">[业务流程形状](../core/orchestration-shapes.md) </span><span class="sxs-lookup"><span data-stu-id="f0e10-121">[Orchestration Shapes](../core/orchestration-shapes.md) </span></span>  
 [<span data-ttu-id="f0e10-122">使用 BizTalk 映射器创建映射</span><span class="sxs-lookup"><span data-stu-id="f0e10-122">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)