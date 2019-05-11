---
title: 段未处于正确顺序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f0c0fdc-10d9-4b77-a80d-b2b8571e7665
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0562c55f6b0b494058805febde18593da1b567f1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279772"
---
# <a name="segment-not-in-proper-sequence"></a><span data-ttu-id="41e23-102">段未处于正确顺序</span><span class="sxs-lookup"><span data-stu-id="41e23-102">Segment Not In Proper Sequence</span></span>
## <a name="details"></a><span data-ttu-id="41e23-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="41e23-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="41e23-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="41e23-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="41e23-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="41e23-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="41e23-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="41e23-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="41e23-107">事件源</span><span class="sxs-lookup"><span data-stu-id="41e23-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="41e23-108">EDI</span><span class="sxs-lookup"><span data-stu-id="41e23-108">EDI</span></span> |
|    <span data-ttu-id="41e23-109">组件</span><span class="sxs-lookup"><span data-stu-id="41e23-109">Component</span></span>    |                                       <span data-ttu-id="41e23-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="41e23-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="41e23-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="41e23-111">Symbolic Name</span></span>  |                        <span data-ttu-id="41e23-112">X12SegmentNotInProperSequenceDescription</span><span class="sxs-lookup"><span data-stu-id="41e23-112">X12SegmentNotInProperSequenceDescription</span></span>                        |
|  <span data-ttu-id="41e23-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="41e23-113">Message Text</span></span>   |                             <span data-ttu-id="41e23-114">段未处于正确顺序</span><span class="sxs-lookup"><span data-stu-id="41e23-114">Segment Not In Proper Sequence</span></span>                             |
  
## <a name="explanation"></a><span data-ttu-id="41e23-115">解释</span><span class="sxs-lookup"><span data-stu-id="41e23-115">Explanation</span></span>  
 <span data-ttu-id="41e23-116">此错误/警告/信息事件表明接收管道无法处理传入的 X12 交换，因为交换中的段未处于文档架构指定的顺序。</span><span class="sxs-lookup"><span data-stu-id="41e23-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because a segment in the interchange is out of the sequence specified by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="41e23-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="41e23-117">User Action</span></span>  
 <span data-ttu-id="41e23-118">若要解决此错误，请让交换的发送方重新安排交换中的段，以便这些段处于文档架构指定的顺序，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="41e23-118">To resolve this error, have the sender of the interchange rearrange the segments in the interchange so they are in the order specified by the document schema, and then resend the interchange.</span></span>