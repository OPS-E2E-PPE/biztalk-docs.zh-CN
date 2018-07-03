---
title: 单一登录： 事件 10566 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7bd140b-5503-40f8-bf5d-604fa763989e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4748670e128b5b3a9717e2e430acb976da7bb4d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015086"
---
# <a name="single-sign-on-event-10566"></a><span data-ttu-id="cc5f3-102">单一登录： 事件 10566</span><span class="sxs-lookup"><span data-stu-id="cc5f3-102">Single Sign-On: Event 10566</span></span>
## <a name="details"></a><span data-ttu-id="cc5f3-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="cc5f3-103">Details</span></span>  
  
|                 |                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cc5f3-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="cc5f3-104">Product Name</span></span>   |                                                                     <span data-ttu-id="cc5f3-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="cc5f3-105">Enterprise Single Sign-On</span></span>                                                                      |
| <span data-ttu-id="cc5f3-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="cc5f3-106">Product Version</span></span> |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    <span data-ttu-id="cc5f3-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="cc5f3-107">Event ID</span></span>     |                                                                               <span data-ttu-id="cc5f3-108">10566</span><span class="sxs-lookup"><span data-stu-id="cc5f3-108">10566</span></span>                                                                                |
|  <span data-ttu-id="cc5f3-109">事件源</span><span class="sxs-lookup"><span data-stu-id="cc5f3-109">Event Source</span></span>   |                                                                               <span data-ttu-id="cc5f3-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="cc5f3-110">ENTSSO</span></span>                                                                               |
|    <span data-ttu-id="cc5f3-111">组件</span><span class="sxs-lookup"><span data-stu-id="cc5f3-111">Component</span></span>    |                                                                                <span data-ttu-id="cc5f3-112">N/A</span><span class="sxs-lookup"><span data-stu-id="cc5f3-112">N/A</span></span>                                                                                 |
|  <span data-ttu-id="cc5f3-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="cc5f3-113">Symbolic Name</span></span>  |                                                                  <span data-ttu-id="cc5f3-114">SSO_WARN_CANNOT_UPDATE_APP_FLAGS</span><span class="sxs-lookup"><span data-stu-id="cc5f3-114">SSO_WARN_CANNOT_UPDATE_APP_FLAGS</span></span>                                                                  |
|  <span data-ttu-id="cc5f3-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="cc5f3-115">Message Text</span></span>   | <span data-ttu-id="cc5f3-116">您无法更新此应用程序的某些指定标志。</span><span class="sxs-lookup"><span data-stu-id="cc5f3-116">You cannot update some of the specified flags for this application.</span></span> <span data-ttu-id="cc5f3-117">这些标志将会被忽略。%r</span><span class="sxs-lookup"><span data-stu-id="cc5f3-117">They will be ignored.%r</span></span><br /><br /> <span data-ttu-id="cc5f3-118">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="cc5f3-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="cc5f3-119">指定标志掩码： %2</span><span class="sxs-lookup"><span data-stu-id="cc5f3-119">Specified Flag Mask: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="cc5f3-120">解释</span><span class="sxs-lookup"><span data-stu-id="cc5f3-120">Explanation</span></span>  
 <span data-ttu-id="cc5f3-121">应用程序中的某些标志无法更改。</span><span class="sxs-lookup"><span data-stu-id="cc5f3-121">Certain flags in an application cannot be changed.</span></span> <span data-ttu-id="cc5f3-122">（例如，不允许将应用程序类型从“个人”更改为“组”。）此应用程序的标志在警告文本中列出。</span><span class="sxs-lookup"><span data-stu-id="cc5f3-122">(For example, it is not allowed to change an application type from Individual to Group.) The flags for this application are specified in the warning text.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cc5f3-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="cc5f3-123">User Action</span></span>  
 <span data-ttu-id="cc5f3-124">不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="cc5f3-124">No user action is required.</span></span>