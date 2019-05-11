---
title: 消息转换模式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aef41642-d33b-4878-be65-ef336530647f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87df85f41e15857cf73e82e437009574861345df
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395903"
---
# <a name="message-transformation-patterns"></a><span data-ttu-id="e1bc2-102">消息转换模式</span><span class="sxs-lookup"><span data-stu-id="e1bc2-102">Message Transformation Patterns</span></span>
<span data-ttu-id="e1bc2-103">消息转换模式定义用于转换消息以进行其他处理，或以匹配所需的文档格式将向其发送消息的服务的经验证指导原则。</span><span class="sxs-lookup"><span data-stu-id="e1bc2-103">Message transformation patterns define proven guidelines for transforming messages for additional processing or to match the expected document format of the service to which the message will be sent.</span></span> <span data-ttu-id="e1bc2-104">一条消息可能需要转换，因为收到的消息的结构不在预期的标准或因为必须将消息从非标准格式转换为 XML。</span><span class="sxs-lookup"><span data-stu-id="e1bc2-104">A message may require transformation because the structure of the received message is not in the expected standard or because the message must be converted from a non-standard format to XML.</span></span>  
  
## <a name="message-translator"></a><span data-ttu-id="e1bc2-105">消息转换器</span><span class="sxs-lookup"><span data-stu-id="e1bc2-105">Message Translator</span></span>  
 <span data-ttu-id="e1bc2-106">消息转换器模式定义为使用不兼容的数据格式的系统之间的通信的解决方案。</span><span class="sxs-lookup"><span data-stu-id="e1bc2-106">The Message Translator pattern defines a solution for communication between systems that use incompatible data formats.</span></span> <span data-ttu-id="e1bc2-107">例如，客户端应用程序可能会发送平面文件的请求消息必须转换为 XML，然后才能进行其他处理。</span><span class="sxs-lookup"><span data-stu-id="e1bc2-107">For example, a client application may send a flat file request message that must be converted to XML before additional processing can occur.</span></span> <span data-ttu-id="e1bc2-108">此模式的详细说明，请参阅[消息转换器](http://go.microsoft.com/fwlink/?LinkId=186845)([http://go.microsoft.com/fwlink/?LinkId=186845](http://go.microsoft.com/fwlink/?LinkId=186845)) 企业集成模式站点上。</span><span class="sxs-lookup"><span data-stu-id="e1bc2-108">For a detailed description of this pattern, see [Message Translator](http://go.microsoft.com/fwlink/?LinkId=186845) ([http://go.microsoft.com/fwlink/?LinkId=186845](http://go.microsoft.com/fwlink/?LinkId=186845)) on the Enterprise Integration Patterns site.</span></span>  
  
 <span data-ttu-id="e1bc2-109">在路线设计器中此模式的实现是一系列[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]转换服务和单个冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="e1bc2-109">The implementation of this pattern in Itinerary Designer is a combination of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] transformation service and a single resolver.</span></span> <span data-ttu-id="e1bc2-110">路线转换服务负责转换使用定义的转换所需的项目的冲突解决程序属性的消息。</span><span class="sxs-lookup"><span data-stu-id="e1bc2-110">The itinerary transformation service is responsible for transforming a message using resolver properties that define the artifacts required for transformation.</span></span> <span data-ttu-id="e1bc2-111">解析程序实现负责提供转换设置，具体取决于冲突解决程序配置静态或动态，进行定义。</span><span class="sxs-lookup"><span data-stu-id="e1bc2-111">The resolver implementation is responsible for providing transformation settings, which can be defined statically or dynamically, depending on the resolver configuration.</span></span>  
  
 <span data-ttu-id="e1bc2-112">消息转换器模式的实现示例，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="e1bc2-112">For an example implementation of the Message Translator pattern, see the following resources:</span></span>  
  
