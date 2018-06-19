---
title: 消息验证 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, messages
- messages, validating
ms.assetid: 720ab16a-7ab4-4741-9951-9ab10a2c4c24
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 940b6aa811cbee845b287c09a66c4b9753313ee0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205941"
---
# <a name="message-validation"></a><span data-ttu-id="0ea54-102">消息验证</span><span class="sxs-lookup"><span data-stu-id="0ea54-102">Message Validation</span></span>
<span data-ttu-id="0ea54-103">2.X 接收和发送管道，则将执行消息验证的 HL7 传入和传出 HL7 消息。</span><span class="sxs-lookup"><span data-stu-id="0ea54-103">Message validation occurs for incoming and outgoing HL7 messages with HL7 2.X receive and send pipelines.</span></span> <span data-ttu-id="0ea54-104">你可以配置验证仅针对 MSH （标头中） 的片段，或为整个消息正文。</span><span class="sxs-lookup"><span data-stu-id="0ea54-104">You can configure validation for only the MSH (header) segment, or for the entire message body.</span></span> <span data-ttu-id="0ea54-105">此外，它是架构的用户可以针对唯一本地化版本验证。</span><span class="sxs-lookup"><span data-stu-id="0ea54-105">In addition, it is possible to validate against unique localized versions of the schema.</span></span> <span data-ttu-id="0ea54-106">通过定义一个唯一的命名空间值，并使用此命名空间值 （级别方） 的 HL7 消息传递配置和定义的消息的实际架构的目标命名空间属性中实现此目的。</span><span class="sxs-lookup"><span data-stu-id="0ea54-106">You accomplish this by defining a unique namespace value, and using this namespace value within both the HL7 messaging configuration (at the party level) and the target namespace property of the actual schema that defines the message.</span></span> <span data-ttu-id="0ea54-107">在运行时， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 使用命名空间和架构的根引用属性的组合来选择消息分析和验证的相应架构。</span><span class="sxs-lookup"><span data-stu-id="0ea54-107">At run time, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses the combination of namespace and the root reference property for the schema to select the appropriate schema for message parsing and validation.</span></span>  
  
 <span data-ttu-id="0ea54-108">分析器和序列化程序来执行验证基于当事方与消息关联的设置。</span><span class="sxs-lookup"><span data-stu-id="0ea54-108">The parser and serializer perform validation based on the settings for the party associated with a message.</span></span> <span data-ttu-id="0ea54-109">其他方设置，包括批处理、 确认和消息标头重写会影响分析器或序列化程序如何执行验证。</span><span class="sxs-lookup"><span data-stu-id="0ea54-109">Other party settings, including batching, acknowledgment, and message-header override affect how the parser or serializer performs validation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ea54-110">序列化程序执行一系列步骤，包括 （如果适用） 执行标头重写从 MSH 映射，并执行 XML 验证。</span><span class="sxs-lookup"><span data-stu-id="0ea54-110">The serializer performs a series of steps, including (if applicable) performing header overrides from an MSH map, and performing XML validation.</span></span> <span data-ttu-id="0ea54-111">如果在标头重写和验证过程同时启用，并标头重写过程到标头字段中输入的值不正确，将会失败消息验证，，即使消息打算通过正文验证。</span><span class="sxs-lookup"><span data-stu-id="0ea54-111">If the header override and validation processes are both enabled, and the header override process enters an incorrect value into a header field, the message will fail validation, even if the message were to pass body validation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ea54-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ea54-112">See Also</span></span>  
 [<span data-ttu-id="0ea54-113">MSH 替代</span><span class="sxs-lookup"><span data-stu-id="0ea54-113">MSH Override</span></span>](../../adapters-and-accelerators/accelerator-hl7/msh-override.md)