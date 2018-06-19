---
title: 无效的数据元素分隔符 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76c50a8b-274f-4f4a-9826-4f6f8123e9d1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d83b8ce3099ebb940507d391881cfd92cde5034d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257461"
---
# <a name="invalid-data-element-separator"></a><span data-ttu-id="eac10-102">数据元素分隔符无效</span><span class="sxs-lookup"><span data-stu-id="eac10-102">Invalid Data Element Separator</span></span>
## <a name="details"></a><span data-ttu-id="eac10-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="eac10-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eac10-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="eac10-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="eac10-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="eac10-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="eac10-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="eac10-106">Event ID</span></span>|-|  
|<span data-ttu-id="eac10-107">事件源</span><span class="sxs-lookup"><span data-stu-id="eac10-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="eac10-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="eac10-108"> EDI</span></span>|  
|<span data-ttu-id="eac10-109">组件</span><span class="sxs-lookup"><span data-stu-id="eac10-109">Component</span></span>|<span data-ttu-id="eac10-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="eac10-110">EDI Engine</span></span>|  
|<span data-ttu-id="eac10-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="eac10-111">Symbolic Name</span></span>|<span data-ttu-id="eac10-112">X12Ta1InvalidDataElementSeparatorDescription</span><span class="sxs-lookup"><span data-stu-id="eac10-112">X12Ta1InvalidDataElementSeparatorDescription</span></span>|  
|<span data-ttu-id="eac10-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="eac10-113">Message Text</span></span>|<span data-ttu-id="eac10-114">数据元素分隔符无效</span><span class="sxs-lookup"><span data-stu-id="eac10-114">Invalid Data Element Separator</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="eac10-115">解释</span><span class="sxs-lookup"><span data-stu-id="eac10-115">Explanation</span></span>  
 <span data-ttu-id="eac10-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为交换中段终止符的值不限于 ASCII 字符集中的字符。</span><span class="sxs-lookup"><span data-stu-id="eac10-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the segment terminator in the interchange was not limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="eac10-117">在 X12 中，段终止符被定义为 ISA 段中的第四个字符。</span><span class="sxs-lookup"><span data-stu-id="eac10-117">In X12, the segment terminator is defined as the fourth character in the ISA segment.</span></span> <span data-ttu-id="eac10-118">在 EDIFACT 中，段终止符为 UNA2 字段。</span><span class="sxs-lookup"><span data-stu-id="eac10-118">In EDIFACT, the segment terminator is the UNA2 field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="eac10-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="eac10-119">User Action</span></span>  
 <span data-ttu-id="eac10-120">若要解决此错误，请确保段终止符（X12 交换中 ISA 段的第四个字符或者 EDIFACT 交换中的 UNA2 字段）仅限于 ASCII 字符集中的字符。</span><span class="sxs-lookup"><span data-stu-id="eac10-120">To resolve this error, make sure that the segment terminator (the fourth character of the ISA segment in an X12 interchange or the UNA2 field in an EDIFACT interchange) is limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="eac10-121">然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="eac10-121">Have the interchange resent.</span></span>