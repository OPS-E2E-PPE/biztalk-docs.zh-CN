---
title: "缺少必需的段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8e459a22-8de5-426a-a46a-1d0ab72b532d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1250499f127aaa09e21269b894ed7bd51bd6a6ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="mandatory-segment-missing"></a><span data-ttu-id="e562d-102">缺少必需的段</span><span class="sxs-lookup"><span data-stu-id="e562d-102">Mandatory Segment Missing</span></span>
## <a name="details"></a><span data-ttu-id="e562d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e562d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e562d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e562d-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e562d-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="e562d-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="e562d-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e562d-106">Event ID</span></span>|-|  
|<span data-ttu-id="e562d-107">事件源</span><span class="sxs-lookup"><span data-stu-id="e562d-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e562d-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="e562d-108"> EDI</span></span>|  
|<span data-ttu-id="e562d-109">组件</span><span class="sxs-lookup"><span data-stu-id="e562d-109">Component</span></span>|<span data-ttu-id="e562d-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="e562d-110">EDI Engine</span></span>|  
|<span data-ttu-id="e562d-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="e562d-111">Symbolic Name</span></span>|<span data-ttu-id="e562d-112">X12MandatorySegmentMissingDescription</span><span class="sxs-lookup"><span data-stu-id="e562d-112">X12MandatorySegmentMissingDescription</span></span>|  
|<span data-ttu-id="e562d-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="e562d-113">Message Text</span></span>|<span data-ttu-id="e562d-114">缺少必需的段</span><span class="sxs-lookup"><span data-stu-id="e562d-114">Mandatory Segment Missing</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e562d-115">解释</span><span class="sxs-lookup"><span data-stu-id="e562d-115">Explanation</span></span>  
 <span data-ttu-id="e562d-116">此错误/警告/信息事件表明接收管道无法处理传入的 X12 交换，因为交换不包含消息架构（其 minOccurs 大于 0）所需的段。</span><span class="sxs-lookup"><span data-stu-id="e562d-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the interchange did not contain a segment that is required by the message schema (for which minOccurs is greater than 0).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e562d-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="e562d-117">User Action</span></span>  
 <span data-ttu-id="e562d-118">若要解决此错误，请确保交换包含消息架构所需的所有段，然后重新发送消息。</span><span class="sxs-lookup"><span data-stu-id="e562d-118">To resolve this error, make sure that the interchange contains all segments required by the message schema, and then have the message resent.</span></span>