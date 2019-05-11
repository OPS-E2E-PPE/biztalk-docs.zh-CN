---
title: EDI 事务集消息结构元素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: caea8408-c09c-4525-a9c9-18abe4432594
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90a76be641269193386d6fb7443bcd7daaed28f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350176"
---
# <a name="edi-transaction-set-message-structural-element"></a><span data-ttu-id="6d696-102">EDI 事务集消息结构元素</span><span class="sxs-lookup"><span data-stu-id="6d696-102">EDI Transaction Set-Message Structural Element</span></span>
<span data-ttu-id="6d696-103">事务集（在 X12 编码中）或消息（在 EDIFACT 编码中）包含构成消息数据的段。</span><span class="sxs-lookup"><span data-stu-id="6d696-103">The transaction set (in X12 encoding) or message (in EDIFACT encoding) contains segments that make up the message data.</span></span> <span data-ttu-id="6d696-104">事务集由标头、数据段集合和尾部组成。</span><span class="sxs-lookup"><span data-stu-id="6d696-104">The transaction set consists of a header, a collection of data segments, and a trailer.</span></span> <span data-ttu-id="6d696-105">事务集中提供了处理事务所需的所有详细信息。</span><span class="sxs-lookup"><span data-stu-id="6d696-105">All details that are required to process the transaction are available within the transaction set.</span></span>  
  
 <span data-ttu-id="6d696-106">事务集必须以 ST 事务集标头（在 X12 中）或 UNH 消息标头（在 EDIFACT 中）开始，</span><span class="sxs-lookup"><span data-stu-id="6d696-106">A transaction set must start with a ST Transaction Set Header (in X12) or a UNH Message Header (in EDIFACT).</span></span> <span data-ttu-id="6d696-107">且必须以 SE 事务集尾部（在 X12 中）或 UNT 消息尾部（在 EDIFACT 中）结束。</span><span class="sxs-lookup"><span data-stu-id="6d696-107">It must end with a SE Transaction Set Trailer (in X12) or a UNT Message Trailer (in EDIFACT).</span></span> <span data-ttu-id="6d696-108">尾部提供包括标头和尾部段在内的数据段的计数。</span><span class="sxs-lookup"><span data-stu-id="6d696-108">The trailer provides a count of the data segments that includes the header and trailer segments.</span></span>  
  
 <span data-ttu-id="6d696-109">事务集可以包含一个或多个循环，这些循环是重复相关段的集合所必需的。</span><span class="sxs-lookup"><span data-stu-id="6d696-109">A transaction set can contain one or more loops, which are required to repeat a collection of related segments.</span></span>