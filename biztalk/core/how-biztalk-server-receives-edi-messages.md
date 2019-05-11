---
title: BizTalk Server 如何接收 EDI 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f3bb88c-9226-4791-b100-ba68dea45278
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9365904b90e3e21f9903be684b33327a3fd037d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387481"
---
# <a name="how-biztalk-server-receives-edi-messages"></a><span data-ttu-id="bc96c-102">BizTalk Server 如何接收 EDI 消息</span><span class="sxs-lookup"><span data-stu-id="bc96c-102">How BizTalk Server Receives EDI Messages</span></span>
<span data-ttu-id="bc96c-103">当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收 EDI 消息时，它执行贸易合作伙伴协议查找和架构发现，验证消息、 发送确认 （如果适用），并解析 EDI 批处理。</span><span class="sxs-lookup"><span data-stu-id="bc96c-103">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives an EDI message, it performs trading partner agreement lookup and schema discovery, validates the message, sends an acknowledgment (if appropriate), and parses the EDI batch.</span></span> <span data-ttu-id="bc96c-104">此处理将由 EDI 接收管道中的 EDI 拆装器执行。</span><span class="sxs-lookup"><span data-stu-id="bc96c-104">This processing is performed by the EDI disassembler in the EDI Receive Pipeline.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bc96c-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="bc96c-105">In This Section</span></span>  
  
-   [<span data-ttu-id="bc96c-106">EDI 接收组件</span><span class="sxs-lookup"><span data-stu-id="bc96c-106">EDI Receive Components</span></span>](../core/edi-receive-components.md)  
  
-   [<span data-ttu-id="bc96c-107">接收到的 EDI 消息的协议解析、架构发现和授权</span><span class="sxs-lookup"><span data-stu-id="bc96c-107">Agreement Resolution, Schema Discovery, and Authorization for Received EDI Messages</span></span>](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)  
  
-   [<span data-ttu-id="bc96c-108">EDI 反汇编程序的工作原理</span><span class="sxs-lookup"><span data-stu-id="bc96c-108">How the EDI Disassembler Works</span></span>](../core/how-the-edi-disassembler-works.md)  
  
-   [<span data-ttu-id="bc96c-109">验证收到的 EDI 消息</span><span class="sxs-lookup"><span data-stu-id="bc96c-109">Validation of Received EDI Messages</span></span>](../core/validation-of-received-edi-messages.md)  
  
-   [<span data-ttu-id="bc96c-110">发送 EDI 确认</span><span class="sxs-lookup"><span data-stu-id="bc96c-110">Sending an EDI Acknowledgment</span></span>](../core/sending-an-edi-acknowledgment.md)  
  
-   [<span data-ttu-id="bc96c-111">处理传入批</span><span class="sxs-lookup"><span data-stu-id="bc96c-111">Processing Incoming Batches</span></span>](../core/processing-incoming-batches.md)