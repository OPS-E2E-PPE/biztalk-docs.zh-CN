---
title: 单一登录：事件 11045 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7212f42-355d-446f-bd07-5fb4e799b607
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d03e5e6ca3cd651c001c2f1df386eb07d32d3c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400952"
---
# <a name="single-sign-on-event-11045"></a><span data-ttu-id="e260d-102">单一登录：事件 11045</span><span class="sxs-lookup"><span data-stu-id="e260d-102">Single Sign-On: Event 11045</span></span>
## <a name="details"></a><span data-ttu-id="e260d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e260d-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e260d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e260d-104">Product Name</span></span>   |                                                                                       <span data-ttu-id="e260d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="e260d-105">Enterprise Single Sign-On</span></span>                                                                                       |
| <span data-ttu-id="e260d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="e260d-106">Product Version</span></span> |                                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                       |
|    <span data-ttu-id="e260d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e260d-107">Event ID</span></span>     |                                                                                                 <span data-ttu-id="e260d-108">11045</span><span class="sxs-lookup"><span data-stu-id="e260d-108">11045</span></span>                                                                                                 |
|  <span data-ttu-id="e260d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e260d-109">Event Source</span></span>   |                                                                                                <span data-ttu-id="e260d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e260d-110">ENTSSO</span></span>                                                                                                 |
|    <span data-ttu-id="e260d-111">组件</span><span class="sxs-lookup"><span data-stu-id="e260d-111">Component</span></span>    |                                                                                                  <span data-ttu-id="e260d-112">不可用</span><span class="sxs-lookup"><span data-stu-id="e260d-112">N/A</span></span>                                                                                                  |
|  <span data-ttu-id="e260d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e260d-113">Symbolic Name</span></span>  |                                                                                   <span data-ttu-id="e260d-114">SSO_WARN_EXISTING_MAPPING_WINDOWS</span><span class="sxs-lookup"><span data-stu-id="e260d-114">SSO_WARN_EXISTING_MAPPING_WINDOWS</span></span>                                                                                   |
|  <span data-ttu-id="e260d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e260d-115">Message Text</span></span>   | <span data-ttu-id="e260d-116">无法创建映射，因为映射已存在指定的 Windows account.%r</span><span class="sxs-lookup"><span data-stu-id="e260d-116">A mapping could not be created because a mapping already exists for the specified Windows account.%r</span></span><br /><br /> <span data-ttu-id="e260d-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="e260d-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="e260d-118">应用程序名称: %2 %r</span><span class="sxs-lookup"><span data-stu-id="e260d-118">Application Name: %2%r</span></span><br /><br /> <span data-ttu-id="e260d-119">Windows 帐户： %3</span><span class="sxs-lookup"><span data-stu-id="e260d-119">Windows Account: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e260d-120">解释</span><span class="sxs-lookup"><span data-stu-id="e260d-120">Explanation</span></span>  
 <span data-ttu-id="e260d-121">映射已存在所指定的 Windows 帐户，并且不允许重复。</span><span class="sxs-lookup"><span data-stu-id="e260d-121">A mapping already exists for the specified Windows account, and duplicates are not allowed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e260d-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="e260d-122">User Action</span></span>  
 <span data-ttu-id="e260d-123">不不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="e260d-123">No user action is necessary.</span></span>