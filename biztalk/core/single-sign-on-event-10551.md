---
title: 单一登录： 事件 10551 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33434989-08d8-4d13-a3cc-4c5543add69c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30c4b315744749d232c30f4cc28c4d297a0f5243
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270741"
---
# <a name="single-sign-on-event-10551"></a><span data-ttu-id="ef7ea-102">单一登录： 事件 10551</span><span class="sxs-lookup"><span data-stu-id="ef7ea-102">Single Sign-On: Event 10551</span></span>
## <a name="details"></a><span data-ttu-id="ef7ea-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ef7ea-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ef7ea-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ef7ea-104">Product Name</span></span>|<span data-ttu-id="ef7ea-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="ef7ea-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="ef7ea-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="ef7ea-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="ef7ea-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ef7ea-107">Event ID</span></span>|<span data-ttu-id="ef7ea-108">10551</span><span class="sxs-lookup"><span data-stu-id="ef7ea-108">10551</span></span>|  
|<span data-ttu-id="ef7ea-109">事件源</span><span class="sxs-lookup"><span data-stu-id="ef7ea-109">Event Source</span></span>|<span data-ttu-id="ef7ea-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ef7ea-110">ENTSSO</span></span>|  
|<span data-ttu-id="ef7ea-111">组件</span><span class="sxs-lookup"><span data-stu-id="ef7ea-111">Component</span></span>|<span data-ttu-id="ef7ea-112">N/A</span><span class="sxs-lookup"><span data-stu-id="ef7ea-112">N/A</span></span>|  
|<span data-ttu-id="ef7ea-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="ef7ea-113">Symbolic Name</span></span>|<span data-ttu-id="ef7ea-114">SSO_WARN_INVALID_USER</span><span class="sxs-lookup"><span data-stu-id="ef7ea-114">SSO_WARN_INVALID_USER</span></span>|  
|<span data-ttu-id="ef7ea-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="ef7ea-115">Message Text</span></span>|<span data-ttu-id="ef7ea-116">无法创建映射，因为指定的用户不是有效 application.%r</span><span class="sxs-lookup"><span data-stu-id="ef7ea-116">A mapping could not be created because the specified user is not valid for this application.%r</span></span><br /><br /> <span data-ttu-id="ef7ea-117">域名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ef7ea-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="ef7ea-118">用户名: %2 %r</span><span class="sxs-lookup"><span data-stu-id="ef7ea-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="ef7ea-119">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="ef7ea-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="ef7ea-120">Application Users: %4</span><span class="sxs-lookup"><span data-stu-id="ef7ea-120">Application Users: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ef7ea-121">解释</span><span class="sxs-lookup"><span data-stu-id="ef7ea-121">Explanation</span></span>  
 <span data-ttu-id="ef7ea-122">指定的用户无效。</span><span class="sxs-lookup"><span data-stu-id="ef7ea-122">The specified user is not valid.</span></span> <span data-ttu-id="ef7ea-123">这可能是拼写错误。</span><span class="sxs-lookup"><span data-stu-id="ef7ea-123">This could be a typing error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ef7ea-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="ef7ea-124">User Action</span></span>  
 <span data-ttu-id="ef7ea-125">检查警告信息中列出的用户名，确认它是否正确性，然后再次创建该映射。</span><span class="sxs-lookup"><span data-stu-id="ef7ea-125">Check the User Name listed in the warning information, confirm that it is correct, and then create the mapping again.</span></span>