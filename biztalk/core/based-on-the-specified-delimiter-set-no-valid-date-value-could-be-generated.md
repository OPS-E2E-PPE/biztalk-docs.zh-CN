---
title: 基于指定的分隔符集，就无法生成有效的日期值 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cdd157c0-9a0d-421b-8350-aa1263126ca0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef866157078e037d7424452a0c7c6a1bff1ae445
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008558"
---
# <a name="based-on-the-specified-delimiter-set-no-valid-date-value-could-be-generated"></a><span data-ttu-id="2579c-102">基于指定的分隔符集，无法生成有效的日期值</span><span class="sxs-lookup"><span data-stu-id="2579c-102">Based on the specified delimiter set, no valid Date value could be generated</span></span>
## <a name="details"></a><span data-ttu-id="2579c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="2579c-103">Details</span></span>  
  
|                 |                                                                                                                 |
|-----------------|-----------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="2579c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="2579c-104">Product Name</span></span>   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                |
| <span data-ttu-id="2579c-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="2579c-105">Product Version</span></span> |                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                            |
|    <span data-ttu-id="2579c-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2579c-106">Event ID</span></span>     |                                                        -                                                        |
|  <span data-ttu-id="2579c-107">事件源</span><span class="sxs-lookup"><span data-stu-id="2579c-107">Event Source</span></span>   |             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2579c-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="2579c-108"> EDI</span></span>              |
|    <span data-ttu-id="2579c-109">组件</span><span class="sxs-lookup"><span data-stu-id="2579c-109">Component</span></span>    |                                                   <span data-ttu-id="2579c-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="2579c-110">EDI Engine</span></span>                                                    |
|  <span data-ttu-id="2579c-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="2579c-111">Symbolic Name</span></span>  |                                                        -                                                        |
|  <span data-ttu-id="2579c-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="2579c-112">Message Text</span></span>   | <span data-ttu-id="2579c-113">基于指定的分隔符集，无法生成有效的日期值。</span><span class="sxs-lookup"><span data-stu-id="2579c-113">Based on the specified delimiter set, no valid Date value could be generated.</span></span> <span data-ttu-id="2579c-114">请使用其他分隔符集。</span><span class="sxs-lookup"><span data-stu-id="2579c-114">Please use another delimiter set.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="2579c-115">解释</span><span class="sxs-lookup"><span data-stu-id="2579c-115">Explanation</span></span>  
 <span data-ttu-id="2579c-116">此错误/警告/信息十表明 EDI 发送管道无法生成有效的日期值，因为传出交换的“日期”字段中使用的某个字符与分隔符相同。</span><span class="sxs-lookup"><span data-stu-id="2579c-116">This Error/Warning/Information event indicates that the EDI send pipeline could not generate a valid date value because a character used in a Date field of the outgoing interchange was the same as a separator character.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2579c-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="2579c-117">User Action</span></span>  
 <span data-ttu-id="2579c-118">若要解决此错误，请更改 EDI 发送管道使用的分隔符值以创建一个消息，以便没有分隔符与传出交换的某个“日期”字段中使用的字符相同。</span><span class="sxs-lookup"><span data-stu-id="2579c-118">To resolve this error, change the separator values used by the EDI send pipeline to create a message so that no separator character will be the same as a character used in a Date field of the outgoing interchange.</span></span> <span data-ttu-id="2579c-119">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="2579c-119">Do one of the following:</span></span>  
  
-   <span data-ttu-id="2579c-120">若要使 X12 交换发送给解析后的参与方，请更改“作为交换接收方的参与方”的“ISA 段定义”页中的分隔符设置。</span><span class="sxs-lookup"><span data-stu-id="2579c-120">For an X12 interchange being sent to a resolved party, change the separator settings in the ISA Segment Definition page for the party as interchange receiver.</span></span>  
  
-   <span data-ttu-id="2579c-121">若要使 X12 交换发送给尚未解析的参与方，请更改“ISA 段定义”全局属性页中的分隔符设置。</span><span class="sxs-lookup"><span data-stu-id="2579c-121">For an X12 interchange being sent to a party that has not been resolved, change the separator settings in the ISA Segment Definition global property page.</span></span>  
  
-   <span data-ttu-id="2579c-122">若要使 EDIFACT 交换发送给解析后的参与方，请更改“作为交换接收方的参与方”的“UNA 段定义”页中的分隔符设置。</span><span class="sxs-lookup"><span data-stu-id="2579c-122">For an EDIFACT interchange being sent to a resolved party, change the separator settings in the UNA Segment Definition page for the party as interchange receiver.</span></span>  
  
-   <span data-ttu-id="2579c-123">若要使 EDIFACT 交换发送给尚未解析的参与方，请更改“UNA 段定义”全局属性页中的分隔符设置。</span><span class="sxs-lookup"><span data-stu-id="2579c-123">For an EDIFACT interchange being sent to a party that has not been resolved, change the separator settings in the UNA Segment Definition global property page.</span></span>