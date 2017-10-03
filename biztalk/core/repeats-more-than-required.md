---
title: "重复多个所需 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fec52b5b-e95f-479e-8922-dcf17dcefee7
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cb8f9e324c9d09e09649719c98e3f684b0d81f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="repeats-more-than-required"></a><span data-ttu-id="81beb-102">重复次数大于必需次数</span><span class="sxs-lookup"><span data-stu-id="81beb-102">Repeats more than required</span></span>
## <a name="details"></a><span data-ttu-id="81beb-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="81beb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="81beb-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="81beb-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="81beb-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="81beb-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="81beb-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="81beb-106">Event ID</span></span>|-|  
|<span data-ttu-id="81beb-107">事件源</span><span class="sxs-lookup"><span data-stu-id="81beb-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="81beb-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="81beb-108"> EDI</span></span>|  
|<span data-ttu-id="81beb-109">组件</span><span class="sxs-lookup"><span data-stu-id="81beb-109">Component</span></span>|<span data-ttu-id="81beb-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="81beb-110">EDI Engine</span></span>|  
|<span data-ttu-id="81beb-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="81beb-111">Symbolic Name</span></span>|<span data-ttu-id="81beb-112">X12FeRepeatsMoreThanRequiredDescription</span><span class="sxs-lookup"><span data-stu-id="81beb-112">X12FeRepeatsMoreThanRequiredDescription</span></span>|  
|<span data-ttu-id="81beb-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="81beb-113">Message Text</span></span>|<span data-ttu-id="81beb-114">重复次数大于必需次数</span><span class="sxs-lookup"><span data-stu-id="81beb-114">Repeats more than required</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="81beb-115">解释</span><span class="sxs-lookup"><span data-stu-id="81beb-115">Explanation</span></span>  
 <span data-ttu-id="81beb-116">此错误/警告/信息事件表明 X12 交换中位于循环内外的段的重复次数大于文档架构所需的次数。</span><span class="sxs-lookup"><span data-stu-id="81beb-116">This Error/Warning/Information event indicates that segments in an X12 interchange that are either inside or outside of a loop repeated more times than required by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="81beb-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="81beb-117">User Action</span></span>  
 <span data-ttu-id="81beb-118">若要解决此错误，请确保位于交换中某个循环内外的段重复架构中指定的次数，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="81beb-118">To resolve this error, make sure that the segments that are either inside or outside of a loop in the interchange repeat the numbers of times specified in the schema, and then resend the interchange.</span></span>