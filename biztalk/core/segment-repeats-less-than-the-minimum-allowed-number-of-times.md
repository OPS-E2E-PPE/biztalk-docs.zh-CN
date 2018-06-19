---
title: 小于允许的最小次数段重复 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c8ca6c3d-f923-49bc-b5d9-65dc2d7adab1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee7aeb488fb2f8634fba73e7ddf3f44cd02a6529
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269933"
---
# <a name="segment-repeats-less-than-the-minimum-allowed-number-of-times"></a><span data-ttu-id="bf0bd-102">段重复次数低于所允许的最少次数</span><span class="sxs-lookup"><span data-stu-id="bf0bd-102">Segment repeats less than the minimum allowed number of times</span></span>
## <a name="details"></a><span data-ttu-id="bf0bd-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="bf0bd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bf0bd-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="bf0bd-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="bf0bd-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="bf0bd-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="bf0bd-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="bf0bd-106">Event ID</span></span>|-|  
|<span data-ttu-id="bf0bd-107">事件源</span><span class="sxs-lookup"><span data-stu-id="bf0bd-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="bf0bd-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="bf0bd-108"> EDI</span></span>|  
|<span data-ttu-id="bf0bd-109">组件</span><span class="sxs-lookup"><span data-stu-id="bf0bd-109">Component</span></span>|<span data-ttu-id="bf0bd-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="bf0bd-110">EDI Engine</span></span>|  
|<span data-ttu-id="bf0bd-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="bf0bd-111">Symbolic Name</span></span>|<span data-ttu-id="bf0bd-112">X12SeSegmentRepeatsLessTimesDescription</span><span class="sxs-lookup"><span data-stu-id="bf0bd-112">X12SeSegmentRepeatsLessTimesDescription</span></span>|  
|<span data-ttu-id="bf0bd-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="bf0bd-113">Message Text</span></span>|<span data-ttu-id="bf0bd-114">段重复次数低于所允许的最少次数</span><span class="sxs-lookup"><span data-stu-id="bf0bd-114">Segment repeats less than the minimum allowed number of times</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bf0bd-115">解释</span><span class="sxs-lookup"><span data-stu-id="bf0bd-115">Explanation</span></span>  
 <span data-ttu-id="bf0bd-116">此错误/警告/信息事件表明接收管道无法处理传入的 X12 交换，因为交换中的段未重复文档架构所需的最少次数。</span><span class="sxs-lookup"><span data-stu-id="bf0bd-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because a segment in the interchange does not repeat the minimum number of times required by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bf0bd-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="bf0bd-117">User Action</span></span>  
 <span data-ttu-id="bf0bd-118">若要解决此错误，请让交换的发送方设置段的重复，以便该段重复文档架构所需的最少次数，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="bf0bd-118">To resolve this error, have the sender of the interchange as repetition of the segment so that it repeats at least the minimum number of times required by the document schema, and then resend the interchange.</span></span>