---
title: 单一登录：Event 10556 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66661a77-e8b0-4972-a3bc-4bb717967699
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30e2f3f8e76f5b2b18aca176dfee1d77c7b1ff1f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398827"
---
# <a name="single-sign-on-event-10556"></a><span data-ttu-id="003b3-102">单一登录：事件 10556</span><span class="sxs-lookup"><span data-stu-id="003b3-102">Single Sign-On: Event 10556</span></span>
## <a name="details"></a><span data-ttu-id="003b3-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="003b3-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                   |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="003b3-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="003b3-104">Product Name</span></span>   |                                                                                                                             <span data-ttu-id="003b3-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="003b3-105">Enterprise Single Sign-On</span></span>                                                                                                                             |
| <span data-ttu-id="003b3-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="003b3-106">Product Version</span></span> |                                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                             |
|    <span data-ttu-id="003b3-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="003b3-107">Event ID</span></span>     |                                                                                                                                       <span data-ttu-id="003b3-108">10556</span><span class="sxs-lookup"><span data-stu-id="003b3-108">10556</span></span>                                                                                                                                       |
|  <span data-ttu-id="003b3-109">事件源</span><span class="sxs-lookup"><span data-stu-id="003b3-109">Event Source</span></span>   |                                                                                                                                      <span data-ttu-id="003b3-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="003b3-110">ENTSSO</span></span>                                                                                                                                       |
|    <span data-ttu-id="003b3-111">组件</span><span class="sxs-lookup"><span data-stu-id="003b3-111">Component</span></span>    |                                                                                                                                        <span data-ttu-id="003b3-112">不可用</span><span class="sxs-lookup"><span data-stu-id="003b3-112">N/A</span></span>                                                                                                                                        |
|  <span data-ttu-id="003b3-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="003b3-113">Symbolic Name</span></span>  |                                                                                                                            <span data-ttu-id="003b3-114">SSO_WARN_INVALID_GROUP_USER</span><span class="sxs-lookup"><span data-stu-id="003b3-114">SSO_WARN_INVALID_GROUP_USER</span></span>                                                                                                                            |
|  <span data-ttu-id="003b3-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="003b3-115">Message Text</span></span>   | <span data-ttu-id="003b3-116">为组应用程序指定的映射不是有效的。</span><span class="sxs-lookup"><span data-stu-id="003b3-116">The mapping specified for a Group application is not valid.</span></span> <span data-ttu-id="003b3-117">映射必须指定一个 application.%r 应用程序用户帐户</span><span class="sxs-lookup"><span data-stu-id="003b3-117">The mapping must specify one of the Application Users accounts for this application.%r</span></span><br /><br /> <span data-ttu-id="003b3-118">域名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="003b3-118">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="003b3-119">用户名: %2 %r</span><span class="sxs-lookup"><span data-stu-id="003b3-119">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="003b3-120">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="003b3-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="003b3-121">应用程序用户： %4</span><span class="sxs-lookup"><span data-stu-id="003b3-121">Application Users: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="003b3-122">解释</span><span class="sxs-lookup"><span data-stu-id="003b3-122">Explanation</span></span>  
 <span data-ttu-id="003b3-123">映射不是有效的。</span><span class="sxs-lookup"><span data-stu-id="003b3-123">The mapping is not valid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="003b3-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="003b3-124">User Action</span></span>  
 <span data-ttu-id="003b3-125">检查映射指定为此应用程序的应用程序用户帐户之一。</span><span class="sxs-lookup"><span data-stu-id="003b3-125">Check that the mapping specifies one of the Application User accounts for this application.</span></span>