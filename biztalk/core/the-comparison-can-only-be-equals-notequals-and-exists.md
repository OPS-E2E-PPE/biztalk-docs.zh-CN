---
title: 比较运算符只能为 Equals、 NotEquals 和 Exists |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aad902a2-d0dc-4d91-87a7-a6305e2f40e0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50499ea6ab9f002d36c213a8bca871884d3b077a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023467"
---
# <a name="the-comparison-can-only-be-equals-notequals-and-exists"></a><span data-ttu-id="45a95-102">比较运算符只能为 Equals、NotEquals 和 Exists</span><span class="sxs-lookup"><span data-stu-id="45a95-102">The Comparison can only be Equals, NotEquals and Exists</span></span>
## <a name="details"></a><span data-ttu-id="45a95-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="45a95-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="45a95-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="45a95-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="45a95-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="45a95-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="45a95-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="45a95-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="45a95-107">事件源</span><span class="sxs-lookup"><span data-stu-id="45a95-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="45a95-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="45a95-108"> EDI</span></span> |
|    <span data-ttu-id="45a95-109">组件</span><span class="sxs-lookup"><span data-stu-id="45a95-109">Component</span></span>    |                                       <span data-ttu-id="45a95-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="45a95-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="45a95-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="45a95-111">Symbolic Name</span></span>  |                                 <span data-ttu-id="45a95-112">Err_InvalidComparision</span><span class="sxs-lookup"><span data-stu-id="45a95-112">Err_InvalidComparision</span></span>                                 |
|  <span data-ttu-id="45a95-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="45a95-113">Message Text</span></span>   |                <span data-ttu-id="45a95-114">比较运算符只能为 Equals、NotEquals 和 Exists。</span><span class="sxs-lookup"><span data-stu-id="45a95-114">The Comparison can only be Equals, NotEquals and Exists.</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="45a95-115">解释</span><span class="sxs-lookup"><span data-stu-id="45a95-115">Explanation</span></span>  
 <span data-ttu-id="45a95-116">此错误/警告/信息事件表明 BizTalk Server 在尝试决定批处理消息时无法比较上下文属性。</span><span class="sxs-lookup"><span data-stu-id="45a95-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="45a95-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="45a95-117">User Action</span></span>  
 <span data-ttu-id="45a95-118">若要解决此错误，请确保在活动的批处理中提供的筛选器没有指定除 Equals、 NotEquals 和 Exists 的 XSD 类型的不支持其他操作的运算符。</span><span class="sxs-lookup"><span data-stu-id="45a95-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify an operator  other than Equals, NotEquals and Exists for XSD types that don’t support other operations.</span></span>