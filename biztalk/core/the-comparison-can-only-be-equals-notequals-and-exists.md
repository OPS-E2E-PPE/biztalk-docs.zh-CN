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
ms.openlocfilehash: 8f319775ec0e42f1a29209a275f0a65af3e6c9bc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298895"
---
# <a name="the-comparison-can-only-be-equals-notequals-and-exists"></a><span data-ttu-id="cb44b-102">比较运算符只能为 Equals、 NotEquals 和 Exists</span><span class="sxs-lookup"><span data-stu-id="cb44b-102">The Comparison can only be Equals, NotEquals and Exists</span></span>
## <a name="details"></a><span data-ttu-id="cb44b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="cb44b-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="cb44b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="cb44b-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="cb44b-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="cb44b-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="cb44b-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="cb44b-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="cb44b-107">事件源</span><span class="sxs-lookup"><span data-stu-id="cb44b-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="cb44b-108">EDI</span><span class="sxs-lookup"><span data-stu-id="cb44b-108">EDI</span></span> |
|    <span data-ttu-id="cb44b-109">组件</span><span class="sxs-lookup"><span data-stu-id="cb44b-109">Component</span></span>    |                                       <span data-ttu-id="cb44b-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="cb44b-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="cb44b-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="cb44b-111">Symbolic Name</span></span>  |                                 <span data-ttu-id="cb44b-112">Err_InvalidComparision</span><span class="sxs-lookup"><span data-stu-id="cb44b-112">Err_InvalidComparision</span></span>                                 |
|  <span data-ttu-id="cb44b-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="cb44b-113">Message Text</span></span>   |                <span data-ttu-id="cb44b-114">比较运算符只能为 Equals、 NotEquals 和 Exists。</span><span class="sxs-lookup"><span data-stu-id="cb44b-114">The Comparison can only be Equals, NotEquals and Exists.</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="cb44b-115">解释</span><span class="sxs-lookup"><span data-stu-id="cb44b-115">Explanation</span></span>  
 <span data-ttu-id="cb44b-116">此错误/警告/信息事件表明 BizTalk Server 在尝试决定批处理消息时无法比较上下文属性。</span><span class="sxs-lookup"><span data-stu-id="cb44b-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cb44b-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="cb44b-117">User Action</span></span>  
 <span data-ttu-id="cb44b-118">若要解决此错误，请确保在活动的批处理中提供的筛选器没有指定除 Equals、 NotEquals 和 Exists 的 XSD 类型的不支持其他操作的运算符。</span><span class="sxs-lookup"><span data-stu-id="cb44b-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify an operator  other than Equals, NotEquals and Exists for XSD types that don’t support other operations.</span></span>