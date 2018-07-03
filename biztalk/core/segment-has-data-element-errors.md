---
title: 段有数据元素错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 469622e2-6500-4f55-ab53-f8d89ee0a978
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30b000f670e4329c68540b51f291097f5bbd4dc2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998886"
---
# <a name="segment-has-data-element-errors"></a><span data-ttu-id="f2041-102">段有数据元素错误</span><span class="sxs-lookup"><span data-stu-id="f2041-102">Segment has data element errors</span></span>
## <a name="details"></a><span data-ttu-id="f2041-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f2041-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="f2041-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f2041-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="f2041-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="f2041-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="f2041-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f2041-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="f2041-107">事件源</span><span class="sxs-lookup"><span data-stu-id="f2041-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f2041-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="f2041-108"> EDI</span></span> |
|    <span data-ttu-id="f2041-109">组件</span><span class="sxs-lookup"><span data-stu-id="f2041-109">Component</span></span>    |                                       <span data-ttu-id="f2041-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="f2041-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="f2041-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="f2041-111">Symbolic Name</span></span>  |                       <span data-ttu-id="f2041-112">X12SegmentHasDataElementErrorsDescription</span><span class="sxs-lookup"><span data-stu-id="f2041-112">X12SegmentHasDataElementErrorsDescription</span></span>                        |
|  <span data-ttu-id="f2041-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="f2041-113">Message Text</span></span>   |                            <span data-ttu-id="f2041-114">段有数据元素错误</span><span class="sxs-lookup"><span data-stu-id="f2041-114">Segment Has Data Element Errors</span></span>                             |
  
## <a name="explanation"></a><span data-ttu-id="f2041-115">解释</span><span class="sxs-lookup"><span data-stu-id="f2041-115">Explanation</span></span>  
 <span data-ttu-id="f2041-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为交换所包含的段中包含的数据元素不符合文档架构。</span><span class="sxs-lookup"><span data-stu-id="f2041-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained segments that included data elements that did not conform to the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f2041-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="f2041-117">User Action</span></span>  
 <span data-ttu-id="f2041-118">若要解决此错误，请确保交换中的数据元素符合文档架构，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="f2041-118">To resolve this error, make sure that the data elements in the interchange conform to the document schema, and then resend the interchange.</span></span>