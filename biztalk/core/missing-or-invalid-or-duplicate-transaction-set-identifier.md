---
title: 缺少或无效或重复事务集标识符 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8580aab2-9fa4-43fb-b643-10621926591e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75251d0210be4ed34a74ba0f3f5cadf84d9941b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263501"
---
# <a name="missing-or-invalid-or-duplicate-transaction-set-identifier"></a><span data-ttu-id="56ea8-102">事务集标识符缺失或无效或重复</span><span class="sxs-lookup"><span data-stu-id="56ea8-102">Missing or invalid or duplicate Transaction set identifier</span></span>
## <a name="details"></a><span data-ttu-id="56ea8-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="56ea8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="56ea8-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="56ea8-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="56ea8-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="56ea8-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="56ea8-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="56ea8-106">Event ID</span></span>|-|  
|<span data-ttu-id="56ea8-107">事件源</span><span class="sxs-lookup"><span data-stu-id="56ea8-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="56ea8-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="56ea8-108"> EDI</span></span>|  
|<span data-ttu-id="56ea8-109">组件</span><span class="sxs-lookup"><span data-stu-id="56ea8-109">Component</span></span>|<span data-ttu-id="56ea8-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="56ea8-110">EDI Engine</span></span>|  
|<span data-ttu-id="56ea8-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="56ea8-111">Symbolic Name</span></span>|<span data-ttu-id="56ea8-112">X12TsMissingOrInvalidTsIdentiferDescription2</span><span class="sxs-lookup"><span data-stu-id="56ea8-112">X12TsMissingOrInvalidTsIdentiferDescription2</span></span>|  
|<span data-ttu-id="56ea8-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="56ea8-113">Message Text</span></span>|<span data-ttu-id="56ea8-114">事务集标识符“{0}”缺失或无效或重复</span><span class="sxs-lookup"><span data-stu-id="56ea8-114">Missing or invalid or duplicate Transaction set identifier '{0}'</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="56ea8-115">解释</span><span class="sxs-lookup"><span data-stu-id="56ea8-115">Explanation</span></span>  
 <span data-ttu-id="56ea8-116">此错误/警告/信息事件表明接收管道或发送管道无法处理 X12 交换，因为事务集标识符的值（在 ST01 字段中）缺失、重复或无效。</span><span class="sxs-lookup"><span data-stu-id="56ea8-116">This Error/Warning/Information event indicates that the receive or send pipeline could not process the X12 interchange because the value of the transaction set identifier (in the ST01 field) was missing, a duplicate, or had an invalid value.</span></span> <span data-ttu-id="56ea8-117">如果文档架构没有 ST 标头和 SE 尾部，则可能会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="56ea8-117">This can occur if the document schema does not have an ST header and an SE trailer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="56ea8-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="56ea8-118">User Action</span></span>  
 <span data-ttu-id="56ea8-119">若要解决此错误，请确保交换具有与 ST01 字段对应的值并且确保架构具有与 ST 标头和 SE 尾部对应的条目。</span><span class="sxs-lookup"><span data-stu-id="56ea8-119">To resolve this error, make sure that the interchange has a value for the ST01 field and that the schema has an entry for the ST header and SE trailer.</span></span> <span data-ttu-id="56ea8-120">验证 ST01 的值是否是有效的三位文档类型的表示符。</span><span class="sxs-lookup"><span data-stu-id="56ea8-120">Verify that the value of ST01 is a valid three-digit document-type designator.</span></span> <span data-ttu-id="56ea8-121">验证 ST01 字段是否未与另一个事务集的 ST01 字段重复。</span><span class="sxs-lookup"><span data-stu-id="56ea8-121">Verify that the ST01 field is not a duplicate with the ST01 field of another transaction set.</span></span>