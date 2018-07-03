---
title: 消息模式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message modes, about message modes
- messages, message modes
- message modes, HL7 messages
ms.assetid: 2d832b67-6f0e-45e1-95ac-cb80b74a7831
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfce63f527dbe9643228b3b47a509b404e78c510
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009134"
---
# <a name="message-modes"></a><span data-ttu-id="04723-102">消息模式</span><span class="sxs-lookup"><span data-stu-id="04723-102">Message Modes</span></span>
<span data-ttu-id="04723-103">有两个基础所有 HL7 消息的基本概念。</span><span class="sxs-lookup"><span data-stu-id="04723-103">There are two basic concepts that underlie all HL7 messages.</span></span> <span data-ttu-id="04723-104">这些概念的地址不同的方式交换数据的独立系统可以进行交互，并提供支持的互操作性要求通过分布式卫生保健系统中的时间结构。</span><span class="sxs-lookup"><span data-stu-id="04723-104">These concepts address different ways in which independent systems that exchange data can interact, and provide a structure that supports the requirements of interoperability over time within a distributed health care system.</span></span> <span data-ttu-id="04723-105">下面列出的概念定义 HL7 设计背后的基础主题：</span><span class="sxs-lookup"><span data-stu-id="04723-105">The concepts listed below define the underlying themes behind the HL7 design:</span></span>  
  
- <span data-ttu-id="04723-106">**消息传送模式**。</span><span class="sxs-lookup"><span data-stu-id="04723-106">**Messaging Mode**.</span></span> <span data-ttu-id="04723-107">交换信息的三个基本用途的识别： 广播请求信息 (interrogative) （声明性） 的信息，并请求系统执行操作 （命令性）。</span><span class="sxs-lookup"><span data-stu-id="04723-107">The recognition of three fundamental purposes for information exchange: to broadcast information (declarative), to request information (interrogative), and to request that the system take an action (imperative).</span></span> <span data-ttu-id="04723-108">每个这些用途有其特定的要求和消息流的模式。</span><span class="sxs-lookup"><span data-stu-id="04723-108">Each of these purposes has its particular requirements and pattern of message flow.</span></span>  
  
- <span data-ttu-id="04723-109">**确认模式**。</span><span class="sxs-lookup"><span data-stu-id="04723-109">**Acknowledgment Mode**.</span></span> <span data-ttu-id="04723-110">需要支持紧密和松散耦合的消息传送的样式。</span><span class="sxs-lookup"><span data-stu-id="04723-110">The need to support tightly and loosely coupled styles of messaging.</span></span> <span data-ttu-id="04723-111">HL7 的确认模式启用发送应用程序需要从接收方，响应，或若要启用要保证消息传递的基础网络。</span><span class="sxs-lookup"><span data-stu-id="04723-111">The acknowledgment modes for HL7 enable a sending application either to require a response from the receiver, or to enable the underlying network to guarantee message delivery.</span></span>  
  
- <span data-ttu-id="04723-112">**本地化**。</span><span class="sxs-lookup"><span data-stu-id="04723-112">**Localization**.</span></span> <span data-ttu-id="04723-113">需要支持特定的本地要求通过允许实体以引入消息规范的特定于站点的材料。</span><span class="sxs-lookup"><span data-stu-id="04723-113">The need to support specific local requirements by allowing entities to introduce site-specific material into message specifications.</span></span>  
  
- <span data-ttu-id="04723-114">**演变**。</span><span class="sxs-lookup"><span data-stu-id="04723-114">**Evolution**.</span></span> <span data-ttu-id="04723-115">需要标准版本之间的互操作性，从而支持具有多个接口和许多应用程序的站点。</span><span class="sxs-lookup"><span data-stu-id="04723-115">The need to support sites with many interfaces and many applications by enabling interoperability between standard versions.</span></span> <span data-ttu-id="04723-116">这使实体到阶段接口升级，而不是需要的所有接口的同时进行升级。</span><span class="sxs-lookup"><span data-stu-id="04723-116">This enables entities to stage interface upgrades, as opposed to requiring simultaneous upgrades of all interfaces.</span></span>  
  
  <span data-ttu-id="04723-117">Microsoft BizTalk Accelerator for HL7 的以下函数 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持更高版本要求：</span><span class="sxs-lookup"><span data-stu-id="04723-117">The following functions of Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) support the above requirements:</span></span>  
  
- <span data-ttu-id="04723-118">HL7 确认模式。</span><span class="sxs-lookup"><span data-stu-id="04723-118">HL7 acknowledgment modes.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="04723-119"> 支持的原始确认模式通过将应用程序确认传递回原始消息发件人。</span><span class="sxs-lookup"><span data-stu-id="04723-119"> supports the original acknowledgment mode by passing application acknowledgments back to the original message sender.</span></span>  
  
- <span data-ttu-id="04723-120">不同的消息传递模式。</span><span class="sxs-lookup"><span data-stu-id="04723-120">Different messaging modes.</span></span> <span data-ttu-id="04723-121">这使广播到多个目标，将联系在一起对关联的查询响应的查询。</span><span class="sxs-lookup"><span data-stu-id="04723-121">This enables broadcast to multiple destinations, and ties together queries to the associated query response.</span></span>  
  
- <span data-ttu-id="04723-122">支持多个版本，包括 XML 和竖线分隔的编码。</span><span class="sxs-lookup"><span data-stu-id="04723-122">Support for multiple versions, including XML and pipe-delimited encodings.</span></span>  
  
- <span data-ttu-id="04723-123">若要启用各种环境的 HL7 版本和升级之间的映射。</span><span class="sxs-lookup"><span data-stu-id="04723-123">Mapping between HL7 versions to enable diverse environments and upgrades.</span></span>  
  
- <span data-ttu-id="04723-124">业务流程内本地化 （自定义）。</span><span class="sxs-lookup"><span data-stu-id="04723-124">Localization (customization) within orchestration.</span></span>  
  
- <span data-ttu-id="04723-125">若要支持调试和计算结果的新接口的工具。</span><span class="sxs-lookup"><span data-stu-id="04723-125">Tools to support debugging and evaluation of new interfaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04723-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="04723-126">See Also</span></span>  
 <span data-ttu-id="04723-127">[处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="04723-127">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="04723-128">[使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="04723-128">[Using HL7 2.X Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span></span>  
 <span data-ttu-id="04723-129">[使用 HL7 2.xml 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="04723-129">[Using HL7 2.XML Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span></span>  
 <span data-ttu-id="04723-130">[消息类型和事件](../../adapters-and-accelerators/accelerator-hl7/message-types-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="04723-130">[Message Types and Events](../../adapters-and-accelerators/accelerator-hl7/message-types-and-events.md) </span></span>  
 [<span data-ttu-id="04723-131">HL7 消息传送</span><span class="sxs-lookup"><span data-stu-id="04723-131">HL7 Messaging</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)