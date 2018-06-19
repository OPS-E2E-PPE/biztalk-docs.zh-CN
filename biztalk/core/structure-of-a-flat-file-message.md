---
title: 平面文件消息的结构 |Microsoft 文档
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
ms.openlocfilehash: badb8aacf6f2ed8ce9e38f1ea6bbe432a1d3b89e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278933"
---
# <a name="structure-of-a-flat-file-message"></a><span data-ttu-id="92b27-102">平面文件消息的结构</span><span class="sxs-lookup"><span data-stu-id="92b27-102">Structure of a Flat File Message</span></span>
<span data-ttu-id="92b27-103">Microsoft 的上下文中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，平面文件实例消息是一个文本文件，可以包含三个逻辑部分： 标头、 正文和尾部，按此顺序。</span><span class="sxs-lookup"><span data-stu-id="92b27-103">In the context of Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], a flat file instance message is a text file that can contain three logical parts: a header, a body, and a trailer, in that order.</span></span> <span data-ttu-id="92b27-104">其中，头部和尾部均是可选的。</span><span class="sxs-lookup"><span data-stu-id="92b27-104">Both the header and the trailer are optional.</span></span> <span data-ttu-id="92b27-105">以下示例显示的平面文件实例消息由这三个部分组成（其正文部分以粗体显示）：</span><span class="sxs-lookup"><span data-stu-id="92b27-105">The following example shows a flat file instance message that consists of all three parts, with the body shown in bold type.</span></span>  
  
```  
Microsoft Corporation  
One Microsoft Way  
Redmond, WA 98033  
  
TRANSACTION-1111,1  
  
```  
  
 <span data-ttu-id="92b27-106">为使平面文件拆装器可正确区分平面文件实例消息的头部、正文和尾部，您必须为每部分分别创建和配置单独的架构。</span><span class="sxs-lookup"><span data-stu-id="92b27-106">For the flat file disassembler to correctly distinguish the header, the body, and the trailer of a flat file instance message, you must create and configure a separate schema for each of them.</span></span>  
  
 <span data-ttu-id="92b27-107">在平面文件实例消息的特定部分中，不同的数据项将分成不同的记录，而记录本身可包含子记录，并最终包含各个数据项（称为字段）。</span><span class="sxs-lookup"><span data-stu-id="92b27-107">Within a particular part of a flat file instance message, different items of data are grouped into records, which themselves can contain subrecords and ultimately the individual items of data, known as fields.</span></span> <span data-ttu-id="92b27-108">使用以下两种不同的基本方法之一，可以将这些记录和字段相互区分开。</span><span class="sxs-lookup"><span data-stu-id="92b27-108">These records and fields are distinguished from each other using one of two different basic methodologies.</span></span> <span data-ttu-id="92b27-109">第一种方法（称为位置法）将每个数据项定义为具有预先确定的长度，并使用填充字符将较短的数据项加长到所需长度。</span><span class="sxs-lookup"><span data-stu-id="92b27-109">The first methodology, known as positional, defines each item of data to be of a pre-established length, with pad characters being used to bring a shorter item of data up to its expected length.</span></span> <span data-ttu-id="92b27-110">第二种方法（称为分隔法）使用一个或多个特殊字符将数据项彼此分隔开。</span><span class="sxs-lookup"><span data-stu-id="92b27-110">The second methodology, known as delimited, uses one or more special characters to separate items of data from each other.</span></span> <span data-ttu-id="92b27-111">此方法不需要使用其他方法所需的多余填充字符，但当数据本身包含已用作分隔符的字符或字符序列时，将需要注意某些特殊事项。</span><span class="sxs-lookup"><span data-stu-id="92b27-111">This methodology avoids the need for otherwise superfluous pad characters, but introduces some special considerations when the data itself contains the character or sequence of characters being used as a delimiter.</span></span>  
  
 <span data-ttu-id="92b27-112">本部分的其余内容对于 BizTalk Server 如何处理平面文件实例消息的头部、正文和尾部提供了高级概述，具体来说，即介绍了 BizTalk Server 将如何决定是否使用可选部分，以及如何分隔入站平面文件实例消息的各个部分和如何将出站平面文件实例消息的各个部分组合起来。</span><span class="sxs-lookup"><span data-stu-id="92b27-112">The remainder of this section provides a high-level overview of how BizTalk Server handles headers, bodies, and trailers in flat file instance messages, and specifically, how it decides whether the optional parts are present, and how it separates the parts of inbound flat file instance messages and combines the parts of outbound flat file instance messages.</span></span> <span data-ttu-id="92b27-113">本部分还提供了有关使用位置记录和字段的平面文件实例消息与使用分隔记录和字段的平面文件实例消息之间的差异的其他信息。</span><span class="sxs-lookup"><span data-stu-id="92b27-113">This section also provides additional information about the differences between flat file instance messages that employ positional records and fields and flat file instance messages that employ delimited records and fields.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="92b27-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="92b27-114">In This Section</span></span>  
  
-   [<span data-ttu-id="92b27-115">平面文件消息标头</span><span class="sxs-lookup"><span data-stu-id="92b27-115">Flat File Message Headers</span></span>](../core/flat-file-message-headers.md)  
  
-   [<span data-ttu-id="92b27-116">平面文件消息正文</span><span class="sxs-lookup"><span data-stu-id="92b27-116">Flat File Message Bodies</span></span>](../core/flat-file-message-bodies.md)  
  
-   [<span data-ttu-id="92b27-117">平面文件消息拖车安排</span><span class="sxs-lookup"><span data-stu-id="92b27-117">Flat File Message Trailers</span></span>](../core/flat-file-message-trailers.md)  
  
-   [<span data-ttu-id="92b27-118">包含的位置记录的平面文件消息</span><span class="sxs-lookup"><span data-stu-id="92b27-118">Flat File Messages with Positional Records</span></span>](../core/flat-file-messages-with-positional-records.md)  
  
-   [<span data-ttu-id="92b27-119">分隔记录的平面文件消息</span><span class="sxs-lookup"><span data-stu-id="92b27-119">Flat File Messages with Delimited Records</span></span>](../core/flat-file-messages-with-delimited-records.md)  
  
-   [<span data-ttu-id="92b27-120">迁移的平面文件记录</span><span class="sxs-lookup"><span data-stu-id="92b27-120">Migrating Flat File Records</span></span>](../core/migrating-flat-file-records.md)