---
title: 分隔记录注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f93dd94-6ab1-4ae0-801d-e44e722d6f09
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98c42d1307340dfad47933fbe1e9bfcc1c2256dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352187"
---
# <a name="delimited-record-considerations"></a><span data-ttu-id="33715-102">分隔记录注意事项</span><span class="sxs-lookup"><span data-stu-id="33715-102">Delimited Record Considerations</span></span>
<span data-ttu-id="33715-103">有一些注意事项，您应考虑使用时分隔**记录**节点在架构中的。</span><span class="sxs-lookup"><span data-stu-id="33715-103">There are a number of considerations that you should keep in mind when working with delimited **Record** nodes within your schemas.</span></span> <span data-ttu-id="33715-104">这包括有关相对于其分隔符，情况下在其中可以选择在组装平面文件表示形式的一条消息，忽略的分隔符和限制有关的混合分隔从属节点的顺序的注意事项和位置记录。</span><span class="sxs-lookup"><span data-stu-id="33715-104">This includes the considerations about the order of subordinate nodes relative to their delimiters, cases in which you can choose to omit delimiters when assembling the flat file representation of a message, and restrictions regarding the intermixing of delimited and positional records.</span></span> <span data-ttu-id="33715-105">本部分提供有关这些注意事项的信息。</span><span class="sxs-lookup"><span data-stu-id="33715-105">This section provides information about these considerations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="33715-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="33715-106">In This Section</span></span>  
  
-   [<span data-ttu-id="33715-107">分隔记录中的标记处理</span><span class="sxs-lookup"><span data-stu-id="33715-107">Tag Handling in Delimited Records</span></span>](../core/tag-handling-in-delimited-records.md)  
  
-   [<span data-ttu-id="33715-108">子顺序的注意事项</span><span class="sxs-lookup"><span data-stu-id="33715-108">Child Order Considerations</span></span>](../core/child-order-considerations.md)  
  
-   [<span data-ttu-id="33715-109">分隔符的保留和取消</span><span class="sxs-lookup"><span data-stu-id="33715-109">Delimiter Preservation and Suppression</span></span>](../core/delimiter-preservation-and-suppression.md)