---
title: 平面文件消息的结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00f2adf6-a47c-498b-b5ae-c6bd55bafceb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dfb2e5f159ad3b792393ad828e0addc7907030c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244120"
---
# <a name="structure-of-a-flat-file-message"></a><span data-ttu-id="7f283-102">平面文件消息的结构</span><span class="sxs-lookup"><span data-stu-id="7f283-102">Structure of a Flat File Message</span></span>
<span data-ttu-id="7f283-103">Microsoft 的上下文中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，平面文件实例消息是一个文本文件，可以包含三个逻辑部分： 一个标头、 正文和尾部，按该顺序。</span><span class="sxs-lookup"><span data-stu-id="7f283-103">In the context of Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], a flat file instance message is a text file that can contain three logical parts: a header, a body, and a trailer, in that order.</span></span> <span data-ttu-id="7f283-104">标头和尾部是可选的。</span><span class="sxs-lookup"><span data-stu-id="7f283-104">Both the header and the trailer are optional.</span></span> <span data-ttu-id="7f283-105">下面的示例演示平面文件实例消息，它包含具有以粗体显示的正文的所有三个部分。</span><span class="sxs-lookup"><span data-stu-id="7f283-105">The following example shows a flat file instance message that consists of all three parts, with the body shown in bold type.</span></span>  
  
```  
Microsoft Corporation  
One Microsoft Way  
Redmond, WA 98033  
  
TRANSACTION-1111,1  
  
```  
  
 <span data-ttu-id="7f283-106">有关以正确区分使用标头、 正文和尾部的平面文件实例消息的平面文件拆装器，必须创建并配置为每个单独的架构。</span><span class="sxs-lookup"><span data-stu-id="7f283-106">For the flat file disassembler to correctly distinguish the header, the body, and the trailer of a flat file instance message, you must create and configure a separate schema for each of them.</span></span>  
  
 <span data-ttu-id="7f283-107">数据的不同项的分组中的平面文件实例消息的特定部分，为记录，本身可以包含子记录，并最终称为字段的数据的各个项。</span><span class="sxs-lookup"><span data-stu-id="7f283-107">Within a particular part of a flat file instance message, different items of data are grouped into records, which themselves can contain subrecords and ultimately the individual items of data, known as fields.</span></span> <span data-ttu-id="7f283-108">这些记录和字段相互区从每个其他使用两个不同的基本方法之一。</span><span class="sxs-lookup"><span data-stu-id="7f283-108">These records and fields are distinguished from each other using one of two different basic methodologies.</span></span> <span data-ttu-id="7f283-109">第一种方法，称为位置法，定义要为预先确定的长度，以将数据保持其预期的长度最短的数据项的填充字符的数据的每个项。</span><span class="sxs-lookup"><span data-stu-id="7f283-109">The first methodology, known as positional, defines each item of data to be of a pre-established length, with pad characters being used to bring a shorter item of data up to its expected length.</span></span> <span data-ttu-id="7f283-110">第二个方法，名为带分隔符、 使用一个或多个特殊字符来分隔每个项的数据。</span><span class="sxs-lookup"><span data-stu-id="7f283-110">The second methodology, known as delimited, uses one or more special characters to separate items of data from each other.</span></span> <span data-ttu-id="7f283-111">此方法不需要使用否则为多余填充字符，但当数据本身包含的字符或字符用作分隔符的序列时引入了一些特殊注意事项。</span><span class="sxs-lookup"><span data-stu-id="7f283-111">This methodology avoids the need for otherwise superfluous pad characters, but introduces some special considerations when the data itself contains the character or sequence of characters being used as a delimiter.</span></span>  
  
 <span data-ttu-id="7f283-112">本部分的余下部分提供了 BizTalk Server 如何处理标头、 正文和尾部平面文件实例消息中的高级概述，具体而言，如何决定可选部分是否存在，以及它如何分隔的部分入站平面文件实例消息，并将组合出站平面文件实例消息的组成部分。</span><span class="sxs-lookup"><span data-stu-id="7f283-112">The remainder of this section provides a high-level overview of how BizTalk Server handles headers, bodies, and trailers in flat file instance messages, and specifically, how it decides whether the optional parts are present, and how it separates the parts of inbound flat file instance messages and combines the parts of outbound flat file instance messages.</span></span> <span data-ttu-id="7f283-113">本部分还提供有关使用位置记录和字段的平面文件实例消息和平面文件实例消息与使用分隔记录和字段之间的区别的其他信息。</span><span class="sxs-lookup"><span data-stu-id="7f283-113">This section also provides additional information about the differences between flat file instance messages that employ positional records and fields and flat file instance messages that employ delimited records and fields.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7f283-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="7f283-114">In This Section</span></span>  
  
-   [<span data-ttu-id="7f283-115">平面文件消息标头</span><span class="sxs-lookup"><span data-stu-id="7f283-115">Flat File Message Headers</span></span>](../core/flat-file-message-headers.md)  
  
-   [<span data-ttu-id="7f283-116">平面文件消息正文</span><span class="sxs-lookup"><span data-stu-id="7f283-116">Flat File Message Bodies</span></span>](../core/flat-file-message-bodies.md)  
  
-   [<span data-ttu-id="7f283-117">平面文件消息尾部</span><span class="sxs-lookup"><span data-stu-id="7f283-117">Flat File Message Trailers</span></span>](../core/flat-file-message-trailers.md)  
  
-   [<span data-ttu-id="7f283-118">带有位置记录的平面文件消息</span><span class="sxs-lookup"><span data-stu-id="7f283-118">Flat File Messages with Positional Records</span></span>](../core/flat-file-messages-with-positional-records.md)  
  
-   [<span data-ttu-id="7f283-119">带有分隔记录的平面文件消息</span><span class="sxs-lookup"><span data-stu-id="7f283-119">Flat File Messages with Delimited Records</span></span>](../core/flat-file-messages-with-delimited-records.md)  
  
-   [<span data-ttu-id="7f283-120">迁移平面文件记录</span><span class="sxs-lookup"><span data-stu-id="7f283-120">Migrating Flat File Records</span></span>](../core/migrating-flat-file-records.md)