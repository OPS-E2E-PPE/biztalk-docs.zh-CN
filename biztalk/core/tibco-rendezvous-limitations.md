---
title: "TIBCO 集合限制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TIBCO Rendezvous, limitations
ms.assetid: 8e210457-2887-43f9-a249-be1daa6ee4eb
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 717188e42450d13dee92364cd9c673aaaf48eaf6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tibco-rendezvous-limitations"></a><span data-ttu-id="72de5-102">TIBCO Rendezvous 限制</span><span class="sxs-lookup"><span data-stu-id="72de5-102">TIBCO Rendezvous Limitations</span></span>
<span data-ttu-id="72de5-103">在 TIBCO Rendezvous 中，不能保证字段名的唯一性。</span><span class="sxs-lookup"><span data-stu-id="72de5-103">In TIBCO Rendezvous, field name uniqueness is not guaranteed.</span></span> <span data-ttu-id="72de5-104">如果 TIBCO Rendezvous 消息包含两个相同的名称字段，则结果 XML 无效。</span><span class="sxs-lookup"><span data-stu-id="72de5-104">If a TIBCO Rendezvous message contains two field names that are the same, the resulting XML is not valid.</span></span>  
  
 <span data-ttu-id="72de5-105">其他限制包括：</span><span class="sxs-lookup"><span data-stu-id="72de5-105">Other limitations include the following:</span></span>  
  
-   <span data-ttu-id="72de5-106">未提供字段排序功能。</span><span class="sxs-lookup"><span data-stu-id="72de5-106">Field ordering/sorting is not provided.</span></span>  
  
-   <span data-ttu-id="72de5-107">根据 TIBCO Rendezvous 文档，使用者名称中不会使用非打印的字符；但是仍可能使用这样的字符。</span><span class="sxs-lookup"><span data-stu-id="72de5-107">According to TIBCO Rendezvous documentation, non-printable characters are not used in subject names; however, it is still possible that such characters are used.</span></span> <span data-ttu-id="72de5-108">用于 TIBCO Rendezvous 的 BizTalk 适配器不支持包含这些字符的使用者名称。</span><span class="sxs-lookup"><span data-stu-id="72de5-108">BizTalk Adapter for TIBCO Rendezvous does not support subject names containing those characters.</span></span>  
  
-   <span data-ttu-id="72de5-109">不支持与后台程序的安全连接。</span><span class="sxs-lookup"><span data-stu-id="72de5-109">Secure connection to daemons is not supported.</span></span>  
  
-   <span data-ttu-id="72de5-110">不支持自定义数据类型。</span><span class="sxs-lookup"><span data-stu-id="72de5-110">Custom data types are not supported.</span></span>  
  
-   <span data-ttu-id="72de5-111">传输端不支持经过验证的消息。</span><span class="sxs-lookup"><span data-stu-id="72de5-111">Certified Messaging is not supported on the transmit side.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72de5-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72de5-112">See Also</span></span>  
 <span data-ttu-id="72de5-113">[TIBCO 会合概念](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="72de5-113">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="72de5-114">入门</span><span class="sxs-lookup"><span data-stu-id="72de5-114">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)