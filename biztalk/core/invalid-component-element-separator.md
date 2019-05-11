---
title: 组件元素分隔符无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 738a1107-86e6-4475-a61d-ed1d9ab7e5d2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baa8896a68f0621437bba07429ce87bdbbbc03a9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381422"
---
# <a name="invalid-component-element-separator"></a><span data-ttu-id="33276-102">组件元素分隔符无效</span><span class="sxs-lookup"><span data-stu-id="33276-102">Invalid Component Element Separator</span></span>
## <a name="details"></a><span data-ttu-id="33276-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="33276-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="33276-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="33276-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="33276-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="33276-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="33276-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="33276-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="33276-107">事件源</span><span class="sxs-lookup"><span data-stu-id="33276-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="33276-108">EDI</span><span class="sxs-lookup"><span data-stu-id="33276-108">EDI</span></span> |
|    <span data-ttu-id="33276-109">组件</span><span class="sxs-lookup"><span data-stu-id="33276-109">Component</span></span>    |                                       <span data-ttu-id="33276-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="33276-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="33276-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="33276-111">Symbolic Name</span></span>  |                   <span data-ttu-id="33276-112">X12Ta1InvalidComponentElementSeparatorDescription\\</span><span class="sxs-lookup"><span data-stu-id="33276-112">X12Ta1InvalidComponentElementSeparatorDescription\\</span></span>                   |
|  <span data-ttu-id="33276-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="33276-113">Message Text</span></span>   |                          <span data-ttu-id="33276-114">组件元素分隔符无效</span><span class="sxs-lookup"><span data-stu-id="33276-114">Invalid Component Element Separator</span></span>                           |
  
## <a name="explanation"></a><span data-ttu-id="33276-115">解释</span><span class="sxs-lookup"><span data-stu-id="33276-115">Explanation</span></span>  
 <span data-ttu-id="33276-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为交换中组件分隔符的值不限于 ASCII 字符集中的字符。</span><span class="sxs-lookup"><span data-stu-id="33276-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the component separator in the interchange was not limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="33276-117">在 X12 中，段终止符为 ISA16 字段。</span><span class="sxs-lookup"><span data-stu-id="33276-117">In X12, the segment terminator is the ISA16 field.</span></span> <span data-ttu-id="33276-118">在 EDIFACT 中，段终止符为 UNA1 字段。</span><span class="sxs-lookup"><span data-stu-id="33276-118">In EDIFACT, the segment terminator is the UNA1 field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="33276-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="33276-119">User Action</span></span>  
 <span data-ttu-id="33276-120">若要解决此错误，请确保段终止符（X12 交换中的 ISA16 字段或者 EDIFACT 交换中的 UNA1 字段）仅限于 ASCII 字符集中的字符。</span><span class="sxs-lookup"><span data-stu-id="33276-120">To resolve this error, make sure that the segment terminator (the ISA16 field in an X12 interchange or the UNA1 field in an EDIFACT interchange) is limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="33276-121">然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="33276-121">Have the interchange resent.</span></span>