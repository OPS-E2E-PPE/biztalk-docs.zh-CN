---
title: 分隔记录注意事项 |Microsoft 文档
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
ms.openlocfilehash: bc6cbd642717b485a1be5cefab07f6a8298d638a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238389"
---
# <a name="delimited-record-considerations"></a><span data-ttu-id="01ea5-102">分隔记录的注意事项</span><span class="sxs-lookup"><span data-stu-id="01ea5-102">Delimited Record Considerations</span></span>
<span data-ttu-id="01ea5-103">有大量你应时需要牢记使用带分隔符的注意事项**记录**在你的架构内的节点。</span><span class="sxs-lookup"><span data-stu-id="01ea5-103">There are a number of considerations that you should keep in mind when working with delimited **Record** nodes within your schemas.</span></span> <span data-ttu-id="01ea5-104">这包括有关从属节点相对于其分隔符，在其中你可以选择省略分隔符时将平面文件消息表示形式，并分隔限制有关的混用例的顺序的注意事项和位置的记录。</span><span class="sxs-lookup"><span data-stu-id="01ea5-104">This includes the considerations about the order of subordinate nodes relative to their delimiters, cases in which you can choose to omit delimiters when assembling the flat file representation of a message, and restrictions regarding the intermixing of delimited and positional records.</span></span> <span data-ttu-id="01ea5-105">本部分提供了有关上述注意事项的信息。</span><span class="sxs-lookup"><span data-stu-id="01ea5-105">This section provides information about these considerations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="01ea5-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="01ea5-106">In This Section</span></span>  
  
-   [<span data-ttu-id="01ea5-107">分隔记录中处理的标记</span><span class="sxs-lookup"><span data-stu-id="01ea5-107">Tag Handling in Delimited Records</span></span>](../core/tag-handling-in-delimited-records.md)  
  
-   [<span data-ttu-id="01ea5-108">子顺序注意事项</span><span class="sxs-lookup"><span data-stu-id="01ea5-108">Child Order Considerations</span></span>](../core/child-order-considerations.md)  
  
-   [<span data-ttu-id="01ea5-109">分隔符保留和抑制</span><span class="sxs-lookup"><span data-stu-id="01ea5-109">Delimiter Preservation and Suppression</span></span>](../core/delimiter-preservation-and-suppression.md)