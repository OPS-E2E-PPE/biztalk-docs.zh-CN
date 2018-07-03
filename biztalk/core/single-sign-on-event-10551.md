---
title: 单一登录： 事件 10551 |Microsoft Docs
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
ms.openlocfilehash: 8a014d9fa9adec99a05eba3f4a0f17047e2e1175
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973486"
---
# <a name="single-sign-on-event-10551"></a><span data-ttu-id="05eec-102">单一登录： 事件 10551</span><span class="sxs-lookup"><span data-stu-id="05eec-102">Single Sign-On: Event 10551</span></span>
## <a name="details"></a><span data-ttu-id="05eec-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="05eec-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="05eec-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="05eec-104">Product Name</span></span>   |                                                                                                   <span data-ttu-id="05eec-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="05eec-105">Enterprise Single Sign-On</span></span>                                                                                                   |
| <span data-ttu-id="05eec-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="05eec-106">Product Version</span></span> |                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                   |
|    <span data-ttu-id="05eec-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="05eec-107">Event ID</span></span>     |                                                                                                             <span data-ttu-id="05eec-108">10551</span><span class="sxs-lookup"><span data-stu-id="05eec-108">10551</span></span>                                                                                                             |
|  <span data-ttu-id="05eec-109">事件源</span><span class="sxs-lookup"><span data-stu-id="05eec-109">Event Source</span></span>   |                                                                                                            <span data-ttu-id="05eec-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="05eec-110">ENTSSO</span></span>                                                                                                             |
|    <span data-ttu-id="05eec-111">组件</span><span class="sxs-lookup"><span data-stu-id="05eec-111">Component</span></span>    |                                                                                                              <span data-ttu-id="05eec-112">N/A</span><span class="sxs-lookup"><span data-stu-id="05eec-112">N/A</span></span>                                                                                                              |
|  <span data-ttu-id="05eec-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="05eec-113">Symbolic Name</span></span>  |                                                                                                     <span data-ttu-id="05eec-114">SSO_WARN_INVALID_USER</span><span class="sxs-lookup"><span data-stu-id="05eec-114">SSO_WARN_INVALID_USER</span></span>                                                                                                     |
|  <span data-ttu-id="05eec-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="05eec-115">Message Text</span></span>   | <span data-ttu-id="05eec-116">无法创建映射，因为指定的用户不是有效 application.%r</span><span class="sxs-lookup"><span data-stu-id="05eec-116">A mapping could not be created because the specified user is not valid for this application.%r</span></span><br /><br /> <span data-ttu-id="05eec-117">域名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="05eec-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="05eec-118">用户名: %2 %r</span><span class="sxs-lookup"><span data-stu-id="05eec-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="05eec-119">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="05eec-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="05eec-120">应用程序用户： %4</span><span class="sxs-lookup"><span data-stu-id="05eec-120">Application Users: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="05eec-121">解释</span><span class="sxs-lookup"><span data-stu-id="05eec-121">Explanation</span></span>  
 <span data-ttu-id="05eec-122">指定的用户无效。</span><span class="sxs-lookup"><span data-stu-id="05eec-122">The specified user is not valid.</span></span> <span data-ttu-id="05eec-123">这可能是拼写错误。</span><span class="sxs-lookup"><span data-stu-id="05eec-123">This could be a typing error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="05eec-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="05eec-124">User Action</span></span>  
 <span data-ttu-id="05eec-125">检查警告信息中列出的用户名，确认它是否正确性，然后再次创建该映射。</span><span class="sxs-lookup"><span data-stu-id="05eec-125">Check the User Name listed in the warning information, confirm that it is correct, and then create the mapping again.</span></span>