---
title: MQSeries 适配器自定义标头 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, custom headers
ms.assetid: b0e18203-a33f-4d50-8483-396699cdff23
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 758b0bb33be70f681d4d7ef732e50555d6eca026
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323788"
---
# <a name="mqseries-adapter-custom-headers"></a><span data-ttu-id="304a8-102">MQSeries 适配器自定义标头</span><span class="sxs-lookup"><span data-stu-id="304a8-102">MQSeries Adapter Custom Headers</span></span>
<span data-ttu-id="304a8-103">由于在 MQSeries 消息中所使用的标头结构，你必须管理任何你想要使用的自定义标头。</span><span class="sxs-lookup"><span data-stu-id="304a8-103">Because of the header structures used in MQSeries messages, you must manage any custom headers you want to use.</span></span> <span data-ttu-id="304a8-104">自定义标头必须是消息正文，以便避免干扰 MQSeries 标头的处理的一部分。</span><span class="sxs-lookup"><span data-stu-id="304a8-104">Custom headers must be part of the message body to avoid interfering with the processing of the MQSeries headers.</span></span> <span data-ttu-id="304a8-105">请确保您避免降级自动升级的属性之一。</span><span class="sxs-lookup"><span data-stu-id="304a8-105">Make sure that you avoid demoting any one of the automatically promoted properties.</span></span> <span data-ttu-id="304a8-106">有关自动升级的属性的详细信息，请参阅[MQSeries 适配器属性](../core/mqseries-adapter-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="304a8-106">For more information about automatically promoted properties, see [MQSeries Adapter Properties](../core/mqseries-adapter-properties.md).</span></span>  
  
 <span data-ttu-id="304a8-107">反过来，消息正文中的自定义标头合并需要进行其他处理。</span><span class="sxs-lookup"><span data-stu-id="304a8-107">In turn, the incorporation of custom headers in the message body requires additional processing.</span></span> <span data-ttu-id="304a8-108">一种解决方案是处理的应用程序管道中的自定义标头。</span><span class="sxs-lookup"><span data-stu-id="304a8-108">One solution is to handle the custom headers in the pipelines of the application.</span></span> <span data-ttu-id="304a8-109">接收管道提取自定义标头信息并将升级为上下文属性的信息。</span><span class="sxs-lookup"><span data-stu-id="304a8-109">A receive pipeline extracts the custom header information and promotes the information as context properties.</span></span> <span data-ttu-id="304a8-110">同样，发送管道使用对应于自定义标头上下文属性，并将消息的正文中的属性降级。</span><span class="sxs-lookup"><span data-stu-id="304a8-110">Similarly, the send pipeline takes the context properties corresponding to the custom header and demotes the properties in the body of the message.</span></span>  
  
 <span data-ttu-id="304a8-111">有关在管道组件中使用自定义标头的示例，请参阅[MQSSendPipelineComponent （BizTalk Server 示例）](../core/mqssendpipelinecomponent-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="304a8-111">For an example of using custom headers in a pipeline component, see [MQSSendPipelineComponent (BizTalk Server Sample)](../core/mqssendpipelinecomponent-biztalk-server-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="304a8-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="304a8-112">See Also</span></span>  
 [<span data-ttu-id="304a8-113">MQSeries 适配器属性</span><span class="sxs-lookup"><span data-stu-id="304a8-113">MQSeries Adapter Properties</span></span>](../core/mqseries-adapter-properties.md)