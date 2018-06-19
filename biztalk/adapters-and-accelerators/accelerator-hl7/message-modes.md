---
title: 消息模式 |Microsoft 文档
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
ms.openlocfilehash: b09a610d000ae6beaef75b1ed0144d1597d517b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205053"
---
# <a name="message-modes"></a><span data-ttu-id="cf8b9-102">消息模式</span><span class="sxs-lookup"><span data-stu-id="cf8b9-102">Message Modes</span></span>
<span data-ttu-id="cf8b9-103">有两个生成所有 HL7 消息的基本概念。</span><span class="sxs-lookup"><span data-stu-id="cf8b9-103">There are two basic concepts that underlie all HL7 messages.</span></span> <span data-ttu-id="cf8b9-104">这些概念地址不同的方式交换数据的独立系统可以在其中进行交互，并提供了一段时间内的分布式卫生保健系统支持的互操作性要求的结构。</span><span class="sxs-lookup"><span data-stu-id="cf8b9-104">These concepts address different ways in which independent systems that exchange data can interact, and provide a structure that supports the requirements of interoperability over time within a distributed health care system.</span></span> <span data-ttu-id="cf8b9-105">下面列出的概念定义后面 HL7 设计在基础主题：</span><span class="sxs-lookup"><span data-stu-id="cf8b9-105">The concepts listed below define the underlying themes behind the HL7 design:</span></span>  
  
-   <span data-ttu-id="cf8b9-106">**消息传送模式**。</span><span class="sxs-lookup"><span data-stu-id="cf8b9-106">**Messaging Mode**.</span></span> <span data-ttu-id="cf8b9-107">识别信息交换的三个基本目的： 广播请求信息 (interrogative) （声明性） 的信息并请求系统执行操作 （命令性）。</span><span class="sxs-lookup"><span data-stu-id="cf8b9-107">The recognition of three fundamental purposes for information exchange: to broadcast information (declarative), to request information (interrogative), and to request that the system take an action (imperative).</span></span> <span data-ttu-id="cf8b9-108">其中每个目的都有其特定的要求和消息流的模式。</span><span class="sxs-lookup"><span data-stu-id="cf8b9-108">Each of these purposes has its particular requirements and pattern of message flow.</span></span>  
  
-   <span data-ttu-id="cf8b9-109">**确认模式**。</span><span class="sxs-lookup"><span data-stu-id="cf8b9-109">**Acknowledgment Mode**.</span></span> <span data-ttu-id="cf8b9-110">需要支持紧密和松散耦合的消息传送的样式。</span><span class="sxs-lookup"><span data-stu-id="cf8b9-110">The need to support tightly and loosely coupled styles of messaging.</span></span> <span data-ttu-id="cf8b9-111">HL7 确认模式启用发送应用程序需要从接收方，响应，或若要启用保证消息传递基础网络。</span><span class="sxs-lookup"><span data-stu-id="cf8b9-111">The acknowledgment modes for HL7 enable a sending application either to require a response from the receiver, or to enable the underlying network to guarantee message delivery.</span></span>  
  
-   <span data-ttu-id="cf8b9-112">**本地化**。</span><span class="sxs-lookup"><span data-stu-id="cf8b9-112">**Localization**.</span></span> <span data-ttu-id="cf8b9-113">公司需要以满足特定的本地要求通过允许实体以将特定于站点的材料引入到消息的规范。</span><span class="sxs-lookup"><span data-stu-id="cf8b9-113">The need to support specific local requirements by allowing entities to introduce site-specific material into message specifications.</span></span>  
  
-   <span data-ttu-id="cf8b9-114">**演变**。</span><span class="sxs-lookup"><span data-stu-id="cf8b9-114">**Evolution**.</span></span> <span data-ttu-id="cf8b9-115">需要通过启用标准版本之间的互操作性支持许多接口与许多应用程序的站点。</span><span class="sxs-lookup"><span data-stu-id="cf8b9-115">The need to support sites with many interfaces and many applications by enabling interoperability between standard versions.</span></span> <span data-ttu-id="cf8b9-116">这使阶段接口升级，而不是需要的所有接口的同时升级到的实体。</span><span class="sxs-lookup"><span data-stu-id="cf8b9-116">This enables entities to stage interface upgrades, as opposed to requiring simultaneous upgrades of all interfaces.</span></span>  
  
 <span data-ttu-id="cf8b9-117">下列函数[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持上述要求：</span><span class="sxs-lookup"><span data-stu-id="cf8b9-117">The following functions of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) support the above requirements:</span></span>  
  
-   <span data-ttu-id="cf8b9-118">HL7 确认模式。</span><span class="sxs-lookup"><span data-stu-id="cf8b9-118">HL7 acknowledgment modes.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="cf8b9-119">支持通过将应用程序确认传递回原始消息发件人的原始确认模式。</span><span class="sxs-lookup"><span data-stu-id="cf8b9-119"> supports the original acknowledgment mode by passing application acknowledgments back to the original message sender.</span></span>  
  
-   <span data-ttu-id="cf8b9-120">不同的消息传递模式。</span><span class="sxs-lookup"><span data-stu-id="cf8b9-120">Different messaging modes.</span></span> <span data-ttu-id="cf8b9-121">这使广播到多个目标，并将联系在一起对关联的查询响应的查询。</span><span class="sxs-lookup"><span data-stu-id="cf8b9-121">This enables broadcast to multiple destinations, and ties together queries to the associated query response.</span></span>  
  
-   <span data-ttu-id="cf8b9-122">支持多个版本，包括 XML 和竖线分隔的编码。</span><span class="sxs-lookup"><span data-stu-id="cf8b9-122">Support for multiple versions, including XML and pipe-delimited encodings.</span></span>  
  
-   <span data-ttu-id="cf8b9-123">若要启用不同的环境的 HL7 版本和升级之间的映射。</span><span class="sxs-lookup"><span data-stu-id="cf8b9-123">Mapping between HL7 versions to enable diverse environments and upgrades.</span></span>  
  
-   <span data-ttu-id="cf8b9-124">在业务流程的本地化 （自定义项）。</span><span class="sxs-lookup"><span data-stu-id="cf8b9-124">Localization (customization) within orchestration.</span></span>  
  
-   <span data-ttu-id="cf8b9-125">若要支持调试和新的接口的计算的工具。</span><span class="sxs-lookup"><span data-stu-id="cf8b9-125">Tools to support debugging and evaluation of new interfaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf8b9-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf8b9-126">See Also</span></span>  
 <span data-ttu-id="cf8b9-127">[处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="cf8b9-127">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="cf8b9-128">[使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="cf8b9-128">[Using HL7 2.X Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span></span>  
 <span data-ttu-id="cf8b9-129">[使用 HL7 2.XML 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="cf8b9-129">[Using HL7 2.XML Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span></span>  
 <span data-ttu-id="cf8b9-130">[消息类型和事件](../../adapters-and-accelerators/accelerator-hl7/message-types-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="cf8b9-130">[Message Types and Events](../../adapters-and-accelerators/accelerator-hl7/message-types-and-events.md) </span></span>  
 [<span data-ttu-id="cf8b9-131">HL7 消息传送</span><span class="sxs-lookup"><span data-stu-id="cf8b9-131">HL7 Messaging</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)