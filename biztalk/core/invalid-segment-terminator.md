---
title: 段终止符无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 508dac21-4731-439d-bf4a-a50858f1ffa0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0249c16bf495f9103759ec4eba9a9c6776b87ca2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001822"
---
# <a name="invalid-segment-terminator"></a><span data-ttu-id="3452a-102">段终止符无效</span><span class="sxs-lookup"><span data-stu-id="3452a-102">Invalid Segment Terminator</span></span>
## <a name="details"></a><span data-ttu-id="3452a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="3452a-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="3452a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="3452a-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="3452a-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="3452a-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="3452a-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="3452a-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="3452a-107">事件源</span><span class="sxs-lookup"><span data-stu-id="3452a-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3452a-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="3452a-108"> EDI</span></span> |
|    <span data-ttu-id="3452a-109">组件</span><span class="sxs-lookup"><span data-stu-id="3452a-109">Component</span></span>    |                                       <span data-ttu-id="3452a-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="3452a-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="3452a-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="3452a-111">Symbolic Name</span></span>  |                       <span data-ttu-id="3452a-112">X12Ta1InvalidSegmentTerminatorDescription</span><span class="sxs-lookup"><span data-stu-id="3452a-112">X12Ta1InvalidSegmentTerminatorDescription</span></span>                        |
|  <span data-ttu-id="3452a-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="3452a-113">Message Text</span></span>   |                               <span data-ttu-id="3452a-114">段终止符无效</span><span class="sxs-lookup"><span data-stu-id="3452a-114">Invalid Segment Terminator</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="3452a-115">解释</span><span class="sxs-lookup"><span data-stu-id="3452a-115">Explanation</span></span>  
 <span data-ttu-id="3452a-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为交换中段终止符的值不限于 ASCII 字符集中的字符。</span><span class="sxs-lookup"><span data-stu-id="3452a-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the segment terminator in the interchange was not limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="3452a-117">在 X12 中，段终止符被定义为 ISA 段中的最后一个字符。</span><span class="sxs-lookup"><span data-stu-id="3452a-117">In X12, the segment terminator is defined as the last character in the ISA segment.</span></span> <span data-ttu-id="3452a-118">在 EDIFACT 中，段终止符为 UNA6 字段。</span><span class="sxs-lookup"><span data-stu-id="3452a-118">In EDIFACT, the segment terminator is the UNA6 field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3452a-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="3452a-119">User Action</span></span>  
 <span data-ttu-id="3452a-120">若要解决此错误，请确保段终止符（X12 交换中 ISA 段的最后一个字符或者 EDIFACT 交换中的 UNA6 字段）仅限于 ASCII 字符集中的字符。</span><span class="sxs-lookup"><span data-stu-id="3452a-120">To resolve this error, make sure that the segment terminator (the last character of the ISA segment in an X12 interchange or the UNA6 field in an EDIFACT interchange) is limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="3452a-121">然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="3452a-121">Have the interchange resent.</span></span>