---
title: "MQSeries 适配器自定义标头 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: MQSeries adapters, custom headers
ms.assetid: b0e18203-a33f-4d50-8483-396699cdff23
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09a05b8c73cd7be84af01eb4465681816e429bc3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="mqseries-adapter-custom-headers"></a><span data-ttu-id="78a92-102">MQSeries 适配器自定义标头</span><span class="sxs-lookup"><span data-stu-id="78a92-102">MQSeries Adapter Custom Headers</span></span>
<span data-ttu-id="78a92-103">由于在 MQSeries 消息中使用了标头结构，因此必须对要使用的所有自定义标头进行管理。</span><span class="sxs-lookup"><span data-stu-id="78a92-103">Because of the header structures used in MQSeries messages, you must manage any custom headers you want to use.</span></span> <span data-ttu-id="78a92-104">为了避免影响对 MQSeries 标头的处理，自定义标头必须包含在消息正文中。</span><span class="sxs-lookup"><span data-stu-id="78a92-104">Custom headers must be part of the message body to avoid interfering with the processing of the MQSeries headers.</span></span> <span data-ttu-id="78a92-105">应避免对任何自动升级的属性进行降级。</span><span class="sxs-lookup"><span data-stu-id="78a92-105">Make sure that you avoid demoting any one of the automatically promoted properties.</span></span> <span data-ttu-id="78a92-106">有关自动提升的属性的详细信息，请参阅[MQSeries 适配器属性](../core/mqseries-adapter-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="78a92-106">For more information about automatically promoted properties, see [MQSeries Adapter Properties](../core/mqseries-adapter-properties.md).</span></span>  
  
 <span data-ttu-id="78a92-107">在消息正文中包含自定义标头需要执行额外的处理任务。</span><span class="sxs-lookup"><span data-stu-id="78a92-107">In turn, the incorporation of custom headers in the message body requires additional processing.</span></span> <span data-ttu-id="78a92-108">一种解决方案是在应用程序的管道中处理自定义标头。</span><span class="sxs-lookup"><span data-stu-id="78a92-108">One solution is to handle the custom headers in the pipelines of the application.</span></span> <span data-ttu-id="78a92-109">接收管道提取自定义标头信息并将该信息升级为上下文属性。</span><span class="sxs-lookup"><span data-stu-id="78a92-109">A receive pipeline extracts the custom header information and promotes the information as context properties.</span></span> <span data-ttu-id="78a92-110">同样，发送管道获取与自定义标头对应的上下文属性并在消息正文中对这些属性进行降级。</span><span class="sxs-lookup"><span data-stu-id="78a92-110">Similarly, the send pipeline takes the context properties corresponding to the custom header and demotes the properties in the body of the message.</span></span>  
  
 <span data-ttu-id="78a92-111">有关在管道组件中使用自定义标头的示例，请参阅[MQSSendPipelineComponent （BizTalk Server 示例）](../core/mqssendpipelinecomponent-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="78a92-111">For an example of using custom headers in a pipeline component, see [MQSSendPipelineComponent (BizTalk Server Sample)](../core/mqssendpipelinecomponent-biztalk-server-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78a92-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78a92-112">See Also</span></span>  
 [<span data-ttu-id="78a92-113">MQSeries 适配器属性</span><span class="sxs-lookup"><span data-stu-id="78a92-113">MQSeries Adapter Properties</span></span>](../core/mqseries-adapter-properties.md)