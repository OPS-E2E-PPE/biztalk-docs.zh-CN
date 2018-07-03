---
title: 单一登录： 事件 10556 |Microsoft Docs
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
ms.openlocfilehash: 79300dc2ff97fe3f410d0e8b06cdfbebd4782a48
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011758"
---
# <a name="single-sign-on-event-10556"></a><span data-ttu-id="0953f-102">单一登录： 事件 10556</span><span class="sxs-lookup"><span data-stu-id="0953f-102">Single Sign-On: Event 10556</span></span>
## <a name="details"></a><span data-ttu-id="0953f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0953f-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                   |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0953f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0953f-104">Product Name</span></span>   |                                                                                                                             <span data-ttu-id="0953f-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="0953f-105">Enterprise Single Sign-On</span></span>                                                                                                                             |
| <span data-ttu-id="0953f-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="0953f-106">Product Version</span></span> |                                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                             |
|    <span data-ttu-id="0953f-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0953f-107">Event ID</span></span>     |                                                                                                                                       <span data-ttu-id="0953f-108">10556</span><span class="sxs-lookup"><span data-stu-id="0953f-108">10556</span></span>                                                                                                                                       |
|  <span data-ttu-id="0953f-109">事件源</span><span class="sxs-lookup"><span data-stu-id="0953f-109">Event Source</span></span>   |                                                                                                                                      <span data-ttu-id="0953f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0953f-110">ENTSSO</span></span>                                                                                                                                       |
|    <span data-ttu-id="0953f-111">组件</span><span class="sxs-lookup"><span data-stu-id="0953f-111">Component</span></span>    |                                                                                                                                        <span data-ttu-id="0953f-112">N/A</span><span class="sxs-lookup"><span data-stu-id="0953f-112">N/A</span></span>                                                                                                                                        |
|  <span data-ttu-id="0953f-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="0953f-113">Symbolic Name</span></span>  |                                                                                                                            <span data-ttu-id="0953f-114">SSO_WARN_INVALID_GROUP_USER</span><span class="sxs-lookup"><span data-stu-id="0953f-114">SSO_WARN_INVALID_GROUP_USER</span></span>                                                                                                                            |
|  <span data-ttu-id="0953f-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="0953f-115">Message Text</span></span>   | <span data-ttu-id="0953f-116">组应用程序指定的映射无效。</span><span class="sxs-lookup"><span data-stu-id="0953f-116">The mapping specified for a Group application is not valid.</span></span> <span data-ttu-id="0953f-117">映射必须为此应用程序指定应用程序用户帐户之一。%r</span><span class="sxs-lookup"><span data-stu-id="0953f-117">The mapping must specify one of the Application Users accounts for this application.%r</span></span><br /><br /> <span data-ttu-id="0953f-118">域名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="0953f-118">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="0953f-119">用户名: %2 %r</span><span class="sxs-lookup"><span data-stu-id="0953f-119">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="0953f-120">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="0953f-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="0953f-121">应用程序用户： %4</span><span class="sxs-lookup"><span data-stu-id="0953f-121">Application Users: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="0953f-122">解释</span><span class="sxs-lookup"><span data-stu-id="0953f-122">Explanation</span></span>  
 <span data-ttu-id="0953f-123">映射无效。</span><span class="sxs-lookup"><span data-stu-id="0953f-123">The mapping is not valid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0953f-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="0953f-124">User Action</span></span>  
 <span data-ttu-id="0953f-125">检查映射是否为此应用程序指定应用程序用户帐户之一。</span><span class="sxs-lookup"><span data-stu-id="0953f-125">Check that the mapping specifies one of the Application User accounts for this application.</span></span>