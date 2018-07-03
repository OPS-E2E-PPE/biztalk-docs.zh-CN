---
title: 单一登录： 事件 11037 |Microsoft Docs
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
ms.openlocfilehash: ceec837a53d4cad3c236373a907497795efbd12a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998894"
---
# <a name="single-sign-on-event-11037"></a><span data-ttu-id="8e8a7-102">单一登录： 事件 11037</span><span class="sxs-lookup"><span data-stu-id="8e8a7-102">Single Sign-On: Event 11037</span></span>
## <a name="details"></a><span data-ttu-id="8e8a7-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8e8a7-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8e8a7-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8e8a7-104">Product Name</span></span>   |                                                                                                               <span data-ttu-id="8e8a7-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="8e8a7-105">Enterprise Single Sign-On</span></span>                                                                                                               |
| <span data-ttu-id="8e8a7-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="8e8a7-106">Product Version</span></span> |                                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                               |
|    <span data-ttu-id="8e8a7-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8e8a7-107">Event ID</span></span>     |                                                                                                                         <span data-ttu-id="8e8a7-108">11037</span><span class="sxs-lookup"><span data-stu-id="8e8a7-108">11037</span></span>                                                                                                                         |
|  <span data-ttu-id="8e8a7-109">事件源</span><span class="sxs-lookup"><span data-stu-id="8e8a7-109">Event Source</span></span>   |                                                                                                                        <span data-ttu-id="8e8a7-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8e8a7-110">ENTSSO</span></span>                                                                                                                         |
|    <span data-ttu-id="8e8a7-111">组件</span><span class="sxs-lookup"><span data-stu-id="8e8a7-111">Component</span></span>    |                                                                                                                          <span data-ttu-id="8e8a7-112">N/A</span><span class="sxs-lookup"><span data-stu-id="8e8a7-112">N/A</span></span>                                                                                                                          |
|  <span data-ttu-id="8e8a7-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="8e8a7-113">Symbolic Name</span></span>  |                                                                                                              <span data-ttu-id="8e8a7-114">SSO_INFO_PS_MAPPING_INVALID</span><span class="sxs-lookup"><span data-stu-id="8e8a7-114">SSO_INFO_PS_MAPPING_INVALID</span></span>                                                                                                              |
|  <span data-ttu-id="8e8a7-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="8e8a7-115">Message Text</span></span>   | <span data-ttu-id="8e8a7-116">外部密码更改。</span><span class="sxs-lookup"><span data-stu-id="8e8a7-116">External password change.</span></span> <span data-ttu-id="8e8a7-117">未更改外部帐户的密码，因为映射不再有效。%r</span><span class="sxs-lookup"><span data-stu-id="8e8a7-117">The password was not changed for the external account because the mapping is no longer valid.%r</span></span><br /><br /> <span data-ttu-id="8e8a7-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="8e8a7-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="8e8a7-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="8e8a7-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="8e8a7-120">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="8e8a7-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="8e8a7-121">外部帐户： %4</span><span class="sxs-lookup"><span data-stu-id="8e8a7-121">External Account: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="8e8a7-122">解释</span><span class="sxs-lookup"><span data-stu-id="8e8a7-122">Explanation</span></span>  
 <span data-ttu-id="8e8a7-123">映射不再是“应用程序用户”组的一部分。</span><span class="sxs-lookup"><span data-stu-id="8e8a7-123">The mapping is no longer a part of the Application Users group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8e8a7-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="8e8a7-124">User Action</span></span>  
 <span data-ttu-id="8e8a7-125">此消息列出了外部帐户和应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="8e8a7-125">The message lists the name of the external account and application.</span></span> <span data-ttu-id="8e8a7-126">您可以使用这一信息来查明映射不再有效的原因。</span><span class="sxs-lookup"><span data-stu-id="8e8a7-126">You can use this information to find out why the mapping is no longer valid.</span></span>