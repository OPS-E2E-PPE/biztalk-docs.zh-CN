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
ms.openlocfilehash: 5119b9b896b3b37b24b9b3151c5e11664dda8774
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="unexpected-root-element"></a><span data-ttu-id="f2be2-102">意外的根元素</span><span class="sxs-lookup"><span data-stu-id="f2be2-102">Unexpected root element</span></span>
## <a name="details"></a><span data-ttu-id="f2be2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f2be2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f2be2-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f2be2-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f2be2-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="f2be2-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="f2be2-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f2be2-106">Event ID</span></span>|<span data-ttu-id="f2be2-107">0</span><span class="sxs-lookup"><span data-stu-id="f2be2-107">0</span></span>|  
|<span data-ttu-id="f2be2-108">事件源</span><span class="sxs-lookup"><span data-stu-id="f2be2-108">Event Source</span></span>|<span data-ttu-id="f2be2-109">0</span><span class="sxs-lookup"><span data-stu-id="f2be2-109">0</span></span>|  
|<span data-ttu-id="f2be2-110">组件</span><span class="sxs-lookup"><span data-stu-id="f2be2-110">Component</span></span>|<span data-ttu-id="f2be2-111">0</span><span class="sxs-lookup"><span data-stu-id="f2be2-111">0</span></span>|  
|<span data-ttu-id="f2be2-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="f2be2-112">Symbolic Name</span></span>|<span data-ttu-id="f2be2-113">0</span><span class="sxs-lookup"><span data-stu-id="f2be2-113">0</span></span>|  
|<span data-ttu-id="f2be2-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="f2be2-114">Message Text</span></span>|<span data-ttu-id="f2be2-115">意外的根元素</span><span class="sxs-lookup"><span data-stu-id="f2be2-115">Unexpected root element</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f2be2-116">解释</span><span class="sxs-lookup"><span data-stu-id="f2be2-116">Explanation</span></span>  
 <span data-ttu-id="f2be2-117">标头属性将不在\<标头 >...\</headers > 格式。</span><span class="sxs-lookup"><span data-stu-id="f2be2-117">Header property is not in \<headers>….\</headers> format.</span></span> <span data-ttu-id="f2be2-118">这种情况通常发生在 InboundHeaders 和 OutboundCustomHeaders。</span><span class="sxs-lookup"><span data-stu-id="f2be2-118">This situation normally applies to InboundHeaders and OutboundCustomHeaders.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f2be2-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="f2be2-119">User Action</span></span>  
 <span data-ttu-id="f2be2-120">确保标头属性中的格式\<标头 >...\</headers >。</span><span class="sxs-lookup"><span data-stu-id="f2be2-120">Ensure that header property is in the format of  \<headers>…\</headers>.</span></span>