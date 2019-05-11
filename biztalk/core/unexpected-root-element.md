---
title: 意外的根元素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ecccf57e-9295-4a6d-95b6-efec662478cf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a34b014015d97a6dfa9dc11345e47480f055a237
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399496"
---
# <a name="unexpected-root-element"></a><span data-ttu-id="725c6-102">意外的根元素</span><span class="sxs-lookup"><span data-stu-id="725c6-102">Unexpected root element</span></span>
## <a name="details"></a><span data-ttu-id="725c6-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="725c6-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="725c6-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="725c6-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="725c6-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="725c6-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="725c6-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="725c6-106">Event ID</span></span>     |                                         <span data-ttu-id="725c6-107">0</span><span class="sxs-lookup"><span data-stu-id="725c6-107">0</span></span>                                          |
|  <span data-ttu-id="725c6-108">事件源</span><span class="sxs-lookup"><span data-stu-id="725c6-108">Event Source</span></span>   |                                         <span data-ttu-id="725c6-109">0</span><span class="sxs-lookup"><span data-stu-id="725c6-109">0</span></span>                                          |
|    <span data-ttu-id="725c6-110">组件</span><span class="sxs-lookup"><span data-stu-id="725c6-110">Component</span></span>    |                                         <span data-ttu-id="725c6-111">0</span><span class="sxs-lookup"><span data-stu-id="725c6-111">0</span></span>                                          |
|  <span data-ttu-id="725c6-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="725c6-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="725c6-113">0</span><span class="sxs-lookup"><span data-stu-id="725c6-113">0</span></span>                                          |
|  <span data-ttu-id="725c6-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="725c6-114">Message Text</span></span>   |                              <span data-ttu-id="725c6-115">意外的根元素</span><span class="sxs-lookup"><span data-stu-id="725c6-115">Unexpected root element</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="725c6-116">解释</span><span class="sxs-lookup"><span data-stu-id="725c6-116">Explanation</span></span>  
 <span data-ttu-id="725c6-117">标头属性不在\<标头\>...\</headers\>格式。</span><span class="sxs-lookup"><span data-stu-id="725c6-117">Header property is not in \<headers\>….\</headers\> format.</span></span> <span data-ttu-id="725c6-118">这种情况通常适用于发生在 InboundHeaders 和 OutboundCustomHeaders。</span><span class="sxs-lookup"><span data-stu-id="725c6-118">This situation normally applies to InboundHeaders and OutboundCustomHeaders.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="725c6-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="725c6-119">User Action</span></span>  
 <span data-ttu-id="725c6-120">确保标头属性的格式\<标头\>...\</headers\>。</span><span class="sxs-lookup"><span data-stu-id="725c6-120">Ensure that header property is in the format of  \<headers\>…\</headers\>.</span></span>