-   [<span data-ttu-id="e1bc2-113">安装和运行路线接入点示例</span><span class="sxs-lookup"><span data-stu-id="e1bc2-113">Installing and Running the Itinerary On-Ramp Sample</span></span>](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
-   [<span data-ttu-id="e1bc2-114">如何：转换消息并使用请求-响应消息交换模式的服务终结点的路由</span><span class="sxs-lookup"><span data-stu-id="e1bc2-114">How to: Transform a Message and Route to a Service Endpoint Using a Request-Response Message Exchange Pattern</span></span>](../esb-toolkit/transform-message-and-route-to-service-endpoint-using-request-response-message.md)  
  
## <a name="normalizer"></a><span data-ttu-id="e1bc2-115">规范化器</span><span class="sxs-lookup"><span data-stu-id="e1bc2-115">Normalizer</span></span>  
 <span data-ttu-id="e1bc2-116">规范化器模式是数据模型转换模式的扩展。</span><span class="sxs-lookup"><span data-stu-id="e1bc2-116">The Normalizer pattern is an extension of the Data Model Transformation pattern.</span></span> <span data-ttu-id="e1bc2-117">此模式中不同的格式定义的解决方案，从多个源接收的消息在语义上等效，但消息到达。</span><span class="sxs-lookup"><span data-stu-id="e1bc2-117">This pattern defines a solution in which messages received from multiple sources are semantically equivalent, but the messages arrive in different formats.</span></span> <span data-ttu-id="e1bc2-118">此模式的详细说明，请参阅[规范化器](http://go.microsoft.com/fwlink/?LinkId=186847)([http://go.microsoft.com/fwlink/?LinkId=186847](http://go.microsoft.com/fwlink/?LinkId=186847)) 企业集成模式站点上。</span><span class="sxs-lookup"><span data-stu-id="e1bc2-118">For a detailed description of this pattern, see [Normalizer](http://go.microsoft.com/fwlink/?LinkId=186847) ([http://go.microsoft.com/fwlink/?LinkId=186847](http://go.microsoft.com/fwlink/?LinkId=186847)) on the Enterprise Integration Patterns site.</span></span>  
  
 <span data-ttu-id="e1bc2-119">在路线设计器中此模式的实现是一系列[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]转换服务和单个冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="e1bc2-119">The implementation of this pattern in Itinerary Designer is a combination of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] transformation service and a single resolver.</span></span> <span data-ttu-id="e1bc2-120">路线转换服务负责转换使用定义的转换所需的项目的冲突解决程序属性的消息。</span><span class="sxs-lookup"><span data-stu-id="e1bc2-120">The itinerary transformation service is responsible for transforming a message using resolver properties that define the artifacts required for transformation.</span></span> <span data-ttu-id="e1bc2-121">解析程序实现负责动态解析具有指定类型的消息的相应 Microsoft BizTalk 映射。</span><span class="sxs-lookup"><span data-stu-id="e1bc2-121">The resolver implementation is responsible for dynamically resolving the appropriate Microsoft BizTalk map for a specified type of message.</span></span>  
  
 <span data-ttu-id="e1bc2-122">规范化器模式的实现示例，请参阅[安装和运行路线接入点示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="e1bc2-122">For an example implementation of the Normalizer pattern, see the [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>  
  
## <a name="content-enricher"></a><span data-ttu-id="e1bc2-123">内容扩充器添加</span><span class="sxs-lookup"><span data-stu-id="e1bc2-123">Content Enricher</span></span>  
 <span data-ttu-id="e1bc2-124">内容扩充器添加模式定义收到的消息可能不包括所需的目标系统来适当地处理该消息的所有数据的解决方案。</span><span class="sxs-lookup"><span data-stu-id="e1bc2-124">The Content Enricher pattern defines a solution in which a received message may not include all the data required for the target system to appropriately process the message.</span></span> <span data-ttu-id="e1bc2-125">例如，发送服务可能包括 ZIP 代码而无需是冗余的状态代码，但接收服务需要一条消息，包括状态代码和邮政编码;接收服务可以处理收到的消息之前，其他数据是必需的。</span><span class="sxs-lookup"><span data-stu-id="e1bc2-125">For example, the sending service may include a ZIP code without a redundant state code, but the receiving service expects a message that includes both a state code and a ZIP code; additional data is required before the receiving service can process the received message.</span></span> <span data-ttu-id="e1bc2-126">此模式的详细说明，请参阅[内容扩充器添加](http://go.microsoft.com/fwlink/?LinkId=186848)([http://go.microsoft.com/fwlink/?LinkId=186848](http://go.microsoft.com/fwlink/?LinkId=186848)) 企业集成模式站点上。</span><span class="sxs-lookup"><span data-stu-id="e1bc2-126">For a detailed description of this pattern, see [Content Enricher](http://go.microsoft.com/fwlink/?LinkId=186848) ([http://go.microsoft.com/fwlink/?LinkId=186848](http://go.microsoft.com/fwlink/?LinkId=186848)) on the Enterprise Integration Patterns site.</span></span>  
  
 <span data-ttu-id="e1bc2-127">有关内容扩充器添加模式的实现示例，请参阅[安装和运行消息充实示例](../esb-toolkit/installing-and-running-the-message-enrichment-sample.md)应用程序。</span><span class="sxs-lookup"><span data-stu-id="e1bc2-127">For an example implementation of the Content Enricher pattern, see the [Installing and Running the Message Enrichment Sample](../esb-toolkit/installing-and-running-the-message-enrichment-sample.md) application.</span></span>