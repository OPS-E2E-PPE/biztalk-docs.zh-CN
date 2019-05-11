---
title: 单一登录：事件 10551 |Microsoft Docs
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
ms.openlocfilehash: 87e1965abac7bf861cfc90cfb2981b5ac30bd5b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250254"
---
# <a name="single-sign-on-event-10551"></a><span data-ttu-id="94975-102">单一登录：事件 10551</span><span class="sxs-lookup"><span data-stu-id="94975-102">Single Sign-On: Event 10551</span></span>
## <a name="details"></a><span data-ttu-id="94975-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="94975-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="94975-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="94975-104">Product Name</span></span>   |                                                                                                   <span data-ttu-id="94975-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="94975-105">Enterprise Single Sign-On</span></span>                                                                                                   |
| <span data-ttu-id="94975-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="94975-106">Product Version</span></span> |                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                   |
|    <span data-ttu-id="94975-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="94975-107">Event ID</span></span>     |                                                                                                             <span data-ttu-id="94975-108">10551</span><span class="sxs-lookup"><span data-stu-id="94975-108">10551</span></span>                                                                                                             |
|  <span data-ttu-id="94975-109">事件源</span><span class="sxs-lookup"><span data-stu-id="94975-109">Event Source</span></span>   |                                                                                                            <span data-ttu-id="94975-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="94975-110">ENTSSO</span></span>                                                                                                             |
|    <span data-ttu-id="94975-111">组件</span><span class="sxs-lookup"><span data-stu-id="94975-111">Component</span></span>    |                                                                                                              <span data-ttu-id="94975-112">不可用</span><span class="sxs-lookup"><span data-stu-id="94975-112">N/A</span></span>                                                                                                              |
|  <span data-ttu-id="94975-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="94975-113">Symbolic Name</span></span>  |                                                                                                     <span data-ttu-id="94975-114">SSO_WARN_INVALID_USER</span><span class="sxs-lookup"><span data-stu-id="94975-114">SSO_WARN_INVALID_USER</span></span>                                                                                                     |
|  <span data-ttu-id="94975-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="94975-115">Message Text</span></span>   | <span data-ttu-id="94975-116">无法创建映射，因为指定的用户不是有效 application.%r</span><span class="sxs-lookup"><span data-stu-id="94975-116">A mapping could not be created because the specified user is not valid for this application.%r</span></span><br /><br /> <span data-ttu-id="94975-117">域名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="94975-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="94975-118">用户名: %2 %r</span><span class="sxs-lookup"><span data-stu-id="94975-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="94975-119">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="94975-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="94975-120">应用程序用户： %4</span><span class="sxs-lookup"><span data-stu-id="94975-120">Application Users: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="94975-121">解释</span><span class="sxs-lookup"><span data-stu-id="94975-121">Explanation</span></span>  
 <span data-ttu-id="94975-122">指定的用户不是有效的。</span><span class="sxs-lookup"><span data-stu-id="94975-122">The specified user is not valid.</span></span> <span data-ttu-id="94975-123">这可能是类型化错误。</span><span class="sxs-lookup"><span data-stu-id="94975-123">This could be a typing error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="94975-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="94975-124">User Action</span></span>  
 <span data-ttu-id="94975-125">检查用户名称列出在警告信息中，确认它是否正确，然后创建该映射再次。</span><span class="sxs-lookup"><span data-stu-id="94975-125">Check the User Name listed in the warning information, confirm that it is correct, and then create the mapping again.</span></span>