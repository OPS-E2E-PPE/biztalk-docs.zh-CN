---
title: "无法合并操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2741790-2c27-4dc5-9299-680e170f0366
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82035f791abd18c597198567a6027ddf739424a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-merge-operations"></a><span data-ttu-id="8e279-102">无法合并操作</span><span class="sxs-lookup"><span data-stu-id="8e279-102">Unable to merge operations</span></span>
## <a name="details"></a><span data-ttu-id="8e279-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8e279-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8e279-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8e279-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="8e279-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="8e279-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="8e279-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8e279-106">Event ID</span></span>|<span data-ttu-id="8e279-107">0</span><span class="sxs-lookup"><span data-stu-id="8e279-107">0</span></span>|  
|<span data-ttu-id="8e279-108">事件源</span><span class="sxs-lookup"><span data-stu-id="8e279-108">Event Source</span></span>|<span data-ttu-id="8e279-109">0</span><span class="sxs-lookup"><span data-stu-id="8e279-109">0</span></span>|  
|<span data-ttu-id="8e279-110">组件</span><span class="sxs-lookup"><span data-stu-id="8e279-110">Component</span></span>|<span data-ttu-id="8e279-111">0</span><span class="sxs-lookup"><span data-stu-id="8e279-111">0</span></span>|  
|<span data-ttu-id="8e279-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="8e279-112">Symbolic Name</span></span>|<span data-ttu-id="8e279-113">0</span><span class="sxs-lookup"><span data-stu-id="8e279-113">0</span></span>|  
|<span data-ttu-id="8e279-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="8e279-114">Message Text</span></span>|<span data-ttu-id="8e279-115">无法合并操作</span><span class="sxs-lookup"><span data-stu-id="8e279-115">Unable to merge operations</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8e279-116">解释</span><span class="sxs-lookup"><span data-stu-id="8e279-116">Explanation</span></span>  
 <span data-ttu-id="8e279-117">此错误表示由于名称冲突或通信方向不同，导致无法合并操作。</span><span class="sxs-lookup"><span data-stu-id="8e279-117">This error indicates the operations cannot be merged due to name collision or due to different communication directions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8e279-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="8e279-118">User Action</span></span>  
 <span data-ttu-id="8e279-119">尝试发布没有名称冲突，但具有相同通信模式的业务流程。</span><span class="sxs-lookup"><span data-stu-id="8e279-119">Try to publish the orchestration without name collision and the same communication pattern.</span></span>