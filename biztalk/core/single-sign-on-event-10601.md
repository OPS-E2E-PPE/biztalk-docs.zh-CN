---
title: 单一登录：Event 10601 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2624025e-b7a8-43b9-aa7e-6811a2fc3278
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dedc94aa8cb5881e4ef738f6414f51463684003a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397793"
---
# <a name="single-sign-on-event-10601"></a><span data-ttu-id="e837a-102">单一登录：事件 10601</span><span class="sxs-lookup"><span data-stu-id="e837a-102">Single Sign-On: Event 10601</span></span>
## <a name="details"></a><span data-ttu-id="e837a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e837a-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e837a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e837a-104">Product Name</span></span>   |                                                                                                                  <span data-ttu-id="e837a-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="e837a-105">Enterprise Single Sign-On</span></span>                                                                                                                   |
| <span data-ttu-id="e837a-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="e837a-106">Product Version</span></span> |                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                  |
|    <span data-ttu-id="e837a-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e837a-107">Event ID</span></span>     |                                                                                                                            <span data-ttu-id="e837a-108">10601</span><span class="sxs-lookup"><span data-stu-id="e837a-108">10601</span></span>                                                                                                                             |
|  <span data-ttu-id="e837a-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e837a-109">Event Source</span></span>   |                                                                                                                            <span data-ttu-id="e837a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e837a-110">ENTSSO</span></span>                                                                                                                            |
|    <span data-ttu-id="e837a-111">组件</span><span class="sxs-lookup"><span data-stu-id="e837a-111">Component</span></span>    |                                                                                                                             <span data-ttu-id="e837a-112">不可用</span><span class="sxs-lookup"><span data-stu-id="e837a-112">N/A</span></span>                                                                                                                              |
|  <span data-ttu-id="e837a-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e837a-113">Symbolic Name</span></span>  |                                                                                                                    <span data-ttu-id="e837a-114">SSO_WARN_INVALID_FLAGS</span><span class="sxs-lookup"><span data-stu-id="e837a-114">SSO_WARN_INVALID_FLAGS</span></span>                                                                                                                    |
|  <span data-ttu-id="e837a-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e837a-115">Message Text</span></span>   | <span data-ttu-id="e837a-116">指定的标志不能用于创建此类应用程序。</span><span class="sxs-lookup"><span data-stu-id="e837a-116">The specified flags are not valid for creating this type of application.</span></span><br /><br /> <span data-ttu-id="e837a-117">请参阅 details.%r 文档</span><span class="sxs-lookup"><span data-stu-id="e837a-117">See documentation for details.%r</span></span><br /><br /> <span data-ttu-id="e837a-118">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="e837a-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="e837a-119">指定的标志: %2 %r</span><span class="sxs-lookup"><span data-stu-id="e837a-119">Specified Flags: %2%r</span></span><br /><br /> <span data-ttu-id="e837a-120">允许的标志: %3 %r</span><span class="sxs-lookup"><span data-stu-id="e837a-120">Allowed Flags: %3%r</span></span><br /><br /> <span data-ttu-id="e837a-121">不允许的标志： %4</span><span class="sxs-lookup"><span data-stu-id="e837a-121">Not Allowed Flags: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e837a-122">解释</span><span class="sxs-lookup"><span data-stu-id="e837a-122">Explanation</span></span>  
 <span data-ttu-id="e837a-123">指定的标志不能用于创建此类应用程序。</span><span class="sxs-lookup"><span data-stu-id="e837a-123">The specified flags are not valid for creating this type of application.</span></span> <span data-ttu-id="e837a-124">警告中列出了而言，应用程序，以及允许的标志和无效。</span><span class="sxs-lookup"><span data-stu-id="e837a-124">The warning lists the application concerned, as well as the flags that are allowed and those that are not.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e837a-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="e837a-125">User Action</span></span>  
 <span data-ttu-id="e837a-126">重新创建应用程序的警告消息中所述的指导。</span><span class="sxs-lookup"><span data-stu-id="e837a-126">Recreate the application following the guidelines outlined in the warning message.</span></span>