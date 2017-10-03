---
title: "根据指定的分隔符集，就无法找到任何有效的数字 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 08887f7d-8256-4de3-8db9-b890451521ff
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9b726ca0ab052ff53ae7f20242972db69fc4725
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="based-on-the-specified-delimiter-set-no-valid-digit-could-be-found"></a><span data-ttu-id="ce479-102">基于指定的分隔符集，找不到有效的数字</span><span class="sxs-lookup"><span data-stu-id="ce479-102">Based on the specified delimiter set, no valid Digit could be found</span></span>
## <a name="details"></a><span data-ttu-id="ce479-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ce479-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ce479-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ce479-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ce479-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ce479-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ce479-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ce479-106">Event ID</span></span>|-|  
|<span data-ttu-id="ce479-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ce479-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ce479-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ce479-108"> EDI</span></span>|  
|<span data-ttu-id="ce479-109">组件</span><span class="sxs-lookup"><span data-stu-id="ce479-109">Component</span></span>|<span data-ttu-id="ce479-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="ce479-110">EDI Engine</span></span>|  
|<span data-ttu-id="ce479-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ce479-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="ce479-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="ce479-112">Message Text</span></span>|<span data-ttu-id="ce479-113">根据指定的分隔符集，无法找到有效的数字。</span><span class="sxs-lookup"><span data-stu-id="ce479-113">Based on the specified delimiter set, no valid Digit could be found.</span></span> <span data-ttu-id="ce479-114">请使用其他分隔符集。</span><span class="sxs-lookup"><span data-stu-id="ce479-114">Please use another delimiter set.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ce479-115">解释</span><span class="sxs-lookup"><span data-stu-id="ce479-115">Explanation</span></span>  
 <span data-ttu-id="ce479-116">此错误/警告/信息事件表明生成传出交换时 EDI 发送管道无法找到有效的数字，因为在传出交换的某个字段中使用的数字与某个分隔符相同。</span><span class="sxs-lookup"><span data-stu-id="ce479-116">This Error/Warning/Information event indicates that the EDI send pipeline could not find a valid digit when generating an outgoing interchange because a digit used in a field of the outgoing interchange was the same as a separator character.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ce479-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="ce479-117">User Action</span></span>  
 <span data-ttu-id="ce479-118">若要解决此错误，请更改 EDI 发送管道用来创建消息的分隔符值，以便没有分隔符与传出交换的某个字段中使用的数字相同。</span><span class="sxs-lookup"><span data-stu-id="ce479-118">To resolve this error, change the separator values used by the EDI send pipeline to create a message so that no separator character will be the same as a digit used in a field of the outgoing interchange.</span></span> <span data-ttu-id="ce479-119">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="ce479-119">Do one of the following:</span></span>  
  
-   <span data-ttu-id="ce479-120">若要使 X12 交换发送给解析后的参与方，请更改“作为交换接收方的参与方”的“ISA 段定义”页中的分隔符设置。</span><span class="sxs-lookup"><span data-stu-id="ce479-120">For an X12 interchange being sent to a resolved party, change the separator settings in the ISA Segment Definition page for the party as interchange receiver.</span></span>  
  
-   <span data-ttu-id="ce479-121">若要使 X12 交换发送给尚未解析的参与方，请更改“ISA 段定义”全局属性页中的分隔符设置。</span><span class="sxs-lookup"><span data-stu-id="ce479-121">For an X12 interchange being sent to a party that has not been resolved, change the separator settings in the ISA Segment Definition global property page.</span></span>  
  
-   <span data-ttu-id="ce479-122">若要使 EDIFACT 交换发送给解析后的参与方，请更改“作为交换接收方的参与方”的“UNA 段定义”页中的分隔符设置。</span><span class="sxs-lookup"><span data-stu-id="ce479-122">For an EDIFACT interchange being sent to a resolved party, change the separator settings in the UNA Segment Definition page for the party as interchange receiver.</span></span>  
  
-   <span data-ttu-id="ce479-123">若要使 EDIFACT 交换发送给尚未解析的参与方，请更改“UNA 段定义”全局属性页中的分隔符设置。</span><span class="sxs-lookup"><span data-stu-id="ce479-123">For an EDIFACT interchange being sent to a party that has not been resolved, change the separator settings in the UNA Segment Definition global property page.</span></span>