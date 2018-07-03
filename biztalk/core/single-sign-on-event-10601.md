---
title: 单一登录： 事件 10601 |Microsoft Docs
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
ms.openlocfilehash: 4ea1dfbcc36cc83498aa316cedeab8fc46a2f4dd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987734"
---
# <a name="single-sign-on-event-10601"></a><span data-ttu-id="a4c6b-102">单一登录： 事件 10601</span><span class="sxs-lookup"><span data-stu-id="a4c6b-102">Single Sign-On: Event 10601</span></span>
## <a name="details"></a><span data-ttu-id="a4c6b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a4c6b-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a4c6b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a4c6b-104">Product Name</span></span>   |                                                                                                                  <span data-ttu-id="a4c6b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="a4c6b-105">Enterprise Single Sign-On</span></span>                                                                                                                   |
| <span data-ttu-id="a4c6b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="a4c6b-106">Product Version</span></span> |                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                  |
|    <span data-ttu-id="a4c6b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a4c6b-107">Event ID</span></span>     |                                                                                                                            <span data-ttu-id="a4c6b-108">10601</span><span class="sxs-lookup"><span data-stu-id="a4c6b-108">10601</span></span>                                                                                                                             |
|  <span data-ttu-id="a4c6b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="a4c6b-109">Event Source</span></span>   |                                                                                                                            <span data-ttu-id="a4c6b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a4c6b-110">ENTSSO</span></span>                                                                                                                            |
|    <span data-ttu-id="a4c6b-111">组件</span><span class="sxs-lookup"><span data-stu-id="a4c6b-111">Component</span></span>    |                                                                                                                             <span data-ttu-id="a4c6b-112">N/A</span><span class="sxs-lookup"><span data-stu-id="a4c6b-112">N/A</span></span>                                                                                                                              |
|  <span data-ttu-id="a4c6b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="a4c6b-113">Symbolic Name</span></span>  |                                                                                                                    <span data-ttu-id="a4c6b-114">SSO_WARN_INVALID_FLAGS</span><span class="sxs-lookup"><span data-stu-id="a4c6b-114">SSO_WARN_INVALID_FLAGS</span></span>                                                                                                                    |
|  <span data-ttu-id="a4c6b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="a4c6b-115">Message Text</span></span>   | <span data-ttu-id="a4c6b-116">指定的标志无法用于创建此类型的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a4c6b-116">The specified flags are not valid for creating this type of application.</span></span><br /><br /> <span data-ttu-id="a4c6b-117">有关详细信息，请参阅文档。%r</span><span class="sxs-lookup"><span data-stu-id="a4c6b-117">See documentation for details.%r</span></span><br /><br /> <span data-ttu-id="a4c6b-118">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="a4c6b-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="a4c6b-119">指定的标志: %2 %r</span><span class="sxs-lookup"><span data-stu-id="a4c6b-119">Specified Flags: %2%r</span></span><br /><br /> <span data-ttu-id="a4c6b-120">允许的标志: %3 %r</span><span class="sxs-lookup"><span data-stu-id="a4c6b-120">Allowed Flags: %3%r</span></span><br /><br /> <span data-ttu-id="a4c6b-121">不允许的标志： %4</span><span class="sxs-lookup"><span data-stu-id="a4c6b-121">Not Allowed Flags: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="a4c6b-122">解释</span><span class="sxs-lookup"><span data-stu-id="a4c6b-122">Explanation</span></span>  
 <span data-ttu-id="a4c6b-123">指定的标志无法用于创建此类型的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a4c6b-123">The specified flags are not valid for creating this type of application.</span></span> <span data-ttu-id="a4c6b-124">警告中列出了相关的应用程序，以及允许和不允许的标志。</span><span class="sxs-lookup"><span data-stu-id="a4c6b-124">The warning lists the application concerned, as well as the flags that are allowed and those that are not.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a4c6b-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="a4c6b-125">User Action</span></span>  
 <span data-ttu-id="a4c6b-126">遵循警告消息中列出的准则来重新创建应用程序。</span><span class="sxs-lookup"><span data-stu-id="a4c6b-126">Recreate the application following the guidelines outlined in the warning message.</span></span>