---
title: 段不在定义的事务集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 914e333f-96e4-4094-880d-51a5f25915c3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3db84f1ae6fda183799b0344d95da7b395aaee8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991694"
---
# <a name="segment-not-in-defined-transaction-set"></a><span data-ttu-id="c9053-102">段不在定义的事务集中</span><span class="sxs-lookup"><span data-stu-id="c9053-102">Segment Not In Defined Transaction set</span></span>
## <a name="details"></a><span data-ttu-id="c9053-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c9053-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="c9053-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c9053-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="c9053-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="c9053-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="c9053-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c9053-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="c9053-107">事件源</span><span class="sxs-lookup"><span data-stu-id="c9053-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c9053-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="c9053-108"> EDI</span></span> |
|    <span data-ttu-id="c9053-109">组件</span><span class="sxs-lookup"><span data-stu-id="c9053-109">Component</span></span>    |                                       <span data-ttu-id="c9053-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="c9053-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="c9053-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="c9053-111">Symbolic Name</span></span>  |                          <span data-ttu-id="c9053-112">X12SegmentNotInDefinedTSDescription</span><span class="sxs-lookup"><span data-stu-id="c9053-112">X12SegmentNotInDefinedTSDescription</span></span>                           |
|  <span data-ttu-id="c9053-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="c9053-113">Message Text</span></span>   |                         <span data-ttu-id="c9053-114">段不在定义的事务集中</span><span class="sxs-lookup"><span data-stu-id="c9053-114">Segment Not In Defined Transaction set</span></span>                         |
  
## <a name="explanation"></a><span data-ttu-id="c9053-115">解释</span><span class="sxs-lookup"><span data-stu-id="c9053-115">Explanation</span></span>  
 <span data-ttu-id="c9053-116">此错误/警告/信息事件表明接收管道无法处理传入的 X12 交换，因为该交换中的事务集不包含文档架构所需的段。</span><span class="sxs-lookup"><span data-stu-id="c9053-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because a transaction set in that interchange does not contain a segment required by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c9053-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="c9053-117">User Action</span></span>  
 <span data-ttu-id="c9053-118">若要解决此错误，请让交换的发送方将所需的段添加到交换的事务集中，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="c9053-118">To resolve this error, have the sender of the interchange add the required segment to the transaction set in the interchange, and then resend the interchange.</span></span>