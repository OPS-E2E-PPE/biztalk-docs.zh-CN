---
title: 包含组数不匹配 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d61ac17-92cd-4a5e-81e6-e2c6fc4085bb
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f02262012a5d02cebaf86fae5a4d19d9b5486d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263029"
---
# <a name="number-of-included-groups-do-not-match"></a><span data-ttu-id="0f9a4-102">包括的组的数目不匹配</span><span class="sxs-lookup"><span data-stu-id="0f9a4-102">Number of included groups do not match</span></span>
## <a name="details"></a><span data-ttu-id="0f9a4-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0f9a4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0f9a4-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0f9a4-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="0f9a4-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="0f9a4-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="0f9a4-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0f9a4-106">Event ID</span></span>|-|  
|<span data-ttu-id="0f9a4-107">事件源</span><span class="sxs-lookup"><span data-stu-id="0f9a4-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0f9a4-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0f9a4-108"> EDI</span></span>|  
|<span data-ttu-id="0f9a4-109">组件</span><span class="sxs-lookup"><span data-stu-id="0f9a4-109">Component</span></span>|<span data-ttu-id="0f9a4-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="0f9a4-110">EDI Engine</span></span>|  
|<span data-ttu-id="0f9a4-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="0f9a4-111">Symbolic Name</span></span>|<span data-ttu-id="0f9a4-112">X12Ta1InvalidNumberOfIncludedGroupsDescription</span><span class="sxs-lookup"><span data-stu-id="0f9a4-112">X12Ta1InvalidNumberOfIncludedGroupsDescription</span></span>|  
|<span data-ttu-id="0f9a4-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="0f9a4-113">Message Text</span></span>|<span data-ttu-id="0f9a4-114">数的包含组不匹配</span><span class="sxs-lookup"><span data-stu-id="0f9a4-114">Number Of included groups do not match</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0f9a4-115">解释</span><span class="sxs-lookup"><span data-stu-id="0f9a4-115">Explanation</span></span>  
 <span data-ttu-id="0f9a4-116">此错误/警告/信息事件表明交换中的组数不等于交换尾部（IEA01 字段）中的数量。</span><span class="sxs-lookup"><span data-stu-id="0f9a4-116">This Error/Warning/Information event indicates that the number of groups in the interchange does not equal the number in the interchange trailer (IEA01 field).</span></span> <span data-ttu-id="0f9a4-117">保留交换并且出错时挂起交换时会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="0f9a4-117">This occurs when the interchange is preserved and the interchange is suspended on an error.</span></span> <span data-ttu-id="0f9a4-118">（如果保留交换并且出错时挂起事务集或者拆分交换，则不会发布此错误消息。）</span><span class="sxs-lookup"><span data-stu-id="0f9a4-118">(The error message is not posted if the interchange is preserved and the transaction sets are suspended on an error, or if the interchange is split.)</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0f9a4-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="0f9a4-119">User Action</span></span>  
 <span data-ttu-id="0f9a4-120">若要解决此错误，请确保交换尾部的 IEA01 字段中的数量与交换中的组数相同，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="0f9a4-120">To resolve this error, make sure that the number in the IEA01 field of the interchange trailer is the same as the number of groups in the interchange, and then resend the interchange.</span></span>