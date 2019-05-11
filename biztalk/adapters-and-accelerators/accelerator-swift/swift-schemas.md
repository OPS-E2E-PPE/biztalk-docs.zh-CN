---
title: SWIFT 架构 |Microsoft Docs
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
ms.openlocfilehash: 84bc0cde2b41d5518c7bd15bdc35b148c658a63e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376948"
---
# <a name="swift-schemas"></a><span data-ttu-id="4810c-102">SWIFT 架构</span><span class="sxs-lookup"><span data-stu-id="4810c-102">SWIFT Schemas</span></span>
[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] <span data-ttu-id="4810c-103">通过发送和接收 SWIFT 财务 (FIN) 消息作为单个平面文件的 SWIFT 网络。</span><span class="sxs-lookup"><span data-stu-id="4810c-103">sends and receives SWIFT financial (FIN) messages as individual flat files over the SWIFT network.</span></span> <span data-ttu-id="4810c-104">每个消息包含一组标头块的一组预定义的标记的字段和位置或有序子字段和尾部尾部块内的一组组成的文本块。</span><span class="sxs-lookup"><span data-stu-id="4810c-104">Each individual message consists of a set of header blocks, a text block made up of a predefined set of labeled fields and positional or ordered subfields, and a set of trailers inside a trailer block.</span></span> <span data-ttu-id="4810c-105">文本块的内容因消息类型而异。</span><span class="sxs-lookup"><span data-stu-id="4810c-105">The content of the text block varies by message type.</span></span>  
  
 <span data-ttu-id="4810c-106">此外，还有许多应用程序，exchange SWIFT 财务 (FIN) 消息批，一系列单个文件中包含的消息。</span><span class="sxs-lookup"><span data-stu-id="4810c-106">There are also many applications, which exchange batches of SWIFT financial (FIN) messages—a set of messages contained in a single file.</span></span> <span data-ttu-id="4810c-107">该文件可能本地传递，或可能通过 FileAct 传输 (通过 SWIFT IP 网络 — SIPN)，或通过 FTP。</span><span class="sxs-lookup"><span data-stu-id="4810c-107">The file may be delivered locally or may be transmitted through FileAct (over the SWIFT IP Network—SIPN), or through FTP.</span></span>  
  
 <span data-ttu-id="4810c-108">若要简化数据的操作与关联这些消息，不管它们是批处理中还是单独提交 Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]提供了一个 XSD 架构定义每种消息类型。</span><span class="sxs-lookup"><span data-stu-id="4810c-108">To simplify the manipulation of the data associated with these messages, regardless of whether they are batched or submitted individually, Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] provides an XSD schema defining each message type.</span></span> <span data-ttu-id="4810c-109">此架构将升级消息类型，以便可以自动与正确的架构，并自动外部的平面文件表示形式，由 SWIFT 网络，与 XML 之间转换消息。</span><span class="sxs-lookup"><span data-stu-id="4810c-109">This schema promotes the message type so that messages can be automatically associated with the proper schema, and automatically transformed between the external flat file representation, used by the SWIFT network, to and from XML.</span></span>  
  
 <span data-ttu-id="4810c-110">架构包含的所有块包括标头、 文本和尾部。</span><span class="sxs-lookup"><span data-stu-id="4810c-110">The schema includes all of the blocks including headers, text, and trailers.</span></span> <span data-ttu-id="4810c-111">此架构是信息的交换架构，因为它是信息的完整，无法使用 FIN 消息级协议，SWIFT 网络上传输消息，并将包含所有与通过 SWIFT 网络接收的消息关联。</span><span class="sxs-lookup"><span data-stu-id="4810c-111">This schema is an interchange schema, because it is comprehensive enough to transmit messages over the SWIFT network using the FIN message-level protocols, and to contain all of the information associated with a message received through the SWIFT network.</span></span>  
  
 <span data-ttu-id="4810c-112">每种消息类型的架构定义的总体格式和该消息类型的上下文。</span><span class="sxs-lookup"><span data-stu-id="4810c-112">The schema for each message type defines the overall format and context of that message type.</span></span> <span data-ttu-id="4810c-113">A4SWIFT 定义每个块。</span><span class="sxs-lookup"><span data-stu-id="4810c-113">A4SWIFT defines each block.</span></span> <span data-ttu-id="4810c-114">在每个块中，字段和子字段的布局方式。根据需要，从常见的基本或复杂类型，在单独的架构中定义生成的字段和子字段。</span><span class="sxs-lookup"><span data-stu-id="4810c-114">Inside each block, the fields and subfields are laid out. As appropriate, the fields and subfields are built from common base or complex types, defined in separate schemas.</span></span> <span data-ttu-id="4810c-115">架构级的验证包括格式、 字符集、 设置值、 范围、 必需/可选，可重复性、 位置和长度，根据需要。</span><span class="sxs-lookup"><span data-stu-id="4810c-115">Schema-level validation includes format, character set, value set, range, required/optional, repeatability, position, and length, as appropriate.</span></span> <span data-ttu-id="4810c-116">业务规则执行跨字段验证和其他逻辑检查。</span><span class="sxs-lookup"><span data-stu-id="4810c-116">The business rules perform cross-field validations and other logical checks.</span></span>  
  
 <span data-ttu-id="4810c-117">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="4810c-117">This section contains:</span></span>  
  
-   [<span data-ttu-id="4810c-118">示例消息演示文稿</span><span class="sxs-lookup"><span data-stu-id="4810c-118">Sample Message Presentation</span></span>](../../adapters-and-accelerators/accelerator-swift/sample-message-presentation.md)  
  
-   [<span data-ttu-id="4810c-119">示例架构演示文稿</span><span class="sxs-lookup"><span data-stu-id="4810c-119">Sample Schema Presentation</span></span>](../../adapters-and-accelerators/accelerator-swift/sample-schema-presentation.md)  
  
-   [<span data-ttu-id="4810c-120">SWIFT 标头</span><span class="sxs-lookup"><span data-stu-id="4810c-120">SWIFT Headers</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-headers.md)  
  
-   [<span data-ttu-id="4810c-121">SWIFT 文本</span><span class="sxs-lookup"><span data-stu-id="4810c-121">SWIFT Text</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-text.md)  
  
-   [<span data-ttu-id="4810c-122">SWIFT 尾部</span><span class="sxs-lookup"><span data-stu-id="4810c-122">SWIFT Trailers</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-trailers.md)  
  
-   [<span data-ttu-id="4810c-123">更新 SWIFT 消息标准</span><span class="sxs-lookup"><span data-stu-id="4810c-123">Updating SWIFT Message Standards</span></span>](../../adapters-and-accelerators/accelerator-swift/updating-swift-messaging-standards.md)