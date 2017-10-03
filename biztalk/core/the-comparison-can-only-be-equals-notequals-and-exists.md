---
title: "比较只能等于、 NotEquals 和 Exists |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aad902a2-d0dc-4d91-87a7-a6305e2f40e0
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: add062aebdbabe7d5965b46c7342595f96a7b8dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-comparison-can-only-be-equals-notequals-and-exists"></a><span data-ttu-id="3ecde-102">比较运算符只能为 Equals、NotEquals 和 Exists</span><span class="sxs-lookup"><span data-stu-id="3ecde-102">The Comparison can only be Equals, NotEquals and Exists</span></span>
## <a name="details"></a><span data-ttu-id="3ecde-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="3ecde-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3ecde-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="3ecde-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="3ecde-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="3ecde-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="3ecde-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="3ecde-106">Event ID</span></span>|-|  
|<span data-ttu-id="3ecde-107">事件源</span><span class="sxs-lookup"><span data-stu-id="3ecde-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3ecde-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="3ecde-108"> EDI</span></span>|  
|<span data-ttu-id="3ecde-109">组件</span><span class="sxs-lookup"><span data-stu-id="3ecde-109">Component</span></span>|<span data-ttu-id="3ecde-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="3ecde-110">EDI Engine</span></span>|  
|<span data-ttu-id="3ecde-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="3ecde-111">Symbolic Name</span></span>|<span data-ttu-id="3ecde-112">Err_InvalidComparision</span><span class="sxs-lookup"><span data-stu-id="3ecde-112">Err_InvalidComparision</span></span>|  
|<span data-ttu-id="3ecde-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="3ecde-113">Message Text</span></span>|<span data-ttu-id="3ecde-114">比较运算符只能为 Equals、NotEquals 和 Exists。</span><span class="sxs-lookup"><span data-stu-id="3ecde-114">The Comparison can only be Equals, NotEquals and Exists.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3ecde-115">解释</span><span class="sxs-lookup"><span data-stu-id="3ecde-115">Explanation</span></span>  
 <span data-ttu-id="3ecde-116">此错误/警告/信息事件表明 BizTalk Server 在尝试决定批处理消息时无法比较上下文属性。</span><span class="sxs-lookup"><span data-stu-id="3ecde-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3ecde-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="3ecde-117">User Action</span></span>  
 <span data-ttu-id="3ecde-118">若要解决此错误，请确保提供活动的批处理数中的筛选器不会指定不支持其他操作的 XSD 类型等于、 NotEquals 和 Exists 以外的运算符。</span><span class="sxs-lookup"><span data-stu-id="3ecde-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify an operator  other than Equals, NotEquals and Exists for XSD types that don’t support other operations.</span></span>