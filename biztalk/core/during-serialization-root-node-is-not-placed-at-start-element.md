---
title: 在序列化期间根节点未位于起始元素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ea4aa6f-0f9c-4b7b-b7f6-24a5ce954048
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4403e9fb895ca05d4438f1e280d79008519918d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350676"
---
# <a name="during-serialization-root-node-is-not-placed-at-start-element"></a><span data-ttu-id="3ab93-102">在序列化期间根节点是未位于起始元素</span><span class="sxs-lookup"><span data-stu-id="3ab93-102">During serialization root node is not placed at start element</span></span>
## <a name="details"></a><span data-ttu-id="3ab93-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="3ab93-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="3ab93-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="3ab93-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="3ab93-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="3ab93-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="3ab93-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="3ab93-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="3ab93-107">事件源</span><span class="sxs-lookup"><span data-stu-id="3ab93-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="3ab93-108">EDI</span><span class="sxs-lookup"><span data-stu-id="3ab93-108">EDI</span></span> |
|    <span data-ttu-id="3ab93-109">组件</span><span class="sxs-lookup"><span data-stu-id="3ab93-109">Component</span></span>    |                                       <span data-ttu-id="3ab93-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="3ab93-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="3ab93-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="3ab93-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="3ab93-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="3ab93-112">Message Text</span></span>   |             <span data-ttu-id="3ab93-113">在序列化期间根节点是未位于起始元素</span><span class="sxs-lookup"><span data-stu-id="3ab93-113">During serialization root node is not placed at start element</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="3ab93-114">解释</span><span class="sxs-lookup"><span data-stu-id="3ab93-114">Explanation</span></span>  
 <span data-ttu-id="3ab93-115">此错误/警告/信息事件表明接收管道不无法处理传入的交换，因为事务集未以 ST 或 UNH 标头开头。</span><span class="sxs-lookup"><span data-stu-id="3ab93-115">This Error/Warning/Information event indicates that the receive pipeline could not process an incoming interchange because the transaction set does not start with an ST or UNH header.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3ab93-116">用户操作</span><span class="sxs-lookup"><span data-stu-id="3ab93-116">User Action</span></span>  
 <span data-ttu-id="3ab93-117">若要解决此错误，请确保每个交换中事务集开头 ST 段 （对于 X12 交换） 或 UNH 段 （对于 EDIFACT 交换），然后重新提交交换。</span><span class="sxs-lookup"><span data-stu-id="3ab93-117">To resolve this error, ensure that each of the transaction sets in an interchange starts with an ST segment (for X12 interchanges) or an UNH segment (for EDIFACT interchanges), and then resubmit the interchange.</span></span>