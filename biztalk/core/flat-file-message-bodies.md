---
title: 平面文件消息正文 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 097e49a1-75d2-44a4-9372-d78de7b7597c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ef973fca636f4e75f05e26638a841e9e51d39b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387952"
---
# <a name="flat-file-message-bodies"></a><span data-ttu-id="10c7f-102">平面文件消息正文</span><span class="sxs-lookup"><span data-stu-id="10c7f-102">Flat File Message Bodies</span></span>
<span data-ttu-id="10c7f-103">平面文件实例消息正文，是必需的是平面文件拆装器处理成一个或多个 XML 实例消息。</span><span class="sxs-lookup"><span data-stu-id="10c7f-103">A flat file instance message body, which is required, is what the flat file disassembler processes into one or more XML instance messages.</span></span> <span data-ttu-id="10c7f-104">若要了解哪些数据需要入站平面文件实例消息正文中，必须使用对应于正文的平面文件架构配置平面文件拆装器。</span><span class="sxs-lookup"><span data-stu-id="10c7f-104">To know what data to expect in an inbound flat file instance message body, you must configure the flat file disassembler with the flat file schema that corresponds to the body.</span></span> <span data-ttu-id="10c7f-105">可以通过使用指定的架构**文档架构**平面文件拆装器的设计时属性或**XMLNORM。DocumentSpecName**消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="10c7f-105">You can specify the schema by using the **Document schema** design-time property of the flat file disassembler or the **XMLNORM.DocumentSpecName** message context property.</span></span> <span data-ttu-id="10c7f-106">因为平面文件实例消息必须有一个正文部分，则必须配置相应的架构使用这两种方法之一。</span><span class="sxs-lookup"><span data-stu-id="10c7f-106">Because flat file instance messages must have a body part, you must configure the appropriate schema using one of these two methods.</span></span>  
  
 <span data-ttu-id="10c7f-107">对于出站平面文件实例消息，平面文件组装器可以动态地确定适当的平面文件架构的实例消息的正文。</span><span class="sxs-lookup"><span data-stu-id="10c7f-107">For outbound flat file instance messages, the flat file assembler can dynamically determine the appropriate flat file schema for the body of the instance message.</span></span> <span data-ttu-id="10c7f-108">平面文件组装器确定消息类型，这是根元素，这两种必须位于出站消息的 XML 版本的名称和目标命名空间的组合中的相应架构。</span><span class="sxs-lookup"><span data-stu-id="10c7f-108">The flat file assembler determines the appropriate schema from the message type, which is a combination of the target namespace and the name of the root element, both of which must be present in the XML version of the outbound message.</span></span> <span data-ttu-id="10c7f-109">或者，您可以显式配置要使用通过配置的平面文件架构**文档架构**平面文件组装器的设计时属性或**XMLNORM。DocumentSpecName**消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="10c7f-109">Alternatively, you can explicitly configure the flat file schema to be used by configuring the **Document schema** design-time property of the flat file assembler or the **XMLNORM.DocumentSpecName** message context property.</span></span>  
  
 <span data-ttu-id="10c7f-110">可在平面文件拆装器会用其来处理入站的实例消息的平面文件架构中指定属性升级在入站平面文件实例消息正文中找到的数据复制到相应的消息上下文中。</span><span class="sxs-lookup"><span data-stu-id="10c7f-110">Data found in inbound flat file instance message bodies can be copied to the corresponding message context by specifying property promotion in the flat file schema being used by the flat file disassembler to process the inbound instance message.</span></span> <span data-ttu-id="10c7f-111">同样，可以通过在平面文件组装器会用其来处理出站消息的平面文件架构中指定的属性降级回出站平面文件实例消息复制消息上下文中的数据。</span><span class="sxs-lookup"><span data-stu-id="10c7f-111">Likewise, data in the message context can be copied back into outbound flat file instance messages by specifying property demotion in the flat file schema being used by the flat file assembler to process the outbound message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10c7f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="10c7f-112">See Also</span></span>  
 <span data-ttu-id="10c7f-113">[平面文件消息标头](../core/flat-file-message-headers.md) </span><span class="sxs-lookup"><span data-stu-id="10c7f-113">[Flat File Message Headers](../core/flat-file-message-headers.md) </span></span>  
 <span data-ttu-id="10c7f-114">[平面文件消息尾部](../core/flat-file-message-trailers.md) </span><span class="sxs-lookup"><span data-stu-id="10c7f-114">[Flat File Message Trailers](../core/flat-file-message-trailers.md) </span></span>  
 <span data-ttu-id="10c7f-115">[平面文件消息的结构](../core/structure-of-a-flat-file-message.md) </span><span class="sxs-lookup"><span data-stu-id="10c7f-115">[Structure of a Flat File Message](../core/structure-of-a-flat-file-message.md) </span></span>  
 [<span data-ttu-id="10c7f-116">如何为平面文件消息创建架构</span><span class="sxs-lookup"><span data-stu-id="10c7f-116">How to Create Schemas for Flat File Messages</span></span>](../core/how-to-create-schemas-for-flat-file-messages.md)