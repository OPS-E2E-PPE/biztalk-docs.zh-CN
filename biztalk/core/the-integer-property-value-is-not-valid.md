---
title: "整数属性值不是有效 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31d4e9a7-4336-40f1-997a-9f79d86b26d2
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acbb350d9dd8fe77e42bb7e8b3cdf4617c87a2f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-integer-property-value-is-not-valid"></a><span data-ttu-id="e6f3c-102">integer 属性值无效</span><span class="sxs-lookup"><span data-stu-id="e6f3c-102">The integer property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="e6f3c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6f3c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e6f3c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e6f3c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e6f3c-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="e6f3c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="e6f3c-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e6f3c-106">Event ID</span></span>|-|  
|<span data-ttu-id="e6f3c-107">事件源</span><span class="sxs-lookup"><span data-stu-id="e6f3c-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e6f3c-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="e6f3c-108"> EDI</span></span>|  
|<span data-ttu-id="e6f3c-109">组件</span><span class="sxs-lookup"><span data-stu-id="e6f3c-109">Component</span></span>|<span data-ttu-id="e6f3c-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="e6f3c-110">EDI Engine</span></span>|  
|<span data-ttu-id="e6f3c-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="e6f3c-111">Symbolic Name</span></span>|<span data-ttu-id="e6f3c-112">Err_InvalidInteger</span><span class="sxs-lookup"><span data-stu-id="e6f3c-112">Err_InvalidInteger</span></span>|  
|<span data-ttu-id="e6f3c-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="e6f3c-113">Message Text</span></span>|<span data-ttu-id="e6f3c-114">integer 属性值无效。</span><span class="sxs-lookup"><span data-stu-id="e6f3c-114">The integer property value is not valid.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e6f3c-115">解释</span><span class="sxs-lookup"><span data-stu-id="e6f3c-115">Explanation</span></span>  
 <span data-ttu-id="e6f3c-116">此错误/警告/信息事件表明 BizTalk Server 在尝试决定是否批处理消息时无法比较上下文属性。</span><span class="sxs-lookup"><span data-stu-id="e6f3c-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide whether to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e6f3c-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="e6f3c-117">User Action</span></span>  
 <span data-ttu-id="e6f3c-118">若要解决此错误，请确保在活动的批处理中提供的筛选器没有指定 XSD 类型为 integer 且值无效的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="e6f3c-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify a context property which has an XSD type of integer with an invalid value.</span></span>