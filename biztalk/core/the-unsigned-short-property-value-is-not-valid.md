---
title: 无符号 Short 属性值不是有效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31600ed6-20bc-4382-9eb3-4d6fa9646411
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 198596c03d6ef7c5cd3b9005458f6eea18bd9b9a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011734"
---
# <a name="the-unsigned-short-property-value-is-not-valid"></a><span data-ttu-id="59147-102">无符号 Short 属性值无效</span><span class="sxs-lookup"><span data-stu-id="59147-102">The unsigned Short property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="59147-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="59147-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="59147-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="59147-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="59147-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="59147-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="59147-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="59147-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="59147-107">事件源</span><span class="sxs-lookup"><span data-stu-id="59147-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="59147-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="59147-108"> EDI</span></span> |
|    <span data-ttu-id="59147-109">组件</span><span class="sxs-lookup"><span data-stu-id="59147-109">Component</span></span>    |                                       <span data-ttu-id="59147-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="59147-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="59147-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="59147-111">Symbolic Name</span></span>  |                                <span data-ttu-id="59147-112">Err_InvalidUnsignedShort</span><span class="sxs-lookup"><span data-stu-id="59147-112">Err_InvalidUnsignedShort</span></span>                                |
|  <span data-ttu-id="59147-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="59147-113">Message Text</span></span>   |                    <span data-ttu-id="59147-114">无符号 Short 属性值无效。</span><span class="sxs-lookup"><span data-stu-id="59147-114">The unsigned Short property value is not valid.</span></span>                     |
  
## <a name="explanation"></a><span data-ttu-id="59147-115">解释</span><span class="sxs-lookup"><span data-stu-id="59147-115">Explanation</span></span>  
 <span data-ttu-id="59147-116">此错误/警告/信息事件表明 BizTalk Server 在尝试决定是否批处理消息时无法比较上下文属性。</span><span class="sxs-lookup"><span data-stu-id="59147-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide whether to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="59147-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="59147-117">User Action</span></span>  
 <span data-ttu-id="59147-118">若要解决此错误，请确保在活动的批处理中提供的筛选器没有指定 XSD 类型为无符号 Short 且值无效的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="59147-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify a context property which has an XSD type of unsigned Short with an invalid value.</span></span>