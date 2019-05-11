---
title: 单一登录：Event 10804 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4d98bef-fdc3-4627-bb5b-663fa502b965
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a93cce2d1ad17248c1ad007f07c0a885b1a8fa6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399515"
---
# <a name="single-sign-on-event-10804"></a><span data-ttu-id="cdfb6-102">单一登录：事件 10804</span><span class="sxs-lookup"><span data-stu-id="cdfb6-102">Single Sign-On: Event 10804</span></span>
## <a name="details"></a><span data-ttu-id="cdfb6-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="cdfb6-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="cdfb6-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="cdfb6-104">Product Name</span></span>   |                 <span data-ttu-id="cdfb6-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="cdfb6-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="cdfb6-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="cdfb6-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="cdfb6-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="cdfb6-107">Event ID</span></span>     |                           <span data-ttu-id="cdfb6-108">10804</span><span class="sxs-lookup"><span data-stu-id="cdfb6-108">10804</span></span>                            |
|  <span data-ttu-id="cdfb6-109">事件源</span><span class="sxs-lookup"><span data-stu-id="cdfb6-109">Event Source</span></span>   |                           <span data-ttu-id="cdfb6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="cdfb6-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="cdfb6-111">组件</span><span class="sxs-lookup"><span data-stu-id="cdfb6-111">Component</span></span>    |                            <span data-ttu-id="cdfb6-112">不可用</span><span class="sxs-lookup"><span data-stu-id="cdfb6-112">N/A</span></span>                             |
|  <span data-ttu-id="cdfb6-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="cdfb6-113">Symbolic Name</span></span>  |                <span data-ttu-id="cdfb6-114">ENTSSO_E_INCORRECT_COMPUTER</span><span class="sxs-lookup"><span data-stu-id="cdfb6-114">ENTSSO_E_INCORRECT_COMPUTER</span></span>                 |
|  <span data-ttu-id="cdfb6-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="cdfb6-115">Message Text</span></span>   |     <span data-ttu-id="cdfb6-116">此适配器未配置此计算机。</span><span class="sxs-lookup"><span data-stu-id="cdfb6-116">This adapter is not configured for this computer.</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="cdfb6-117">解释</span><span class="sxs-lookup"><span data-stu-id="cdfb6-117">Explanation</span></span>  
 <span data-ttu-id="cdfb6-118">每个适配器配置为在由其长名称标识的特定计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="cdfb6-118">Each adapter is configured to run on a specific computer, which is identified by its long name.</span></span> <span data-ttu-id="cdfb6-119">名称不正确，或者想要在另一台计算机上运行的适配器。</span><span class="sxs-lookup"><span data-stu-id="cdfb6-119">Either the name is incorrect, or you are trying to run the adapter on a different computer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cdfb6-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="cdfb6-120">User Action</span></span>  
 <span data-ttu-id="cdfb6-121">请参阅此适配器，以确定相应的计算机的正确名称的配置。</span><span class="sxs-lookup"><span data-stu-id="cdfb6-121">See the configuration for this adapter to determine the proper name of the appropriate computer.</span></span>