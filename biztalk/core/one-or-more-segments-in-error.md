---
title: "在错误中的一个或多个段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ee86667-e72a-4f1b-8d5c-15ca710dbe5d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 340c722bc96ec8efdf2f48e6b40260aa5323e675
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="one-or-more-segments-in-error"></a><span data-ttu-id="a26b9-102">有一个或多个段出错</span><span class="sxs-lookup"><span data-stu-id="a26b9-102">One or more segments in error</span></span>
## <a name="details"></a><span data-ttu-id="a26b9-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a26b9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a26b9-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a26b9-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="a26b9-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="a26b9-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="a26b9-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a26b9-106">Event ID</span></span>|-|  
|<span data-ttu-id="a26b9-107">事件源</span><span class="sxs-lookup"><span data-stu-id="a26b9-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a26b9-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="a26b9-108"> EDI</span></span>|  
|<span data-ttu-id="a26b9-109">组件</span><span class="sxs-lookup"><span data-stu-id="a26b9-109">Component</span></span>|<span data-ttu-id="a26b9-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="a26b9-110">EDI Engine</span></span>|  
|<span data-ttu-id="a26b9-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="a26b9-111">Symbolic Name</span></span>|<span data-ttu-id="a26b9-112">X12TsOneOrMoreSegmentsInErrorDescription</span><span class="sxs-lookup"><span data-stu-id="a26b9-112">X12TsOneOrMoreSegmentsInErrorDescription</span></span>|  
|<span data-ttu-id="a26b9-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="a26b9-113">Message Text</span></span>|<span data-ttu-id="a26b9-114">有一个或多个段出错</span><span class="sxs-lookup"><span data-stu-id="a26b9-114">One or more segments in error</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a26b9-115">解释</span><span class="sxs-lookup"><span data-stu-id="a26b9-115">Explanation</span></span>  
 <span data-ttu-id="a26b9-116">此错误/警告/信息事件表明交换中的一个或多个段不符合管理它们的架构。</span><span class="sxs-lookup"><span data-stu-id="a26b9-116">This Error/Warning/Information event indicates that one or more segments in the interchange did not conform to the schema governing them.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a26b9-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="a26b9-117">User Action</span></span>  
 <span data-ttu-id="a26b9-118">若要解决此错误，请确定哪个段有错误，打开管理该段的架构，并通过该架构确定该段出错的原因。</span><span class="sxs-lookup"><span data-stu-id="a26b9-118">To resolve this error, determine which segment is in error, open the schema governing that segment, and determine from that schema why the segment is in error.</span></span>