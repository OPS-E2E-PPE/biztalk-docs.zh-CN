---
title: 段超出了最大值使用说明 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4e1704a-5d49-4549-af50-d1a89a1e70f0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62a52f7589dc42d3af6b07db6fcbeb926a3d5dbc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985318"
---
# <a name="segment-exceeds-maximum-use-description"></a><span data-ttu-id="0e5f9-102">段超出了最大值使用说明</span><span class="sxs-lookup"><span data-stu-id="0e5f9-102">Segment Exceeds Maximum Use Description</span></span>
## <a name="details"></a><span data-ttu-id="0e5f9-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0e5f9-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="0e5f9-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0e5f9-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="0e5f9-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="0e5f9-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="0e5f9-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0e5f9-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="0e5f9-107">事件源</span><span class="sxs-lookup"><span data-stu-id="0e5f9-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0e5f9-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0e5f9-108"> EDI</span></span> |
|    <span data-ttu-id="0e5f9-109">组件</span><span class="sxs-lookup"><span data-stu-id="0e5f9-109">Component</span></span>    |                                       <span data-ttu-id="0e5f9-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="0e5f9-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="0e5f9-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="0e5f9-111">Symbolic Name</span></span>  |                         <span data-ttu-id="0e5f9-112">X12SegmentExceedsMaximumUseDescription</span><span class="sxs-lookup"><span data-stu-id="0e5f9-112">X12SegmentExceedsMaximumUseDescription</span></span>                         |
|  <span data-ttu-id="0e5f9-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="0e5f9-113">Message Text</span></span>   |                        <span data-ttu-id="0e5f9-114">段超出了最大值使用说明</span><span class="sxs-lookup"><span data-stu-id="0e5f9-114">Segment Exceeds Maximum Use Description</span></span>                         |
  
## <a name="explanation"></a><span data-ttu-id="0e5f9-115">解释</span><span class="sxs-lookup"><span data-stu-id="0e5f9-115">Explanation</span></span>  
 <span data-ttu-id="0e5f9-116">此错误/警告/信息事件表明接收管道不无法处理传入的交换，因为该交换包含一个段的更多实例不是架构所允许的。</span><span class="sxs-lookup"><span data-stu-id="0e5f9-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained more instances of a segment than allowed by the schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0e5f9-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="0e5f9-117">User Action</span></span>  
 <span data-ttu-id="0e5f9-118">若要解决此错误，请确保交换中的段数未超过所允许的最大段数，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="0e5f9-118">To resolve this error, make sure that the interchange does not have more than the maximum allowed number of segments, and then resend the interchange.</span></span>