---
title: SWIFT 尾部 |Microsoft Docs
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
ms.openlocfilehash: b781371962b8c8d32168d6c9ba4ce38fe20a4a49
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529726"
---
# <a name="swift-trailers"></a><span data-ttu-id="b3ce2-102">SWIFT 尾部</span><span class="sxs-lookup"><span data-stu-id="b3ce2-102">SWIFT Trailers</span></span>
<span data-ttu-id="b3ce2-103">每个 SWIFT 消息具有所需的消息交换和安全要求的一个或多个尾部。</span><span class="sxs-lookup"><span data-stu-id="b3ce2-103">Each SWIFT message has one or more trailers as required by the message exchange and security requirements.</span></span> <span data-ttu-id="b3ce2-104">系统尾部，如果适用，请按照用户尾部。</span><span class="sxs-lookup"><span data-stu-id="b3ce2-104">System trailers, if applicable, follow user trailers.</span></span> <span data-ttu-id="b3ce2-105">每个尾部尾部块中的将显示在由进一步对大括号分隔 subblock。</span><span class="sxs-lookup"><span data-stu-id="b3ce2-105">Each trailer within the Trailer Block appears within a subblock delimited by further pairs of curly brackets.</span></span> <span data-ttu-id="b3ce2-106">每个 subblock 开头指示后接一个冒号的尾部类型的三个字母。</span><span class="sxs-lookup"><span data-stu-id="b3ce2-106">Each subblock begins with three letters denoting the trailer type, followed by a colon.</span></span>  
  
 <span data-ttu-id="b3ce2-107">SWIFT 尾部架构 (SWIFT Trailer.xsd) 包含以下格式：</span><span class="sxs-lookup"><span data-stu-id="b3ce2-107">The SWIFT Trailer schema (SWIFT Trailer.xsd) contains the format for the following:</span></span>  
  
- <span data-ttu-id="b3ce2-108">文本块的结束分隔符</span><span class="sxs-lookup"><span data-stu-id="b3ce2-108">The ending delimiter of the text block</span></span>  
  
- <span data-ttu-id="b3ce2-109">用户尾部 （用户和系统信息）</span><span class="sxs-lookup"><span data-stu-id="b3ce2-109">User trailers (user and system information)</span></span>  
  
- <span data-ttu-id="b3ce2-110">系统尾部</span><span class="sxs-lookup"><span data-stu-id="b3ce2-110">System trailers</span></span>  
  
  <span data-ttu-id="b3ce2-111">文本块的结束分隔符是"--}"。</span><span class="sxs-lookup"><span data-stu-id="b3ce2-111">The ending delimiter of the Text Block is "-}".</span></span> <span data-ttu-id="b3ce2-112">尾部块开头"{5:"。</span><span class="sxs-lookup"><span data-stu-id="b3ce2-112">The trailer block begins with "{5:".</span></span> <span data-ttu-id="b3ce2-113">尾部块的内容包括用户信息 （校验和、 消息身份验证、 专有身份验证等） 和系统信息 （延迟的消息、 消息引用，可能的重复消息等）。</span><span class="sxs-lookup"><span data-stu-id="b3ce2-113">The contents of the trailer block include both user information (checksum, message authentication, proprietary authentication, and so on), and system information (delayed message, message reference, possible duplicate message, and so on).</span></span> <span data-ttu-id="b3ce2-114">添加的 SWIFT 尾部还提供第三个块中，分隔"{s:"。</span><span class="sxs-lookup"><span data-stu-id="b3ce2-114">Trailers added by SWIFT also provide a third block, delimited by "{S:".</span></span> <span data-ttu-id="b3ce2-115">*SWIFT 用户手册*，"查找服务说明"主题，详细介绍块 5 的内容。</span><span class="sxs-lookup"><span data-stu-id="b3ce2-115">The *SWIFT User Handbook*, "FIN Service Description" topic, describes in detail the contents of block 5.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] <span data-ttu-id="b3ce2-116">不会验证内容块 s。</span><span class="sxs-lookup"><span data-stu-id="b3ce2-116">does not validate the contents of block S.</span></span>  
  
  <span data-ttu-id="b3ce2-117">实际 FIN 接口或 SWIFT 网络将追加尾部。</span><span class="sxs-lookup"><span data-stu-id="b3ce2-117">The actual FIN interface or the SWIFT network appends the trailers.</span></span> <span data-ttu-id="b3ce2-118">如果消息中包含尾部时[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收消息，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]携带消息尾部。</span><span class="sxs-lookup"><span data-stu-id="b3ce2-118">If a message contains a trailer when [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receives the message, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] carries the trailer with the message.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] <span data-ttu-id="b3ce2-119">如果消息不包含尾部不会引发错误时[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收的消息。</span><span class="sxs-lookup"><span data-stu-id="b3ce2-119">does not raise an error if a message does not contain a trailer when [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receives the message.</span></span> <span data-ttu-id="b3ce2-120">作为使用标头，所有尾部项，包括块本身，都是可选中[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b3ce2-120">As with headers, all of the trailer entries, including the blocks themselves, are optional in [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span>  
  
  <span data-ttu-id="b3ce2-121">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="b3ce2-121">This section contains:</span></span>  
  
- [<span data-ttu-id="b3ce2-122">用户尾部</span><span class="sxs-lookup"><span data-stu-id="b3ce2-122">User Trailers</span></span>](../../adapters-and-accelerators/accelerator-swift/user-trailers.md)  
  
- [<span data-ttu-id="b3ce2-123">系统尾部</span><span class="sxs-lookup"><span data-stu-id="b3ce2-123">System Trailers</span></span>](../../adapters-and-accelerators/accelerator-swift/system-trailers.md)  
  
## <a name="see-also"></a><span data-ttu-id="b3ce2-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="b3ce2-124">See Also</span></span>  
 [<span data-ttu-id="b3ce2-125">处理架构</span><span class="sxs-lookup"><span data-stu-id="b3ce2-125">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)