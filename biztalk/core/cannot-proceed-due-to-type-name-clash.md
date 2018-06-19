---
title: 由于类型名称冲突，无法进行 |Microsoft 文档
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
ms.openlocfilehash: 2de1d4962db915a462990962e933c1413a408eee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231205"
---
# <a name="cannot-proceed-due-to-type-name-clash"></a><span data-ttu-id="ab76e-102">由于类型名冲突无法继续</span><span class="sxs-lookup"><span data-stu-id="ab76e-102">Cannot proceed due to type name clash</span></span>
## <a name="details"></a><span data-ttu-id="ab76e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ab76e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ab76e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ab76e-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ab76e-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ab76e-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="ab76e-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ab76e-106">Event ID</span></span>|<span data-ttu-id="ab76e-107">0</span><span class="sxs-lookup"><span data-stu-id="ab76e-107">0</span></span>|  
|<span data-ttu-id="ab76e-108">事件源</span><span class="sxs-lookup"><span data-stu-id="ab76e-108">Event Source</span></span>|<span data-ttu-id="ab76e-109">0</span><span class="sxs-lookup"><span data-stu-id="ab76e-109">0</span></span>|  
|<span data-ttu-id="ab76e-110">组件</span><span class="sxs-lookup"><span data-stu-id="ab76e-110">Component</span></span>|<span data-ttu-id="ab76e-111">0</span><span class="sxs-lookup"><span data-stu-id="ab76e-111">0</span></span>|  
|<span data-ttu-id="ab76e-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="ab76e-112">Symbolic Name</span></span>|<span data-ttu-id="ab76e-113">0</span><span class="sxs-lookup"><span data-stu-id="ab76e-113">0</span></span>|  
|<span data-ttu-id="ab76e-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="ab76e-114">Message Text</span></span>|<span data-ttu-id="ab76e-115">由于类型名称冲突而无法继续。</span><span class="sxs-lookup"><span data-stu-id="ab76e-115">Cannot proceed due to type name clash.</span></span> <span data-ttu-id="ab76e-116">命名空间中已存在名称“{0}”</span><span class="sxs-lookup"><span data-stu-id="ab76e-116">The name "{0}" already exists in the namespace</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ab76e-117">解释</span><span class="sxs-lookup"><span data-stu-id="ab76e-117">Explanation</span></span>  
 <span data-ttu-id="ab76e-118">此错误表明定义的同一命名空间中的多个项目具有同一名称。</span><span class="sxs-lookup"><span data-stu-id="ab76e-118">This error indicates multiple artifacts in the same defined namespace have the same name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ab76e-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="ab76e-119">User Action</span></span>  
 <span data-ttu-id="ab76e-120">重新命名相同命名空间中的项目或将其置于不同命名空间中。</span><span class="sxs-lookup"><span data-stu-id="ab76e-120">Rename the artifacts in the same namespace or put them in a different namespace.</span></span>