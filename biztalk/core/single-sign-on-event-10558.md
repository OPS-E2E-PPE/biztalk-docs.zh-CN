---
title: 单一登录： 事件 10558 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84637b67-09df-4c1e-b9f2-85a738ba0d7a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d9a281d6a6ca20a274db4b3ffe5b2697ff812c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974862"
---
# <a name="single-sign-on-event-10558"></a><span data-ttu-id="20f87-102">单一登录： 事件 10558</span><span class="sxs-lookup"><span data-stu-id="20f87-102">Single Sign-On: Event 10558</span></span>
## <a name="details"></a><span data-ttu-id="20f87-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="20f87-103">Details</span></span>  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="20f87-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="20f87-104">Product Name</span></span>   |                                                                                  <span data-ttu-id="20f87-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="20f87-105">Enterprise Single Sign-On</span></span>                                                                                   |
| <span data-ttu-id="20f87-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="20f87-106">Product Version</span></span> |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    <span data-ttu-id="20f87-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="20f87-107">Event ID</span></span>     |                                                                                            <span data-ttu-id="20f87-108">10558</span><span class="sxs-lookup"><span data-stu-id="20f87-108">10558</span></span>                                                                                             |
|  <span data-ttu-id="20f87-109">事件源</span><span class="sxs-lookup"><span data-stu-id="20f87-109">Event Source</span></span>   |                                                                                            <span data-ttu-id="20f87-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="20f87-110">ENTSSO</span></span>                                                                                            |
|    <span data-ttu-id="20f87-111">组件</span><span class="sxs-lookup"><span data-stu-id="20f87-111">Component</span></span>    |                                                                                             <span data-ttu-id="20f87-112">N/A</span><span class="sxs-lookup"><span data-stu-id="20f87-112">N/A</span></span>                                                                                              |
|  <span data-ttu-id="20f87-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="20f87-113">Symbolic Name</span></span>  |                                                                                  <span data-ttu-id="20f87-114">SSO_WARN_USER_OWN_MAPPINGS</span><span class="sxs-lookup"><span data-stu-id="20f87-114">SSO_WARN_USER_OWN_MAPPINGS</span></span>                                                                                  |
|  <span data-ttu-id="20f87-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="20f87-115">Message Text</span></span>   | <span data-ttu-id="20f87-116">应用程序用户只能控制自己的映射。%r</span><span class="sxs-lookup"><span data-stu-id="20f87-116">Application Users are only allowed to control their own mappings.%r</span></span><br /><br /> <span data-ttu-id="20f87-117">域名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="20f87-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="20f87-118">用户名: %2 %r</span><span class="sxs-lookup"><span data-stu-id="20f87-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="20f87-119">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="20f87-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="20f87-120">客户端用户： %4</span><span class="sxs-lookup"><span data-stu-id="20f87-120">Client User: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="20f87-121">解释</span><span class="sxs-lookup"><span data-stu-id="20f87-121">Explanation</span></span>  
 <span data-ttu-id="20f87-122">应用程序用户尝试控制其他用户的映射。</span><span class="sxs-lookup"><span data-stu-id="20f87-122">An attempt was made by an Application User to control the mappings of a different user.</span></span> <span data-ttu-id="20f87-123">不允许这样做。</span><span class="sxs-lookup"><span data-stu-id="20f87-123">This is not allowed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="20f87-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="20f87-124">User Action</span></span>  
 <span data-ttu-id="20f87-125">映射只能由特定映射的应用程序用户来控制。</span><span class="sxs-lookup"><span data-stu-id="20f87-125">Mappings can only be controlled by the Application Users for those specific mappings.</span></span>