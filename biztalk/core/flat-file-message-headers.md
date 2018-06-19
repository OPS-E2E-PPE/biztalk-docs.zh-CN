---
title: 平面文件消息标头 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1981daaf-149a-426d-9a2f-5fcf64bce185
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 271e9fe74d0a55f4b3ff5271861d24474fffaf37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246349"
---
# <a name="flat-file-message-headers"></a><span data-ttu-id="f9a46-102">平面文件消息头部</span><span class="sxs-lookup"><span data-stu-id="f9a46-102">Flat File Message Headers</span></span>
<span data-ttu-id="f9a46-103">可选的平面文件实例消息头的平面文件反汇编程序分析已在中配置的平面文件架构由控制**标头架构**的平面文件反汇编程序的设计时属性或**XMLNORM。HeaderSpecName**消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="f9a46-103">The parsing of the optional flat file instance message header by the flat file disassembler is controlled by the flat file schema that you have configured in the **Header schema** design-time property of the flat file disassembler or the **XMLNORM.HeaderSpecName** message context property.</span></span> <span data-ttu-id="f9a46-104">如果未指定使用这两种方法之一的架构，平面文件反汇编程序假定平面文件实例消息不包含标头。</span><span class="sxs-lookup"><span data-stu-id="f9a46-104">If you have not specified a schema using one of these two methods, the flat file disassembler assumes that the flat file instance message does not contain a header.</span></span>  

## <a name="outbound-messages"></a><span data-ttu-id="f9a46-105">出站消息</span><span class="sxs-lookup"><span data-stu-id="f9a46-105">Outbound messages</span></span>  
 <span data-ttu-id="f9a46-106">对于出站的平面文件实例消息，你可以配置以通过指定适当的架构中生成一个标头的平面文件汇编其**标头规范名称**设计时属性或**XMLNORM。HeaderSpecName**消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="f9a46-106">For outbound flat file instance messages, you can configure the flat file assembler to produce a header by specifying the appropriate schema in its **Header Specification Name** design-time property or the **XMLNORM.HeaderSpecName** message context property.</span></span> <span data-ttu-id="f9a46-107">有关设置消息上下文属性的详细信息，请参阅**消息上下文属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="f9a46-107">For more information about setting message context properties, see **Message Context Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  

## <a name="inbound-messages"></a><span data-ttu-id="f9a46-108">入站的消息</span><span class="sxs-lookup"><span data-stu-id="f9a46-108">Inbound messages</span></span>  
 <span data-ttu-id="f9a46-109">可以保留并使用两个不同的方式在入站平面文件实例消息标头中找到的数据。</span><span class="sxs-lookup"><span data-stu-id="f9a46-109">Data found in inbound flat file instance message headers can be preserved and utilized in two different ways.</span></span> <span data-ttu-id="f9a46-110">首先，平面文件实例消息标头可以保存在整个消息上下文的更高版本还原作为标题对应的出站的平面文件实例消息的正文中。</span><span class="sxs-lookup"><span data-stu-id="f9a46-110">First, flat file instance message headers can be saved in their entirety within the message context of the body for later restoration as the header of a corresponding outbound flat file instance message.</span></span> <span data-ttu-id="f9a46-111">你可以使用**保留标头**接收管道来指定应保留标头属性。</span><span class="sxs-lookup"><span data-stu-id="f9a46-111">You can use the **Preserve header** property of the receive pipeline to specify that the header should be preserved.</span></span> <span data-ttu-id="f9a46-112">如果在平面文件汇编器指定一个标头，将对出站消息中使用保留的标头。</span><span class="sxs-lookup"><span data-stu-id="f9a46-112">And if a header is specified in the flat file assembler, the preserved header will be used on the outbound message.</span></span>  
  
 <span data-ttu-id="f9a46-113">平面文件实例消息标头中的数据的第二个、 单个项可以复制到通过在相应的架构中指定的一个或多个字段的属性提升平面文件消息正文与关联的消息上下文。</span><span class="sxs-lookup"><span data-stu-id="f9a46-113">Second, individual items of data from a flat file instance message header can be copied to the message context associated with the flat file message body by specifying property promotion for one or more of the fields in the corresponding schema.</span></span> <span data-ttu-id="f9a46-114">有关将升级属性的详细信息，请参阅[提升属性](../core/promoting-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="f9a46-114">For more information about promoting properties, see [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9a46-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9a46-115">See Also</span></span>  
 <span data-ttu-id="f9a46-116">[平面文件消息正文](../core/flat-file-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="f9a46-116">[Flat File Message Bodies](../core/flat-file-message-bodies.md) </span></span>  
 <span data-ttu-id="f9a46-117">[平面文件消息拖车安排](../core/flat-file-message-trailers.md) </span><span class="sxs-lookup"><span data-stu-id="f9a46-117">[Flat File Message Trailers](../core/flat-file-message-trailers.md) </span></span>  
 <span data-ttu-id="f9a46-118">[平面文件消息的结构](../core/structure-of-a-flat-file-message.md) </span><span class="sxs-lookup"><span data-stu-id="f9a46-118">[Structure of a Flat File Message](../core/structure-of-a-flat-file-message.md) </span></span>  
 [<span data-ttu-id="f9a46-119">如何创建平面文件消息架构</span><span class="sxs-lookup"><span data-stu-id="f9a46-119">How to Create Schemas for Flat File Messages</span></span>](../core/how-to-create-schemas-for-flat-file-messages.md)