---
title: 平面文件消息拖车安排 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfe115a5-4fdc-4779-94f3-437b5a06fbd4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cbeaef3f23de3cb89d873413964cd331ec23f43
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246285"
---
# <a name="flat-file-message-trailers"></a><span data-ttu-id="06dbc-102">平面文件消息尾部</span><span class="sxs-lookup"><span data-stu-id="06dbc-102">Flat File Message Trailers</span></span>
<span data-ttu-id="06dbc-103">使用平面文件实例消息标头，在由已在中配置的平面文件架构控制通过平面文件反汇编程序的可选的平面文件实例消息尾部的分析**尾部架构**设计时平面文件反汇编程序的属性或**XMLNORM。TrailerSpecName**消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="06dbc-103">As with flat file instance message headers, the parsing of the optional flat file instance message trailer by the flat file disassembler is controlled by the flat file schema that you have configured in the **Trailer schema** design-time property of the flat file disassembler or the **XMLNORM.TrailerSpecName** message context property.</span></span> <span data-ttu-id="06dbc-104">如果未使用上述两种方法之一来指定架构，则平面文件拆装器将假设平面文件实例消息不包含尾部。</span><span class="sxs-lookup"><span data-stu-id="06dbc-104">If you have not specified a schema using one of these two methods, the flat file disassembler will assume that the flat file instance message does not contain a trailer.</span></span>  
  
 <span data-ttu-id="06dbc-105">与平面文件实例消息头不同，平面文件实例消息尾部既不能作为单独的单元进行保存和还原，也不能使用属性升级来将各个数据项复制到与该平面文件实例消息正文相关联的消息上下文中。</span><span class="sxs-lookup"><span data-stu-id="06dbc-105">Unlike with flat file instance message headers, flat file instance message trailers can neither be saved and restored as a single unit, nor can they use property promotion to copy individual items of data to the message context associated with the flat file instance message body.</span></span> <span data-ttu-id="06dbc-106">但是，尾部可以添加到出站的平面文件实例消息通过指定中的相应架构**尾部架构**的平面文件汇编器的设计时属性或**XMLNORM。TrailerSpecName**消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="06dbc-106">However, a trailer can be added to an outbound flat file instance message by specifying the appropriate schema in the **Trailer schema** design-time property of the flat file assembler or the **XMLNORM.TrailerSpecName** message context property.</span></span> <span data-ttu-id="06dbc-107">通过在平面文件实例消息正文的消息上下文中使用属性降级，或在相应的架构中指定默认值或固定值，可以指定构成尾部的可变部分的数据。</span><span class="sxs-lookup"><span data-stu-id="06dbc-107">The data that constitutes the variable portion of the trailer can be specified using property demotion from the message context of the flat file instance message body, or by specifying default or fixed values in the corresponding schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06dbc-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06dbc-108">See Also</span></span>  
 <span data-ttu-id="06dbc-109">[平面文件消息标头](../core/flat-file-message-headers.md) </span><span class="sxs-lookup"><span data-stu-id="06dbc-109">[Flat File Message Headers](../core/flat-file-message-headers.md) </span></span>  
 <span data-ttu-id="06dbc-110">[平面文件消息正文](../core/flat-file-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="06dbc-110">[Flat File Message Bodies](../core/flat-file-message-bodies.md) </span></span>  
 <span data-ttu-id="06dbc-111">[平面文件消息的结构](../core/structure-of-a-flat-file-message.md) </span><span class="sxs-lookup"><span data-stu-id="06dbc-111">[Structure of a Flat File Message](../core/structure-of-a-flat-file-message.md) </span></span>  
 [<span data-ttu-id="06dbc-112">如何创建平面文件消息架构</span><span class="sxs-lookup"><span data-stu-id="06dbc-112">How to Create Schemas for Flat File Messages</span></span>](../core/how-to-create-schemas-for-flat-file-messages.md)