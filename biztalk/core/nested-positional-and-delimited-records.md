---
title: "嵌套位置和分隔记录 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1688f04-d3c7-492c-82f7-a734bec0e409
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccc3d994a3561f26df1bdffa7b547b1f647936a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="nested-positional-and-delimited-records"></a><span data-ttu-id="bc277-102">嵌套的位置和分隔记录</span><span class="sxs-lookup"><span data-stu-id="bc277-102">Nested Positional and Delimited Records</span></span>
<span data-ttu-id="bc277-103">中支持 Microsoft 的平面文件格式[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、 位置和分隔记录的某些组合允许和不允许其他人使用。</span><span class="sxs-lookup"><span data-stu-id="bc277-103">In the flat file formats supported by Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], some combinations of positional and delimited records are allowed and others are disallowed.</span></span> <span data-ttu-id="bc277-104">允许使用以下组合：</span><span class="sxs-lookup"><span data-stu-id="bc277-104">The following combinations are allowed:</span></span>  
  
-   <span data-ttu-id="bc277-105">平面文件中的分隔符用于确定所有记录及其从属记录之间的边界，平面文件中（可能有所不同）的分隔符用于在这些记录中分隔字段。</span><span class="sxs-lookup"><span data-stu-id="bc277-105">Flat files in which delimiters are used to determine the boundaries between all records and their subordinate records from each other, and in which (possibly different) delimiters are used to separate the fields within those records.</span></span>  
  
-   <span data-ttu-id="bc277-106">平面文件中所有记录、其从属记录及其字段之间的边界基于它们在文件中的位置根据预定义记录和字段长度来确定。</span><span class="sxs-lookup"><span data-stu-id="bc277-106">Flat files in which the boundaries between all records, their subordinate records, and their fields are determined based on their position within the file according to predefined record and field lengths.</span></span>  
  
-   <span data-ttu-id="bc277-107">平面文件中的分隔符用于确定文件中至少最外层一组记录之间的边界，平面文件中使用分隔和位置从属记录的组合。</span><span class="sxs-lookup"><span data-stu-id="bc277-107">Flat files in which delimiters are used to determine the boundaries between at least the outermost set of records in the file, and in which a mix of delimited and positional subordinate records are used.</span></span> <span data-ttu-id="bc277-108">分别使用分隔符或固定字段长度来确定分隔或位置从属记录中字段之间的边界。</span><span class="sxs-lookup"><span data-stu-id="bc277-108">Boundaries between the fields within a delimited or positional subordinate record are determined using either delimiters or fixed field lengths, respectively.</span></span> <span data-ttu-id="bc277-109">位置（从属）记录的从属记录必须也是位置记录；换句话说，文件的某一部分从分隔记录切换为位置记录后，该文件的整个从属部分必须是位置记录。</span><span class="sxs-lookup"><span data-stu-id="bc277-109">The subordinate records of a positional (subordinate) record must also be positional; in other words, once a portion of the file switches from delimited to positional records, that entire subordinate portion of the file must be positional.</span></span>  
  
 <span data-ttu-id="bc277-110">由于将导致解析多义性，因此只要出现位置记录，都禁止位置记录包含分隔从属记录。</span><span class="sxs-lookup"><span data-stu-id="bc277-110">Due to the parsing ambiguities that would result, positional records, wherever they occur, are prohibited from containing delimited subordinate records.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc277-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc277-111">See Also</span></span>  
 [<span data-ttu-id="bc277-112">注意事项时创建平面文件消息架构</span><span class="sxs-lookup"><span data-stu-id="bc277-112">Considerations When Creating Flat File Message Schemas</span></span>](../core/considerations-when-creating-flat-file-message-schemas.md)