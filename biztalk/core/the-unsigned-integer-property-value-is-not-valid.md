---
title: 无符号的 integer 属性值不是有效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63b0398f-7848-4971-8c08-95923d80cbe3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de6af46fc5719e8ccbe52dbfb419e104915d051e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973934"
---
# <a name="the-unsigned-integer-property-value-is-not-valid"></a><span data-ttu-id="4ed2a-102">无符号的 integer 属性值无效</span><span class="sxs-lookup"><span data-stu-id="4ed2a-102">The unsigned integer property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="4ed2a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="4ed2a-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="4ed2a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="4ed2a-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="4ed2a-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="4ed2a-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="4ed2a-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="4ed2a-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="4ed2a-107">事件源</span><span class="sxs-lookup"><span data-stu-id="4ed2a-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4ed2a-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="4ed2a-108"> EDI</span></span> |
|    <span data-ttu-id="4ed2a-109">组件</span><span class="sxs-lookup"><span data-stu-id="4ed2a-109">Component</span></span>    |                                       <span data-ttu-id="4ed2a-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="4ed2a-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="4ed2a-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="4ed2a-111">Symbolic Name</span></span>  |                               <span data-ttu-id="4ed2a-112">Err_InvalidUnsignedInteger</span><span class="sxs-lookup"><span data-stu-id="4ed2a-112">Err_InvalidUnsignedInteger</span></span>                               |
|  <span data-ttu-id="4ed2a-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="4ed2a-113">Message Text</span></span>   |                   <span data-ttu-id="4ed2a-114">无符号 integer 属性值无效。</span><span class="sxs-lookup"><span data-stu-id="4ed2a-114">The unsigned integer property value is not valid.</span></span>                    |
  
## <a name="explanation"></a><span data-ttu-id="4ed2a-115">解释</span><span class="sxs-lookup"><span data-stu-id="4ed2a-115">Explanation</span></span>  
 <span data-ttu-id="4ed2a-116">此错误/警告/信息事件表明 BizTalk Server 在尝试决定是否批处理消息时无法比较上下文属性。</span><span class="sxs-lookup"><span data-stu-id="4ed2a-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide whether to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4ed2a-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="4ed2a-117">User Action</span></span>  
 <span data-ttu-id="4ed2a-118">若要解决此错误，请确保在活动的批处理中提供的筛选器没有指定 XSD 类型为无符号 integer 且值无效的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="4ed2a-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify a context property which has an XSD type of unsigned integer with an invalid value.</span></span>