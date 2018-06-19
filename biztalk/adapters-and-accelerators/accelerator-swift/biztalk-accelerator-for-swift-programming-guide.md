---
title: BizTalk Accelerator for SWIFT 编程指南 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developing, programming guide
- programming guide
ms.assetid: b4ef9a7b-2812-4ac0-a59c-f47ba84d2551
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac316a8eec53f9323c54f2025f25f5f4d9e93512
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209021"
---
# <a name="biztalk-accelerator-for-swift-programming-guide"></a><span data-ttu-id="a6288-102">BizTalk Accelerator for SWIFT 编程指南</span><span class="sxs-lookup"><span data-stu-id="a6288-102">BizTalk Accelerator for SWIFT Programming Guide</span></span>
<span data-ttu-id="a6288-103">本部分说明了概念和过程的开发人员编写代码与[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a6288-103">This section explains concepts and procedures for developers writing code with [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="a6288-104">将本指南中结合使用[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]文档。</span><span class="sxs-lookup"><span data-stu-id="a6288-104">Use this guide in conjunction with the [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6288-105">阅读此指南之前，你应该熟悉[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]开发， [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]，和[运行时，消息修复、 FIN 响应和消息传送](../../adapters-and-accelerators/accelerator-swift/runtime-message-repair-fin-response-and-messaging.md)。</span><span class="sxs-lookup"><span data-stu-id="a6288-105">Before reading this guide, you should be familiar with [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] development, [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)], and [Runtime, message repair, FIN response, and messaging](../../adapters-and-accelerators/accelerator-swift/runtime-message-repair-fin-response-and-messaging.md).</span></span>  
  
 <span data-ttu-id="a6288-106">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="a6288-106">This section contains:</span></span>  
  
-   [<span data-ttu-id="a6288-107">使用架构</span><span class="sxs-lookup"><span data-stu-id="a6288-107">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)  
  
-   [<span data-ttu-id="a6288-108">使用 SWIFT 反汇编程序和汇编程序</span><span class="sxs-lookup"><span data-stu-id="a6288-108">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)  
  
-   [<span data-ttu-id="a6288-109">使用失败的邮件订阅</span><span class="sxs-lookup"><span data-stu-id="a6288-109">Working with Failed Message Subscriptions</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)