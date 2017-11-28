---
title: "不在正确的顺序的段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f0c0fdc-10d9-4b77-a80d-b2b8571e7665
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70b6147ea32bed7adf10640a3291ea9c75f71b1e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="segment-not-in-proper-sequence"></a><span data-ttu-id="5b59f-102">段未处于正确顺序</span><span class="sxs-lookup"><span data-stu-id="5b59f-102">Segment Not In Proper Sequence</span></span>
## <a name="details"></a><span data-ttu-id="5b59f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5b59f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5b59f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5b59f-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="5b59f-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="5b59f-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="5b59f-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5b59f-106">Event ID</span></span>|-|  
|<span data-ttu-id="5b59f-107">事件源</span><span class="sxs-lookup"><span data-stu-id="5b59f-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5b59f-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="5b59f-108"> EDI</span></span>|  
|<span data-ttu-id="5b59f-109">组件</span><span class="sxs-lookup"><span data-stu-id="5b59f-109">Component</span></span>|<span data-ttu-id="5b59f-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="5b59f-110">EDI Engine</span></span>|  
|<span data-ttu-id="5b59f-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="5b59f-111">Symbolic Name</span></span>|<span data-ttu-id="5b59f-112">X12SegmentNotInProperSequenceDescription</span><span class="sxs-lookup"><span data-stu-id="5b59f-112">X12SegmentNotInProperSequenceDescription</span></span>|  
|<span data-ttu-id="5b59f-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="5b59f-113">Message Text</span></span>|<span data-ttu-id="5b59f-114">段未处于正确顺序</span><span class="sxs-lookup"><span data-stu-id="5b59f-114">Segment Not In Proper Sequence</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5b59f-115">解释</span><span class="sxs-lookup"><span data-stu-id="5b59f-115">Explanation</span></span>  
 <span data-ttu-id="5b59f-116">此错误/警告/信息事件表明接收管道无法处理传入的 X12 交换，因为交换中的段未处于文档架构指定的顺序。</span><span class="sxs-lookup"><span data-stu-id="5b59f-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because a segment in the interchange is out of the sequence specified by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5b59f-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="5b59f-117">User Action</span></span>  
 <span data-ttu-id="5b59f-118">若要解决此错误，请让交换的发送方重新安排交换中的段，以便这些段处于文档架构指定的顺序，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="5b59f-118">To resolve this error, have the sender of the interchange rearrange the segments in the interchange so they are in the order specified by the document schema, and then resend the interchange.</span></span>