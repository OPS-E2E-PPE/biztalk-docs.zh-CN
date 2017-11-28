---
title: "段具有数据元素错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 469622e2-6500-4f55-ab53-f8d89ee0a978
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27c8c9e43bfe0a733a3e95b7812195a0b7f3990c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="segment-has-data-element-errors"></a><span data-ttu-id="7e78e-102">段具有数据元素错误</span><span class="sxs-lookup"><span data-stu-id="7e78e-102">Segment has data element errors</span></span>
## <a name="details"></a><span data-ttu-id="7e78e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7e78e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7e78e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7e78e-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="7e78e-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="7e78e-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="7e78e-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7e78e-106">Event ID</span></span>|-|  
|<span data-ttu-id="7e78e-107">事件源</span><span class="sxs-lookup"><span data-stu-id="7e78e-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7e78e-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="7e78e-108"> EDI</span></span>|  
|<span data-ttu-id="7e78e-109">组件</span><span class="sxs-lookup"><span data-stu-id="7e78e-109">Component</span></span>|<span data-ttu-id="7e78e-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="7e78e-110">EDI Engine</span></span>|  
|<span data-ttu-id="7e78e-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="7e78e-111">Symbolic Name</span></span>|<span data-ttu-id="7e78e-112">X12SegmentHasDataElementErrorsDescription</span><span class="sxs-lookup"><span data-stu-id="7e78e-112">X12SegmentHasDataElementErrorsDescription</span></span>|  
|<span data-ttu-id="7e78e-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="7e78e-113">Message Text</span></span>|<span data-ttu-id="7e78e-114">段有数据元素错误</span><span class="sxs-lookup"><span data-stu-id="7e78e-114">Segment Has Data Element Errors</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7e78e-115">解释</span><span class="sxs-lookup"><span data-stu-id="7e78e-115">Explanation</span></span>  
 <span data-ttu-id="7e78e-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为交换所包含的段中包含的数据元素不符合文档架构。</span><span class="sxs-lookup"><span data-stu-id="7e78e-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained segments that included data elements that did not conform to the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7e78e-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="7e78e-117">User Action</span></span>  
 <span data-ttu-id="7e78e-118">若要解决此错误，请确保交换中的数据元素符合文档架构，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="7e78e-118">To resolve this error, make sure that the data elements in the interchange conform to the document schema, and then resend the interchange.</span></span>