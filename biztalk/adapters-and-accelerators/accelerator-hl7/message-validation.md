---
title: 消息验证 |Microsoft Docs
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
ms.openlocfilehash: 67d3da2162fedcb266e5b754e8bb55893238d7e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303681"
---
# <a name="message-validation"></a><span data-ttu-id="99ae1-102">消息验证</span><span class="sxs-lookup"><span data-stu-id="99ae1-102">Message Validation</span></span>
<span data-ttu-id="99ae1-103">消息验证发生的传入和传出 HL7 消息 HL7 2.X 接收和发送管道。</span><span class="sxs-lookup"><span data-stu-id="99ae1-103">Message validation occurs for incoming and outgoing HL7 messages with HL7 2.X receive and send pipelines.</span></span> <span data-ttu-id="99ae1-104">你可以配置验证只有 MSH （标头） 段，或整个消息正文。</span><span class="sxs-lookup"><span data-stu-id="99ae1-104">You can configure validation for only the MSH (header) segment, or for the entire message body.</span></span> <span data-ttu-id="99ae1-105">此外，就可以根据唯一本地化版本的架构进行验证。</span><span class="sxs-lookup"><span data-stu-id="99ae1-105">In addition, it is possible to validate against unique localized versions of the schema.</span></span> <span data-ttu-id="99ae1-106">通过定义一个唯一的命名空间值，并使用此命名空间值 （在参与方级别） 的 HL7 消息传送配置和定义消息的实际架构的目标命名空间属性中完成此操作。</span><span class="sxs-lookup"><span data-stu-id="99ae1-106">You accomplish this by defining a unique namespace value, and using this namespace value within both the HL7 messaging configuration (at the party level) and the target namespace property of the actual schema that defines the message.</span></span> <span data-ttu-id="99ae1-107">在运行时，Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 使用命名空间和架构的根引用属性的组合来选择消息分析和验证相应的架构。</span><span class="sxs-lookup"><span data-stu-id="99ae1-107">At run time, Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses the combination of namespace and the root reference property for the schema to select the appropriate schema for message parsing and validation.</span></span>  
  
 <span data-ttu-id="99ae1-108">分析器和序列化程序来执行基于与消息关联的参与方设置的验证。</span><span class="sxs-lookup"><span data-stu-id="99ae1-108">The parser and serializer perform validation based on the settings for the party associated with a message.</span></span> <span data-ttu-id="99ae1-109">其他参与方设置，包括批处理、 确认和消息标头重写会影响分析器或序列化程序如何执行验证。</span><span class="sxs-lookup"><span data-stu-id="99ae1-109">Other party settings, including batching, acknowledgment, and message-header override affect how the parser or serializer performs validation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99ae1-110">序列化程序执行一系列的步骤，包括 （如果适用） 执行从 MSH 映射，标头重写和执行 XML 验证。</span><span class="sxs-lookup"><span data-stu-id="99ae1-110">The serializer performs a series of steps, including (if applicable) performing header overrides from an MSH map, and performing XML validation.</span></span> <span data-ttu-id="99ae1-111">如果标头重写和验证过程是同时启用了，并且标头重写过程将不正确的值输入到标头字段，该消息将通过验证，即使该消息是通过正文验证。</span><span class="sxs-lookup"><span data-stu-id="99ae1-111">If the header override and validation processes are both enabled, and the header override process enters an incorrect value into a header field, the message will fail validation, even if the message were to pass body validation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99ae1-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="99ae1-112">See Also</span></span>  
 [<span data-ttu-id="99ae1-113"> MSH 替代</span><span class="sxs-lookup"><span data-stu-id="99ae1-113">MSH Override</span></span>](../../adapters-and-accelerators/accelerator-hl7/msh-override.md)