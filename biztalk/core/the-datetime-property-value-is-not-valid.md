---
title: "日期时间属性值不是有效 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0dc527e-82d5-40dc-941e-f2e056163017
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f6f784bc04e243de3bbb3cfb1c1acc760c35015
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-datetime-property-value-is-not-valid"></a><span data-ttu-id="67bf0-102">datetime 属性值无效</span><span class="sxs-lookup"><span data-stu-id="67bf0-102">The datetime property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="67bf0-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="67bf0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="67bf0-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="67bf0-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="67bf0-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="67bf0-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="67bf0-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="67bf0-106">Event ID</span></span>|-|  
|<span data-ttu-id="67bf0-107">事件源</span><span class="sxs-lookup"><span data-stu-id="67bf0-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="67bf0-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="67bf0-108"> EDI</span></span>|  
|<span data-ttu-id="67bf0-109">组件</span><span class="sxs-lookup"><span data-stu-id="67bf0-109">Component</span></span>|<span data-ttu-id="67bf0-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="67bf0-110">EDI Engine</span></span>|  
|<span data-ttu-id="67bf0-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="67bf0-111">Symbolic Name</span></span>|<span data-ttu-id="67bf0-112">Err_InvalidDateTime</span><span class="sxs-lookup"><span data-stu-id="67bf0-112">Err_InvalidDateTime</span></span>|  
|<span data-ttu-id="67bf0-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="67bf0-113">Message Text</span></span>|<span data-ttu-id="67bf0-114">datetime 属性值无效。</span><span class="sxs-lookup"><span data-stu-id="67bf0-114">The datetime property value is not valid.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="67bf0-115">解释</span><span class="sxs-lookup"><span data-stu-id="67bf0-115">Explanation</span></span>  
 <span data-ttu-id="67bf0-116">此错误/警告/信息事件表明 BizTalk Server 在尝试决定是否批处理消息时无法比较上下文属性。</span><span class="sxs-lookup"><span data-stu-id="67bf0-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide whether to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="67bf0-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="67bf0-117">User Action</span></span>  
 <span data-ttu-id="67bf0-118">若要解决此错误，请确保在活动的批处理中提供的筛选器没有指定 XSD 类型为日期且值为无效日期的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="67bf0-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify a context property which has an XSD type of date and the value is invalid date.</span></span>