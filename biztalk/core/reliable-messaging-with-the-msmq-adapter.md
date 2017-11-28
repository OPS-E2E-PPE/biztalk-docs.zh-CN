---
title: "使用 MSMQ 适配器可靠消息传递 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, reliability
- reliability
- reliability, MSMQ adapters
- MSMQ adapters, reliability
- reliability, messages
ms.assetid: 1a4b4f77-c508-4c3f-82f9-5722d0af6c63
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc90ce4619527a6c53cbaf5a2546cb8708362b65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="reliable-messaging-with-the-msmq-adapter"></a><span data-ttu-id="da0a5-102">使用 MSMQ 适配器可靠消息传递</span><span class="sxs-lookup"><span data-stu-id="da0a5-102">Reliable Messaging with the MSMQ Adapter</span></span>
<span data-ttu-id="da0a5-103">通过使用特定的配置设置以及使用事务，可以提高使用 MSMQ 适配器发送和接收消息的可靠性。</span><span class="sxs-lookup"><span data-stu-id="da0a5-103">You can improve the reliability of sending and receiving messages with the MSMQ adapter by using particular configuration settings and by using transactions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da0a5-104">如果不使用事务，则在计算机发生故障时将丢失群集配置中的消息。</span><span class="sxs-lookup"><span data-stu-id="da0a5-104">If you do not use transactions, you can lose messages in clustered configurations if a computer fails.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="da0a5-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="da0a5-105">In This Section</span></span>  
  
-   [<span data-ttu-id="da0a5-106">使用 MSMQ 适配器可靠消息传递的属性</span><span class="sxs-lookup"><span data-stu-id="da0a5-106">Properties for Reliable Messaging with the MSMQ Adapter</span></span>](../core/properties-for-reliable-messaging-with-the-msmq-adapter.md)  
  
-   [<span data-ttu-id="da0a5-107">使用 MSMQ 适配器处理的事务</span><span class="sxs-lookup"><span data-stu-id="da0a5-107">Transaction Handling with the MSMQ Adapter</span></span>](../core/transaction-handling-with-the-msmq-adapter.md)