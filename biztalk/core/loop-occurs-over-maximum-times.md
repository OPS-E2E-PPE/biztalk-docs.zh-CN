---
title: "通过最大时间将会发生循环 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0ac9f5d3-04ec-4c40-8a1f-17ef0b143cda
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 827ab88a2676cd052ee1ea3ba3a4bd7bd80f1912
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="loop-occurs-over-maximum-times"></a><span data-ttu-id="e9bed-102">循环次数超过最大次数</span><span class="sxs-lookup"><span data-stu-id="e9bed-102">Loop Occurs Over Maximum Times</span></span>
## <a name="details"></a><span data-ttu-id="e9bed-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e9bed-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e9bed-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e9bed-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e9bed-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="e9bed-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="e9bed-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e9bed-106">Event ID</span></span>|-|  
|<span data-ttu-id="e9bed-107">事件源</span><span class="sxs-lookup"><span data-stu-id="e9bed-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e9bed-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="e9bed-108"> EDI</span></span>|  
|<span data-ttu-id="e9bed-109">组件</span><span class="sxs-lookup"><span data-stu-id="e9bed-109">Component</span></span>|<span data-ttu-id="e9bed-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="e9bed-110">EDI Engine</span></span>|  
|<span data-ttu-id="e9bed-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="e9bed-111">Symbolic Name</span></span>|<span data-ttu-id="e9bed-112">X12LoopOccursOverMaximumTimesDescription</span><span class="sxs-lookup"><span data-stu-id="e9bed-112">X12LoopOccursOverMaximumTimesDescription</span></span>|  
|<span data-ttu-id="e9bed-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="e9bed-113">Message Text</span></span>|<span data-ttu-id="e9bed-114">循环通信发生在最大次数</span><span class="sxs-lookup"><span data-stu-id="e9bed-114">Loops Occurs Over Maximum Times</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e9bed-115">解释</span><span class="sxs-lookup"><span data-stu-id="e9bed-115">Explanation</span></span>  
 <span data-ttu-id="e9bed-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为该交换包含一个重复次数高于消息架构所需最多次数的循环。</span><span class="sxs-lookup"><span data-stu-id="e9bed-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained a loop that repeated more times than the maximum number of times required by the message schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e9bed-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="e9bed-117">User Action</span></span>  
 <span data-ttu-id="e9bed-118">若要解决此错误，请确保交换中的循环重复次数不超过消息架构中为循环指定的 maxOccurs 属性中的次数，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="e9bed-118">To resolve this error, make sure that the loop repeats in the interchange no more than the number of times in the maxOccurs property specified for the loop in the message schema, and then have the interchange resent.</span></span>