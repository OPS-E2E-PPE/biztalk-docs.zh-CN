---
title: "意外的段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7169190c-8893-4076-8634-137fd43992f2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47ff173b88c51ecf28a4979cef3a0c61475c62c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="unexpected-segment"></a><span data-ttu-id="e03d3-102">意外段</span><span class="sxs-lookup"><span data-stu-id="e03d3-102">Unexpected segment</span></span>
## <a name="details"></a><span data-ttu-id="e03d3-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e03d3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e03d3-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e03d3-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e03d3-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="e03d3-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="e03d3-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e03d3-106">Event ID</span></span>|-|  
|<span data-ttu-id="e03d3-107">事件源</span><span class="sxs-lookup"><span data-stu-id="e03d3-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e03d3-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="e03d3-108"> EDI</span></span>|  
|<span data-ttu-id="e03d3-109">组件</span><span class="sxs-lookup"><span data-stu-id="e03d3-109">Component</span></span>|<span data-ttu-id="e03d3-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="e03d3-110">EDI Engine</span></span>|  
|<span data-ttu-id="e03d3-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="e03d3-111">Symbolic Name</span></span>|<span data-ttu-id="e03d3-112">X12UnexpectedSegmentDescription</span><span class="sxs-lookup"><span data-stu-id="e03d3-112">X12UnexpectedSegmentDescription</span></span>|  
|<span data-ttu-id="e03d3-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="e03d3-113">Message Text</span></span>|<span data-ttu-id="e03d3-114">意外段</span><span class="sxs-lookup"><span data-stu-id="e03d3-114">Unexpected segment</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e03d3-115">解释</span><span class="sxs-lookup"><span data-stu-id="e03d3-115">Explanation</span></span>  
 <span data-ttu-id="e03d3-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为该交换包含一个未由文档架构或服务架构定义的段。</span><span class="sxs-lookup"><span data-stu-id="e03d3-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contains a segment that is not defined by either the document schema or the service schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e03d3-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="e03d3-117">User Action</span></span>  
 <span data-ttu-id="e03d3-118">若要解决此错误，请让交换的发送方从交换中删除意外段，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="e03d3-118">To resolve this error, have the sender of the interchange remove the unexpected segment from the interchange, and then resend the interchange.</span></span>