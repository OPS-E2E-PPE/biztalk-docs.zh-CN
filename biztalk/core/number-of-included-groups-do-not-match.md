---
title: 包含的组的数目不匹配 |Microsoft Docs
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
ms.openlocfilehash: cf61012de6ba864d6f0ff4e553b4c74e1d501c20
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988166"
---
# <a name="number-of-included-groups-do-not-match"></a><span data-ttu-id="b9c7c-102">包括的组的数目不匹配</span><span class="sxs-lookup"><span data-stu-id="b9c7c-102">Number of included groups do not match</span></span>
## <a name="details"></a><span data-ttu-id="b9c7c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b9c7c-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="b9c7c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b9c7c-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="b9c7c-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="b9c7c-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="b9c7c-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b9c7c-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="b9c7c-107">事件源</span><span class="sxs-lookup"><span data-stu-id="b9c7c-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b9c7c-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="b9c7c-108"> EDI</span></span> |
|    <span data-ttu-id="b9c7c-109">组件</span><span class="sxs-lookup"><span data-stu-id="b9c7c-109">Component</span></span>    |                                       <span data-ttu-id="b9c7c-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="b9c7c-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="b9c7c-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="b9c7c-111">Symbolic Name</span></span>  |                     <span data-ttu-id="b9c7c-112">X12Ta1InvalidNumberOfIncludedGroupsDescription</span><span class="sxs-lookup"><span data-stu-id="b9c7c-112">X12Ta1InvalidNumberOfIncludedGroupsDescription</span></span>                     |
|  <span data-ttu-id="b9c7c-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="b9c7c-113">Message Text</span></span>   |                         <span data-ttu-id="b9c7c-114">组的包含的数目不匹配</span><span class="sxs-lookup"><span data-stu-id="b9c7c-114">Number Of included groups do not match</span></span>                         |
  
## <a name="explanation"></a><span data-ttu-id="b9c7c-115">解释</span><span class="sxs-lookup"><span data-stu-id="b9c7c-115">Explanation</span></span>  
 <span data-ttu-id="b9c7c-116">此错误/警告/信息事件表明交换中的组数不等于交换尾部（IEA01 字段）中的数量。</span><span class="sxs-lookup"><span data-stu-id="b9c7c-116">This Error/Warning/Information event indicates that the number of groups in the interchange does not equal the number in the interchange trailer (IEA01 field).</span></span> <span data-ttu-id="b9c7c-117">保留交换并且出错时挂起交换时会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="b9c7c-117">This occurs when the interchange is preserved and the interchange is suspended on an error.</span></span> <span data-ttu-id="b9c7c-118">（如果保留交换并且出错时挂起事务集或者拆分交换，则不会发布此错误消息。）</span><span class="sxs-lookup"><span data-stu-id="b9c7c-118">(The error message is not posted if the interchange is preserved and the transaction sets are suspended on an error, or if the interchange is split.)</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b9c7c-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="b9c7c-119">User Action</span></span>  
 <span data-ttu-id="b9c7c-120">若要解决此错误，请确保交换尾部的 IEA01 字段中的数量与交换中的组数相同，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="b9c7c-120">To resolve this error, make sure that the number in the IEA01 field of the interchange trailer is the same as the number of groups in the interchange, and then resend the interchange.</span></span>