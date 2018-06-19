---
title: SWIFT 架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SWIFT, SWIFT messages
- schemas, SWIFT
- SWIFT messages, SWIFT schemas
- SWIFT, schemas
ms.assetid: 53017a56-a718-4577-a08c-9c92d9a54e7a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b4bac26d99fb3282650c20381bbc18237f8908a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214917"
---
# <a name="swift-schemas"></a><span data-ttu-id="20380-102">SWIFT 架构</span><span class="sxs-lookup"><span data-stu-id="20380-102">SWIFT Schemas</span></span>
[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]<span data-ttu-id="20380-103">通过发送和接收 SWIFT 财务 (FIN) 消息作为单个平面文件 SWIFT 网络。</span><span class="sxs-lookup"><span data-stu-id="20380-103"> sends and receives SWIFT financial (FIN) messages as individual flat files over the SWIFT network.</span></span> <span data-ttu-id="20380-104">每个单个消息包含一组标头块组成一组预定义的标记的字段和位置或有序子字段和尾部预告片块中的一组文本块。</span><span class="sxs-lookup"><span data-stu-id="20380-104">Each individual message consists of a set of header blocks, a text block made up of a predefined set of labeled fields and positional or ordered subfields, and a set of trailers inside a trailer block.</span></span> <span data-ttu-id="20380-105">文本块的内容因消息类型而异。</span><span class="sxs-lookup"><span data-stu-id="20380-105">The content of the text block varies by message type.</span></span>  
  
 <span data-ttu-id="20380-106">也有许多应用程序，交换 SWIFT 财务 (FIN) 消息批处理-一组的单个文件中包含的消息。</span><span class="sxs-lookup"><span data-stu-id="20380-106">There are also many applications, which exchange batches of SWIFT financial (FIN) messages—a set of messages contained in a single file.</span></span> <span data-ttu-id="20380-107">该文件可能本地传递，或可能通过 FileAct 传输 (通过 SWIFT IP 网络-SIPN)，或通过 FTP。</span><span class="sxs-lookup"><span data-stu-id="20380-107">The file may be delivered locally or may be transmitted through FileAct (over the SWIFT IP Network—SIPN), or through FTP.</span></span>  
  
 <span data-ttu-id="20380-108">若要简化与这些消息，无论它们是批处理还是单独，提交关联的数据的操作[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]提供 XSD 架构定义每种消息类型。</span><span class="sxs-lookup"><span data-stu-id="20380-108">To simplify the manipulation of the data associated with these messages, regardless of whether they are batched or submitted individually, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] provides an XSD schema defining each message type.</span></span> <span data-ttu-id="20380-109">此架构提升消息类型，以便可以自动与正确的架构，并自动转换之间外部的平面文件表示形式，由 SWIFT 网络，或从 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="20380-109">This schema promotes the message type so that messages can be automatically associated with the proper schema, and automatically transformed between the external flat file representation, used by the SWIFT network, to and from XML.</span></span>  
  
 <span data-ttu-id="20380-110">架构包含的所有块包括标头、 文本和拖车安排。</span><span class="sxs-lookup"><span data-stu-id="20380-110">The schema includes all of the blocks including headers, text, and trailers.</span></span> <span data-ttu-id="20380-111">此架构是信息的交换架构，因为它是信息的完整，无法通过 SWIFT 网络使用 FIN 消息级协议，传输消息，并可包含所有与通过 SWIFT 网络收到的消息关联。</span><span class="sxs-lookup"><span data-stu-id="20380-111">This schema is an interchange schema, because it is comprehensive enough to transmit messages over the SWIFT network using the FIN message-level protocols, and to contain all of the information associated with a message received through the SWIFT network.</span></span>  
  
 <span data-ttu-id="20380-112">每种消息类型的架构定义的整体的格式和该消息类型的上下文。</span><span class="sxs-lookup"><span data-stu-id="20380-112">The schema for each message type defines the overall format and context of that message type.</span></span> <span data-ttu-id="20380-113">A4SWIFT 定义每个块。</span><span class="sxs-lookup"><span data-stu-id="20380-113">A4SWIFT defines each block.</span></span> <span data-ttu-id="20380-114">在每个块内的字段和子字段的布局。根据需要，从常见的基本或复杂类型，在单独的架构中定义生成的字段和子字段。</span><span class="sxs-lookup"><span data-stu-id="20380-114">Inside each block, the fields and subfields are laid out. As appropriate, the fields and subfields are built from common base or complex types, defined in separate schemas.</span></span> <span data-ttu-id="20380-115">架构级别验证包括格式、 字符集、 设置值、 范围、 必需/可选，可重复性、 位置和长度，根据需要。</span><span class="sxs-lookup"><span data-stu-id="20380-115">Schema-level validation includes format, character set, value set, range, required/optional, repeatability, position, and length, as appropriate.</span></span> <span data-ttu-id="20380-116">业务规则执行跨字段验证和其他逻辑检查。</span><span class="sxs-lookup"><span data-stu-id="20380-116">The business rules perform cross-field validations and other logical checks.</span></span>  
  
 <span data-ttu-id="20380-117">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="20380-117">This section contains:</span></span>  
  
-   [<span data-ttu-id="20380-118">示例消息演示文稿</span><span class="sxs-lookup"><span data-stu-id="20380-118">Sample Message Presentation</span></span>](../../adapters-and-accelerators/accelerator-swift/sample-message-presentation.md)  
  
-   [<span data-ttu-id="20380-119">示例架构演示文稿</span><span class="sxs-lookup"><span data-stu-id="20380-119">Sample Schema Presentation</span></span>](../../adapters-and-accelerators/accelerator-swift/sample-schema-presentation.md)  
  
-   [<span data-ttu-id="20380-120">SWIFT 标头</span><span class="sxs-lookup"><span data-stu-id="20380-120">SWIFT Headers</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-headers.md)  
  
-   [<span data-ttu-id="20380-121">SWIFT 文本</span><span class="sxs-lookup"><span data-stu-id="20380-121">SWIFT Text</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-text.md)  
  
-   [<span data-ttu-id="20380-122">SWIFT 拖车安排</span><span class="sxs-lookup"><span data-stu-id="20380-122">SWIFT Trailers</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-trailers.md)  
  
-   [<span data-ttu-id="20380-123">更新 SWIFT 消息标准</span><span class="sxs-lookup"><span data-stu-id="20380-123">Updating SWIFT Message Standards</span></span>](../../adapters-and-accelerators/accelerator-swift/updating-swift-messaging-standards.md)