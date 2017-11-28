---
title: "BizTalk Server 将 EDI 消息的发送 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4eaf1085-4244-4df2-9d89-52ebdf6bcbbc
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4727a407c28ede98bba67774576d4d43329a946
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-biztalk-server-sends-edi-messages"></a><span data-ttu-id="31fee-102">BizTalk Server 将 EDI 消息的发送</span><span class="sxs-lookup"><span data-stu-id="31fee-102">How BizTalk Server Sends EDI Messages</span></span>
<span data-ttu-id="31fee-103">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送 EDI 消息时，它将执行协议查找和架构发现、验证消息、发送确认（如果适合）并对 EDI 批处理进行序列化。</span><span class="sxs-lookup"><span data-stu-id="31fee-103">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends an EDI message, it performs agreement lookup and schema discovery, validates the message, sends an acknowledgment (if appropriate), and serializes the EDI batch.</span></span> <span data-ttu-id="31fee-104">此处理将由 EDI 发送管道中的 EDI 组装器执行。</span><span class="sxs-lookup"><span data-stu-id="31fee-104">This processing is performed by the EDI assembler in the EDI Send Pipeline.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="31fee-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="31fee-105">In This Section</span></span>  
  
-   [<span data-ttu-id="31fee-106">EDI 发送组件</span><span class="sxs-lookup"><span data-stu-id="31fee-106">EDI Send Components</span></span>](../core/edi-send-components.md)  
  
-   [<span data-ttu-id="31fee-107">协议解析和传出的 EDI 消息的架构确定</span><span class="sxs-lookup"><span data-stu-id="31fee-107">Agreement Resolution and Schema Determination for Outgoing EDI Messages</span></span>](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)  
  
-   [<span data-ttu-id="31fee-108">EDI 汇编器的工作原理</span><span class="sxs-lookup"><span data-stu-id="31fee-108">How the EDI Assembler Works</span></span>](../core/how-the-edi-assembler-works.md)  
  
-   [<span data-ttu-id="31fee-109">重写 EDI 标头</span><span class="sxs-lookup"><span data-stu-id="31fee-109">Overriding EDI Headers</span></span>](../core/overriding-edi-headers.md)  
  
-   [<span data-ttu-id="31fee-110">传出 EDI 消息的验证</span><span class="sxs-lookup"><span data-stu-id="31fee-110">Validation of Outgoing EDI Messages</span></span>](../core/validation-of-outgoing-edi-messages.md)  
  
-   [<span data-ttu-id="31fee-111">对传出的 EDI 消息进行批处理</span><span class="sxs-lookup"><span data-stu-id="31fee-111">Batching Outgoing EDI Messages</span></span>](../core/batching-outgoing-edi-messages.md)  
  
-   [<span data-ttu-id="31fee-112">处理收到的确认</span><span class="sxs-lookup"><span data-stu-id="31fee-112">Processing a Received Acknowledgment</span></span>](../core/processing-a-received-acknowledgment.md)