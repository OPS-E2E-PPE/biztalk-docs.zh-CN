---
title: "段超过最大使用说明 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4e1704a-5d49-4549-af50-d1a89a1e70f0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71f5e5a0ae590be850a4560324814c756d51e9fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="segment-exceeds-maximum-use-description"></a><span data-ttu-id="221d8-102">段超过最大使用说明</span><span class="sxs-lookup"><span data-stu-id="221d8-102">Segment Exceeds Maximum Use Description</span></span>
## <a name="details"></a><span data-ttu-id="221d8-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="221d8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="221d8-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="221d8-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="221d8-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="221d8-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="221d8-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="221d8-106">Event ID</span></span>|-|  
|<span data-ttu-id="221d8-107">事件源</span><span class="sxs-lookup"><span data-stu-id="221d8-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="221d8-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="221d8-108"> EDI</span></span>|  
|<span data-ttu-id="221d8-109">组件</span><span class="sxs-lookup"><span data-stu-id="221d8-109">Component</span></span>|<span data-ttu-id="221d8-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="221d8-110">EDI Engine</span></span>|  
|<span data-ttu-id="221d8-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="221d8-111">Symbolic Name</span></span>|<span data-ttu-id="221d8-112">X12SegmentExceedsMaximumUseDescription</span><span class="sxs-lookup"><span data-stu-id="221d8-112">X12SegmentExceedsMaximumUseDescription</span></span>|  
|<span data-ttu-id="221d8-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="221d8-113">Message Text</span></span>|<span data-ttu-id="221d8-114">段超过最大使用说明</span><span class="sxs-lookup"><span data-stu-id="221d8-114">Segment Exceeds Maximum Use Description</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="221d8-115">解释</span><span class="sxs-lookup"><span data-stu-id="221d8-115">Explanation</span></span>  
 <span data-ttu-id="221d8-116">此错误/警告/信息事件指示接收管道不无法处理传入的交换，因为该交换包含段的更多实例不是架构所允许的。</span><span class="sxs-lookup"><span data-stu-id="221d8-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained more instances of a segment than allowed by the schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="221d8-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="221d8-117">User Action</span></span>  
 <span data-ttu-id="221d8-118">若要解决此错误，请确保交换中的段数未超过所允许的最大段数，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="221d8-118">To resolve this error, make sure that the interchange does not have more than the maximum allowed number of segments, and then resend the interchange.</span></span>