---
title: 单一登录：Event 11037 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b523ff56-112e-4798-97d2-b1b19e130ec7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d64605fbdd4cb470fc6dec060650bd78b581f84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401031"
---
# <a name="single-sign-on-event-11037"></a><span data-ttu-id="fe46e-102">单一登录：事件 11037</span><span class="sxs-lookup"><span data-stu-id="fe46e-102">Single Sign-On: Event 11037</span></span>
## <a name="details"></a><span data-ttu-id="fe46e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="fe46e-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="fe46e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="fe46e-104">Product Name</span></span>   |                                                                                                               <span data-ttu-id="fe46e-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="fe46e-105">Enterprise Single Sign-On</span></span>                                                                                                               |
| <span data-ttu-id="fe46e-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="fe46e-106">Product Version</span></span> |                                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                               |
|    <span data-ttu-id="fe46e-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="fe46e-107">Event ID</span></span>     |                                                                                                                         <span data-ttu-id="fe46e-108">11037</span><span class="sxs-lookup"><span data-stu-id="fe46e-108">11037</span></span>                                                                                                                         |
|  <span data-ttu-id="fe46e-109">事件源</span><span class="sxs-lookup"><span data-stu-id="fe46e-109">Event Source</span></span>   |                                                                                                                        <span data-ttu-id="fe46e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fe46e-110">ENTSSO</span></span>                                                                                                                         |
|    <span data-ttu-id="fe46e-111">组件</span><span class="sxs-lookup"><span data-stu-id="fe46e-111">Component</span></span>    |                                                                                                                          <span data-ttu-id="fe46e-112">不可用</span><span class="sxs-lookup"><span data-stu-id="fe46e-112">N/A</span></span>                                                                                                                          |
|  <span data-ttu-id="fe46e-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="fe46e-113">Symbolic Name</span></span>  |                                                                                                              <span data-ttu-id="fe46e-114">SSO_INFO_PS_MAPPING_INVALID</span><span class="sxs-lookup"><span data-stu-id="fe46e-114">SSO_INFO_PS_MAPPING_INVALID</span></span>                                                                                                              |
|  <span data-ttu-id="fe46e-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="fe46e-115">Message Text</span></span>   | <span data-ttu-id="fe46e-116">外部密码更改。</span><span class="sxs-lookup"><span data-stu-id="fe46e-116">External password change.</span></span> <span data-ttu-id="fe46e-117">密码未更改外部帐户因为映射不再 valid.%r</span><span class="sxs-lookup"><span data-stu-id="fe46e-117">The password was not changed for the external account because the mapping is no longer valid.%r</span></span><br /><br /> <span data-ttu-id="fe46e-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="fe46e-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="fe46e-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="fe46e-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="fe46e-120">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="fe46e-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="fe46e-121">外部帐户： %4</span><span class="sxs-lookup"><span data-stu-id="fe46e-121">External Account: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="fe46e-122">解释</span><span class="sxs-lookup"><span data-stu-id="fe46e-122">Explanation</span></span>  
 <span data-ttu-id="fe46e-123">映射不再是 Application Users 组的一部分。</span><span class="sxs-lookup"><span data-stu-id="fe46e-123">The mapping is no longer a part of the Application Users group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fe46e-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="fe46e-124">User Action</span></span>  
 <span data-ttu-id="fe46e-125">此消息列出了外部帐户和应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="fe46e-125">The message lists the name of the external account and application.</span></span> <span data-ttu-id="fe46e-126">可以使用此信息来找出为什么映射不再有效。</span><span class="sxs-lookup"><span data-stu-id="fe46e-126">You can use this information to find out why the mapping is no longer valid.</span></span>