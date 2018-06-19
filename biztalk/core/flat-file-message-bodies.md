---
title: 平面文件消息正文 |Microsoft 文档
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
ms.openlocfilehash: 2de8748d9a36c817f7db8fed96a59c8d2bd7dda2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246781"
---
# <a name="flat-file-message-bodies"></a><span data-ttu-id="25e84-102">平面文件消息正文</span><span class="sxs-lookup"><span data-stu-id="25e84-102">Flat File Message Bodies</span></span>
<span data-ttu-id="25e84-103">平面文件实例消息正文，是必需的是平面文件反汇编程序处理到一个或多个 XML 实例消息。</span><span class="sxs-lookup"><span data-stu-id="25e84-103">A flat file instance message body, which is required, is what the flat file disassembler processes into one or more XML instance messages.</span></span> <span data-ttu-id="25e84-104">要知道哪些数据需要入站平面文件实例消息正文中，你必须配置与对应于正文的平面文件架构的平面文件反汇编程序。</span><span class="sxs-lookup"><span data-stu-id="25e84-104">To know what data to expect in an inbound flat file instance message body, you must configure the flat file disassembler with the flat file schema that corresponds to the body.</span></span> <span data-ttu-id="25e84-105">你可以通过使用指定的架构**文档架构**的平面文件反汇编程序的设计时属性或**XMLNORM。DocumentSpecName**消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="25e84-105">You can specify the schema by using the **Document schema** design-time property of the flat file disassembler or the **XMLNORM.DocumentSpecName** message context property.</span></span> <span data-ttu-id="25e84-106">由于平面文件实例消息必须有正文部分，你必须配置相应的架构使用这两种方法之一。</span><span class="sxs-lookup"><span data-stu-id="25e84-106">Because flat file instance messages must have a body part, you must configure the appropriate schema using one of these two methods.</span></span>  
  
 <span data-ttu-id="25e84-107">对于出站的平面文件实例消息，平面文件汇编器可以动态确定实例消息的正文的相应的平面文件架构。</span><span class="sxs-lookup"><span data-stu-id="25e84-107">For outbound flat file instance messages, the flat file assembler can dynamically determine the appropriate flat file schema for the body of the instance message.</span></span> <span data-ttu-id="25e84-108">平面文件汇编器确定消息类型，这是根元素，这两种必须存在于出站消息的 XML 版本的名称和目标命名空间的组合中的相应架构。</span><span class="sxs-lookup"><span data-stu-id="25e84-108">The flat file assembler determines the appropriate schema from the message type, which is a combination of the target namespace and the name of the root element, both of which must be present in the XML version of the outbound message.</span></span> <span data-ttu-id="25e84-109">或者，你可以显式配置平面文件架构，用于通过配置**文档架构**的平面文件汇编器的设计时属性或**XMLNORM。DocumentSpecName**消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="25e84-109">Alternatively, you can explicitly configure the flat file schema to be used by configuring the **Document schema** design-time property of the flat file assembler or the **XMLNORM.DocumentSpecName** message context property.</span></span>  
  
 <span data-ttu-id="25e84-110">在入站平面文件实例消息正文中找到的数据可以复制到相应的消息上下文中，通过在平面文件架构的平面文件反汇编程序用于处理入站的实例消息中指定属性提升。</span><span class="sxs-lookup"><span data-stu-id="25e84-110">Data found in inbound flat file instance message bodies can be copied to the corresponding message context by specifying property promotion in the flat file schema being used by the flat file disassembler to process the inbound instance message.</span></span> <span data-ttu-id="25e84-111">同样，还可以在平面文件架构的平面文件汇编正在使用其来处理该出站消息中指定属性降级回出站的平面文件实例消息复制消息上下文中的数据。</span><span class="sxs-lookup"><span data-stu-id="25e84-111">Likewise, data in the message context can be copied back into outbound flat file instance messages by specifying property demotion in the flat file schema being used by the flat file assembler to process the outbound message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25e84-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25e84-112">See Also</span></span>  
 <span data-ttu-id="25e84-113">[平面文件消息标头](../core/flat-file-message-headers.md) </span><span class="sxs-lookup"><span data-stu-id="25e84-113">[Flat File Message Headers](../core/flat-file-message-headers.md) </span></span>  
 <span data-ttu-id="25e84-114">[平面文件消息拖车安排](../core/flat-file-message-trailers.md) </span><span class="sxs-lookup"><span data-stu-id="25e84-114">[Flat File Message Trailers](../core/flat-file-message-trailers.md) </span></span>  
 <span data-ttu-id="25e84-115">[平面文件消息的结构](../core/structure-of-a-flat-file-message.md) </span><span class="sxs-lookup"><span data-stu-id="25e84-115">[Structure of a Flat File Message](../core/structure-of-a-flat-file-message.md) </span></span>  
 [<span data-ttu-id="25e84-116">如何创建平面文件消息架构</span><span class="sxs-lookup"><span data-stu-id="25e84-116">How to Create Schemas for Flat File Messages</span></span>](../core/how-to-create-schemas-for-flat-file-messages.md)