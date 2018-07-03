---
title: 由于类型名冲突无法继续 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ced6de4-0950-498e-a548-5c85419726d8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 742d537f2329c53cd974abbaac9a6b9f7f8f5126
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008478"
---
# <a name="cannot-proceed-due-to-type-name-clash"></a><span data-ttu-id="423a2-102">由于类型名冲突无法继续</span><span class="sxs-lookup"><span data-stu-id="423a2-102">Cannot proceed due to type name clash</span></span>
## <a name="details"></a><span data-ttu-id="423a2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="423a2-103">Details</span></span>  
  
|                 |                                                                                       |
|-----------------|---------------------------------------------------------------------------------------|
|  <span data-ttu-id="423a2-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="423a2-104">Product Name</span></span>   |  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="423a2-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="423a2-105">Product Version</span></span> |              [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]               |
|    <span data-ttu-id="423a2-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="423a2-106">Event ID</span></span>     |                                           <span data-ttu-id="423a2-107">0</span><span class="sxs-lookup"><span data-stu-id="423a2-107">0</span></span>                                           |
|  <span data-ttu-id="423a2-108">事件源</span><span class="sxs-lookup"><span data-stu-id="423a2-108">Event Source</span></span>   |                                           <span data-ttu-id="423a2-109">0</span><span class="sxs-lookup"><span data-stu-id="423a2-109">0</span></span>                                           |
|    <span data-ttu-id="423a2-110">组件</span><span class="sxs-lookup"><span data-stu-id="423a2-110">Component</span></span>    |                                           <span data-ttu-id="423a2-111">0</span><span class="sxs-lookup"><span data-stu-id="423a2-111">0</span></span>                                           |
|  <span data-ttu-id="423a2-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="423a2-112">Symbolic Name</span></span>  |                                           <span data-ttu-id="423a2-113">0</span><span class="sxs-lookup"><span data-stu-id="423a2-113">0</span></span>                                           |
|  <span data-ttu-id="423a2-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="423a2-114">Message Text</span></span>   | <span data-ttu-id="423a2-115">由于类型名称冲突而无法继续。</span><span class="sxs-lookup"><span data-stu-id="423a2-115">Cannot proceed due to type name clash.</span></span> <span data-ttu-id="423a2-116">名称"{0}"命名空间中已存在</span><span class="sxs-lookup"><span data-stu-id="423a2-116">The name "{0}" already exists in the namespace</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="423a2-117">解释</span><span class="sxs-lookup"><span data-stu-id="423a2-117">Explanation</span></span>  
 <span data-ttu-id="423a2-118">此错误表明定义的同一命名空间中的多个项目具有同一名称。</span><span class="sxs-lookup"><span data-stu-id="423a2-118">This error indicates multiple artifacts in the same defined namespace have the same name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="423a2-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="423a2-119">User Action</span></span>  
 <span data-ttu-id="423a2-120">重新命名相同命名空间中的项目或将其置于不同命名空间中。</span><span class="sxs-lookup"><span data-stu-id="423a2-120">Rename the artifacts in the same namespace or put them in a different namespace.</span></span>