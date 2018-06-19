---
title: 段不中定义的事务集 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 914e333f-96e4-4094-880d-51a5f25915c3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2f0b330110ef08196681e54e543173c3f2bd0f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269517"
---
# <a name="segment-not-in-defined-transaction-set"></a><span data-ttu-id="45111-102">段不在定义的事务集中</span><span class="sxs-lookup"><span data-stu-id="45111-102">Segment Not In Defined Transaction set</span></span>
## <a name="details"></a><span data-ttu-id="45111-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="45111-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="45111-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="45111-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="45111-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="45111-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="45111-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="45111-106">Event ID</span></span>|-|  
|<span data-ttu-id="45111-107">事件源</span><span class="sxs-lookup"><span data-stu-id="45111-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="45111-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="45111-108"> EDI</span></span>|  
|<span data-ttu-id="45111-109">组件</span><span class="sxs-lookup"><span data-stu-id="45111-109">Component</span></span>|<span data-ttu-id="45111-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="45111-110">EDI Engine</span></span>|  
|<span data-ttu-id="45111-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="45111-111">Symbolic Name</span></span>|<span data-ttu-id="45111-112">X12SegmentNotInDefinedTSDescription</span><span class="sxs-lookup"><span data-stu-id="45111-112">X12SegmentNotInDefinedTSDescription</span></span>|  
|<span data-ttu-id="45111-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="45111-113">Message Text</span></span>|<span data-ttu-id="45111-114">段不在定义的事务集中</span><span class="sxs-lookup"><span data-stu-id="45111-114">Segment Not In Defined Transaction set</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="45111-115">解释</span><span class="sxs-lookup"><span data-stu-id="45111-115">Explanation</span></span>  
 <span data-ttu-id="45111-116">此错误/警告/信息事件表明接收管道无法处理传入的 X12 交换，因为该交换中的事务集不包含文档架构所需的段。</span><span class="sxs-lookup"><span data-stu-id="45111-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because a transaction set in that interchange does not contain a segment required by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="45111-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="45111-117">User Action</span></span>  
 <span data-ttu-id="45111-118">若要解决此错误，请让交换的发送方将所需的段添加到交换的事务集中，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="45111-118">To resolve this error, have the sender of the interchange add the required segment to the transaction set in the interchange, and then resend the interchange.</span></span>