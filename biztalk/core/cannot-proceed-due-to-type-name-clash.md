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
ms.openlocfilehash: 2a2423e0ba1ba537bde860b2539b77e59e67857a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357621"
---
# <a name="cannot-proceed-due-to-type-name-clash"></a><span data-ttu-id="3b0b4-102">由于类型名冲突无法继续</span><span class="sxs-lookup"><span data-stu-id="3b0b4-102">Cannot proceed due to type name clash</span></span>
## <a name="details"></a><span data-ttu-id="3b0b4-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="3b0b4-103">Details</span></span>  
  
|                 |                                                                                       |
|-----------------|---------------------------------------------------------------------------------------|
|  <span data-ttu-id="3b0b4-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="3b0b4-104">Product Name</span></span>   |  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="3b0b4-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="3b0b4-105">Product Version</span></span> |              [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]               |
|    <span data-ttu-id="3b0b4-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="3b0b4-106">Event ID</span></span>     |                                           <span data-ttu-id="3b0b4-107">0</span><span class="sxs-lookup"><span data-stu-id="3b0b4-107">0</span></span>                                           |
|  <span data-ttu-id="3b0b4-108">事件源</span><span class="sxs-lookup"><span data-stu-id="3b0b4-108">Event Source</span></span>   |                                           <span data-ttu-id="3b0b4-109">0</span><span class="sxs-lookup"><span data-stu-id="3b0b4-109">0</span></span>                                           |
|    <span data-ttu-id="3b0b4-110">组件</span><span class="sxs-lookup"><span data-stu-id="3b0b4-110">Component</span></span>    |                                           <span data-ttu-id="3b0b4-111">0</span><span class="sxs-lookup"><span data-stu-id="3b0b4-111">0</span></span>                                           |
|  <span data-ttu-id="3b0b4-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="3b0b4-112">Symbolic Name</span></span>  |                                           <span data-ttu-id="3b0b4-113">0</span><span class="sxs-lookup"><span data-stu-id="3b0b4-113">0</span></span>                                           |
|  <span data-ttu-id="3b0b4-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="3b0b4-114">Message Text</span></span>   | <span data-ttu-id="3b0b4-115">由于类型名称冲突而无法继续。</span><span class="sxs-lookup"><span data-stu-id="3b0b4-115">Cannot proceed due to type name clash.</span></span> <span data-ttu-id="3b0b4-116">名称"{0}"命名空间中已存在</span><span class="sxs-lookup"><span data-stu-id="3b0b4-116">The name "{0}" already exists in the namespace</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="3b0b4-117">解释</span><span class="sxs-lookup"><span data-stu-id="3b0b4-117">Explanation</span></span>  
 <span data-ttu-id="3b0b4-118">此错误表明定义的同一命名空间中的多个项目具有同一名称。</span><span class="sxs-lookup"><span data-stu-id="3b0b4-118">This error indicates multiple artifacts in the same defined namespace have the same name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3b0b4-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="3b0b4-119">User Action</span></span>  
 <span data-ttu-id="3b0b4-120">重新命名相同命名空间中的项目或将其置于不同命名空间中。</span><span class="sxs-lookup"><span data-stu-id="3b0b4-120">Rename the artifacts in the same namespace or put them in a different namespace.</span></span>