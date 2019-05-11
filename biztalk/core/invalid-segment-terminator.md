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
ms.openlocfilehash: 0ebd39a1711f4e1af15735f5a6d2e9523c490036
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330478"
---
# <a name="invalid-segment-terminator"></a><span data-ttu-id="fe255-102">段终止符无效</span><span class="sxs-lookup"><span data-stu-id="fe255-102">Invalid Segment Terminator</span></span>
## <a name="details"></a><span data-ttu-id="fe255-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="fe255-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="fe255-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="fe255-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="fe255-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="fe255-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="fe255-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="fe255-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="fe255-107">事件源</span><span class="sxs-lookup"><span data-stu-id="fe255-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="fe255-108">EDI</span><span class="sxs-lookup"><span data-stu-id="fe255-108">EDI</span></span> |
|    <span data-ttu-id="fe255-109">组件</span><span class="sxs-lookup"><span data-stu-id="fe255-109">Component</span></span>    |                                       <span data-ttu-id="fe255-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="fe255-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="fe255-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="fe255-111">Symbolic Name</span></span>  |                       <span data-ttu-id="fe255-112">X12Ta1InvalidSegmentTerminatorDescription</span><span class="sxs-lookup"><span data-stu-id="fe255-112">X12Ta1InvalidSegmentTerminatorDescription</span></span>                        |
|  <span data-ttu-id="fe255-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="fe255-113">Message Text</span></span>   |                               <span data-ttu-id="fe255-114">段终止符无效</span><span class="sxs-lookup"><span data-stu-id="fe255-114">Invalid Segment Terminator</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="fe255-115">解释</span><span class="sxs-lookup"><span data-stu-id="fe255-115">Explanation</span></span>  
 <span data-ttu-id="fe255-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为交换中段终止符的值不限于 ASCII 字符集中的字符。</span><span class="sxs-lookup"><span data-stu-id="fe255-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the segment terminator in the interchange was not limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="fe255-117">在 X12 中，段终止符被定义为 ISA 段中的最后一个字符。</span><span class="sxs-lookup"><span data-stu-id="fe255-117">In X12, the segment terminator is defined as the last character in the ISA segment.</span></span> <span data-ttu-id="fe255-118">在 EDIFACT 中，段终止符为 UNA6 字段。</span><span class="sxs-lookup"><span data-stu-id="fe255-118">In EDIFACT, the segment terminator is the UNA6 field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fe255-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="fe255-119">User Action</span></span>  
 <span data-ttu-id="fe255-120">若要解决此错误，请确保段终止符（X12 交换中 ISA 段的最后一个字符或者 EDIFACT 交换中的 UNA6 字段）仅限于 ASCII 字符集中的字符。</span><span class="sxs-lookup"><span data-stu-id="fe255-120">To resolve this error, make sure that the segment terminator (the last character of the ISA segment in an X12 interchange or the UNA6 field in an EDIFACT interchange) is limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="fe255-121">然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="fe255-121">Have the interchange resent.</span></span>