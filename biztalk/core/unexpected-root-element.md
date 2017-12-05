---
title: "意外的根元素 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ecccf57e-9295-4a6d-95b6-efec662478cf
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec4ed8e39a05f81984dca21794eca3d829ba8f42
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="unexpected-root-element"></a><span data-ttu-id="90afb-102">意外的根元素</span><span class="sxs-lookup"><span data-stu-id="90afb-102">Unexpected root element</span></span>
## <a name="details"></a><span data-ttu-id="90afb-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="90afb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="90afb-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="90afb-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="90afb-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="90afb-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="90afb-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="90afb-106">Event ID</span></span>|<span data-ttu-id="90afb-107">0</span><span class="sxs-lookup"><span data-stu-id="90afb-107">0</span></span>|  
|<span data-ttu-id="90afb-108">事件源</span><span class="sxs-lookup"><span data-stu-id="90afb-108">Event Source</span></span>|<span data-ttu-id="90afb-109">0</span><span class="sxs-lookup"><span data-stu-id="90afb-109">0</span></span>|  
|<span data-ttu-id="90afb-110">组件</span><span class="sxs-lookup"><span data-stu-id="90afb-110">Component</span></span>|<span data-ttu-id="90afb-111">0</span><span class="sxs-lookup"><span data-stu-id="90afb-111">0</span></span>|  
|<span data-ttu-id="90afb-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="90afb-112">Symbolic Name</span></span>|<span data-ttu-id="90afb-113">0</span><span class="sxs-lookup"><span data-stu-id="90afb-113">0</span></span>|  
|<span data-ttu-id="90afb-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="90afb-114">Message Text</span></span>|<span data-ttu-id="90afb-115">意外的根元素</span><span class="sxs-lookup"><span data-stu-id="90afb-115">Unexpected root element</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="90afb-116">解释</span><span class="sxs-lookup"><span data-stu-id="90afb-116">Explanation</span></span>  
 <span data-ttu-id="90afb-117">标头属性将不在\<标头\>...\</headers\>格式。</span><span class="sxs-lookup"><span data-stu-id="90afb-117">Header property is not in \<headers\>….\</headers\> format.</span></span> <span data-ttu-id="90afb-118">这种情况通常发生在 InboundHeaders 和 OutboundCustomHeaders。</span><span class="sxs-lookup"><span data-stu-id="90afb-118">This situation normally applies to InboundHeaders and OutboundCustomHeaders.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="90afb-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="90afb-119">User Action</span></span>  
 <span data-ttu-id="90afb-120">确保标头属性中的格式\<标头\>...\</headers\>。</span><span class="sxs-lookup"><span data-stu-id="90afb-120">Ensure that header property is in the format of  \<headers\>…\</headers\>.</span></span>