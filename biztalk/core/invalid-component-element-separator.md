---
title: 无效的组件元素分隔符 |Microsoft 文档
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
ms.openlocfilehash: 4abf047a61dc8b8f2eb89e436594e47e6f4cb067
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257253"
---
# <a name="invalid-component-element-separator"></a><span data-ttu-id="1019c-102">组件元素分隔符无效</span><span class="sxs-lookup"><span data-stu-id="1019c-102">Invalid Component Element Separator</span></span>
## <a name="details"></a><span data-ttu-id="1019c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1019c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1019c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1019c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="1019c-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="1019c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="1019c-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1019c-106">Event ID</span></span>|-|  
|<span data-ttu-id="1019c-107">事件源</span><span class="sxs-lookup"><span data-stu-id="1019c-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1019c-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="1019c-108"> EDI</span></span>|  
|<span data-ttu-id="1019c-109">组件</span><span class="sxs-lookup"><span data-stu-id="1019c-109">Component</span></span>|<span data-ttu-id="1019c-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="1019c-110">EDI Engine</span></span>|  
|<span data-ttu-id="1019c-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="1019c-111">Symbolic Name</span></span>|<span data-ttu-id="1019c-112">X12Ta1InvalidComponentElementSeparatorDescription\\</span><span class="sxs-lookup"><span data-stu-id="1019c-112">X12Ta1InvalidComponentElementSeparatorDescription\\</span></span>|  
|<span data-ttu-id="1019c-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="1019c-113">Message Text</span></span>|<span data-ttu-id="1019c-114">组件元素分隔符无效</span><span class="sxs-lookup"><span data-stu-id="1019c-114">Invalid Component Element Separator</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1019c-115">解释</span><span class="sxs-lookup"><span data-stu-id="1019c-115">Explanation</span></span>  
 <span data-ttu-id="1019c-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为交换中组件分隔符的值不限于 ASCII 字符集中的字符。</span><span class="sxs-lookup"><span data-stu-id="1019c-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the component separator in the interchange was not limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="1019c-117">在 X12 中，段终止符为 ISA16 字段。</span><span class="sxs-lookup"><span data-stu-id="1019c-117">In X12, the segment terminator is the ISA16 field.</span></span> <span data-ttu-id="1019c-118">在 EDIFACT 中，段终止符为 UNA1 字段。</span><span class="sxs-lookup"><span data-stu-id="1019c-118">In EDIFACT, the segment terminator is the UNA1 field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1019c-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="1019c-119">User Action</span></span>  
 <span data-ttu-id="1019c-120">若要解决此错误，请确保段终止符（X12 交换中的 ISA16 字段或者 EDIFACT 交换中的 UNA1 字段）仅限于 ASCII 字符集中的字符。</span><span class="sxs-lookup"><span data-stu-id="1019c-120">To resolve this error, make sure that the segment terminator (the ISA16 field in an X12 interchange or the UNA1 field in an EDIFACT interchange) is limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="1019c-121">然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="1019c-121">Have the interchange resent.</span></span>