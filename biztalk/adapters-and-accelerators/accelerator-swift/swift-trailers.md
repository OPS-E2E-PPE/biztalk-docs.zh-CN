---
title: SWIFT 拖车安排 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SWIFT Trailer schema
- schemas, SWIFT
- trailers [SWIFT]
- SWIFT, trailers
ms.assetid: b6d64584-0514-4c87-98c0-33755efc4695
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc3155ac21f55e7c61483b9287429f9b722f6a84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214493"
---
# <a name="swift-trailers"></a><span data-ttu-id="d7eb1-102">SWIFT 拖车安排</span><span class="sxs-lookup"><span data-stu-id="d7eb1-102">SWIFT Trailers</span></span>
<span data-ttu-id="d7eb1-103">每个 SWIFT 消息具有所需的消息交换和安全要求的一个或多个拖车安排。</span><span class="sxs-lookup"><span data-stu-id="d7eb1-103">Each SWIFT message has one or more trailers as required by the message exchange and security requirements.</span></span> <span data-ttu-id="d7eb1-104">系统尾部如果适用，请按照用户拖车安排。</span><span class="sxs-lookup"><span data-stu-id="d7eb1-104">System trailers, if applicable, follow user trailers.</span></span> <span data-ttu-id="d7eb1-105">每个预告片预告片块中的将显示在由进一步对大括号分隔 subblock。</span><span class="sxs-lookup"><span data-stu-id="d7eb1-105">Each trailer within the Trailer Block appears within a subblock delimited by further pairs of curly brackets.</span></span> <span data-ttu-id="d7eb1-106">每个 subblock 开头表示跟一个冒号的电影预告片类型的三个字母。</span><span class="sxs-lookup"><span data-stu-id="d7eb1-106">Each subblock begins with three letters denoting the trailer type, followed by a colon.</span></span>  
  
 <span data-ttu-id="d7eb1-107">SWIFT 尾部架构 (SWIFT Trailer.xsd) 包含以下格式：</span><span class="sxs-lookup"><span data-stu-id="d7eb1-107">The SWIFT Trailer schema (SWIFT Trailer.xsd) contains the format for the following:</span></span>  
  
-   <span data-ttu-id="d7eb1-108">文本块结束分隔符</span><span class="sxs-lookup"><span data-stu-id="d7eb1-108">The ending delimiter of the text block</span></span>  
  
-   <span data-ttu-id="d7eb1-109">用户拖车安排 （用户和系统信息）</span><span class="sxs-lookup"><span data-stu-id="d7eb1-109">User trailers (user and system information)</span></span>  
  
-   <span data-ttu-id="d7eb1-110">系统拖车安排</span><span class="sxs-lookup"><span data-stu-id="d7eb1-110">System trailers</span></span>  
  
 <span data-ttu-id="d7eb1-111">结束分隔符的文本块是"-}"。</span><span class="sxs-lookup"><span data-stu-id="d7eb1-111">The ending delimiter of the Text Block is "-}".</span></span> <span data-ttu-id="d7eb1-112">电影预告片块开头"{5:"。</span><span class="sxs-lookup"><span data-stu-id="d7eb1-112">The trailer block begins with "{5:".</span></span> <span data-ttu-id="d7eb1-113">电影预告片块的内容包括用户信息 （校验和、 消息身份验证、 专有身份验证等） 和系统信息 （延迟的消息、 消息引用、 可能的重复消息和等等）。</span><span class="sxs-lookup"><span data-stu-id="d7eb1-113">The contents of the trailer block include both user information (checksum, message authentication, proprietary authentication, and so on), and system information (delayed message, message reference, possible duplicate message, and so on).</span></span> <span data-ttu-id="d7eb1-114">拖车安排添加 SWIFT 还提供分隔的第三个块"{s:"。</span><span class="sxs-lookup"><span data-stu-id="d7eb1-114">Trailers added by SWIFT also provide a third block, delimited by "{S:".</span></span> <span data-ttu-id="d7eb1-115">*SWIFT 用户手册*，"FIN 服务说明"主题详细地介绍了块 5 的内容。</span><span class="sxs-lookup"><span data-stu-id="d7eb1-115">The *SWIFT User Handbook*, "FIN Service Description" topic, describes in detail the contents of block 5.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="d7eb1-116">不会验证内容块 s。</span><span class="sxs-lookup"><span data-stu-id="d7eb1-116"> does not validate the contents of block S.</span></span>  
  
 <span data-ttu-id="d7eb1-117">实际的 FIN 接口或 SWIFT 网络追加拖车安排。</span><span class="sxs-lookup"><span data-stu-id="d7eb1-117">The actual FIN interface or the SWIFT network appends the trailers.</span></span> <span data-ttu-id="d7eb1-118">当消息中包含尾部时[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收消息时，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]传送消息的尾部。</span><span class="sxs-lookup"><span data-stu-id="d7eb1-118">If a message contains a trailer when [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receives the message, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] carries the trailer with the message.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="d7eb1-119">如果消息不包含尾部不引发错误时[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收消息。</span><span class="sxs-lookup"><span data-stu-id="d7eb1-119"> does not raise an error if a message does not contain a trailer when [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receives the message.</span></span> <span data-ttu-id="d7eb1-120">作为标头，与所有预告片项，包括块本身，在中是可选[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d7eb1-120">As with headers, all of the trailer entries, including the blocks themselves, are optional in [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span>  
  
 <span data-ttu-id="d7eb1-121">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="d7eb1-121">This section contains:</span></span>  
  
-   [<span data-ttu-id="d7eb1-122">用户拖车安排</span><span class="sxs-lookup"><span data-stu-id="d7eb1-122">User Trailers</span></span>](../../adapters-and-accelerators/accelerator-swift/user-trailers.md)  
  
-   [<span data-ttu-id="d7eb1-123">系统拖车安排</span><span class="sxs-lookup"><span data-stu-id="d7eb1-123">System Trailers</span></span>](../../adapters-and-accelerators/accelerator-swift/system-trailers.md)  
  
## <a name="see-also"></a><span data-ttu-id="d7eb1-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7eb1-124">See Also</span></span>  
 [<span data-ttu-id="d7eb1-125">使用架构</span><span class="sxs-lookup"><span data-stu-id="d7eb1-125">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)