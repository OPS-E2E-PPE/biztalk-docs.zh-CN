---
title: "单一登录： 事件 10558 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 84637b67-09df-4c1e-b9f2-85a738ba0d7a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c2ee5c21bdf90e6aedcdbe2ac83e0e51a7f48f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10558"></a><span data-ttu-id="77e76-102">单一登录： 事件 10558</span><span class="sxs-lookup"><span data-stu-id="77e76-102">Single Sign-On: Event 10558</span></span>
## <a name="details"></a><span data-ttu-id="77e76-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="77e76-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="77e76-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="77e76-104">Product Name</span></span>|<span data-ttu-id="77e76-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="77e76-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="77e76-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="77e76-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="77e76-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="77e76-107">Event ID</span></span>|<span data-ttu-id="77e76-108">10558</span><span class="sxs-lookup"><span data-stu-id="77e76-108">10558</span></span>|  
|<span data-ttu-id="77e76-109">事件源</span><span class="sxs-lookup"><span data-stu-id="77e76-109">Event Source</span></span>|<span data-ttu-id="77e76-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="77e76-110">ENTSSO</span></span>|  
|<span data-ttu-id="77e76-111">组件</span><span class="sxs-lookup"><span data-stu-id="77e76-111">Component</span></span>|<span data-ttu-id="77e76-112">N/A</span><span class="sxs-lookup"><span data-stu-id="77e76-112">N/A</span></span>|  
|<span data-ttu-id="77e76-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="77e76-113">Symbolic Name</span></span>|<span data-ttu-id="77e76-114">SSO_WARN_USER_OWN_MAPPINGS</span><span class="sxs-lookup"><span data-stu-id="77e76-114">SSO_WARN_USER_OWN_MAPPINGS</span></span>|  
|<span data-ttu-id="77e76-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="77e76-115">Message Text</span></span>|<span data-ttu-id="77e76-116">应用程序用户只能控制自己的映射。%r</span><span class="sxs-lookup"><span data-stu-id="77e76-116">Application Users are only allowed to control their own mappings.%r</span></span><br /><br /> <span data-ttu-id="77e76-117">域名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="77e76-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="77e76-118">用户名: %2 %r</span><span class="sxs-lookup"><span data-stu-id="77e76-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="77e76-119">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="77e76-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="77e76-120">客户端用户： %4</span><span class="sxs-lookup"><span data-stu-id="77e76-120">Client User: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="77e76-121">解释</span><span class="sxs-lookup"><span data-stu-id="77e76-121">Explanation</span></span>  
 <span data-ttu-id="77e76-122">应用程序用户尝试控制其他用户的映射。</span><span class="sxs-lookup"><span data-stu-id="77e76-122">An attempt was made by an Application User to control the mappings of a different user.</span></span> <span data-ttu-id="77e76-123">不允许这样做。</span><span class="sxs-lookup"><span data-stu-id="77e76-123">This is not allowed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="77e76-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="77e76-124">User Action</span></span>  
 <span data-ttu-id="77e76-125">映射只能由特定映射的应用程序用户来控制。</span><span class="sxs-lookup"><span data-stu-id="77e76-125">Mappings can only be controlled by the Application Users for those specific mappings.</span></span>