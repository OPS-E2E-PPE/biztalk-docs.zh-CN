---
title: "单一登录： 事件 10557 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f29bc394-4c56-4ded-93a1-004afb3a054a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afc65dba8760c85ad9eb6552e56e52cc6b7dd3ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10557"></a><span data-ttu-id="197bf-102">单一登录： 事件 10557</span><span class="sxs-lookup"><span data-stu-id="197bf-102">Single Sign-On: Event 10557</span></span>
## <a name="details"></a><span data-ttu-id="197bf-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="197bf-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="197bf-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="197bf-104">Product Name</span></span>|<span data-ttu-id="197bf-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="197bf-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="197bf-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="197bf-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="197bf-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="197bf-107">Event ID</span></span>|<span data-ttu-id="197bf-108">10557</span><span class="sxs-lookup"><span data-stu-id="197bf-108">10557</span></span>|  
|<span data-ttu-id="197bf-109">事件源</span><span class="sxs-lookup"><span data-stu-id="197bf-109">Event Source</span></span>|<span data-ttu-id="197bf-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="197bf-110">ENTSSO</span></span>|  
|<span data-ttu-id="197bf-111">组件</span><span class="sxs-lookup"><span data-stu-id="197bf-111">Component</span></span>|<span data-ttu-id="197bf-112">N/A</span><span class="sxs-lookup"><span data-stu-id="197bf-112">N/A</span></span>|  
|<span data-ttu-id="197bf-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="197bf-113">Symbolic Name</span></span>|<span data-ttu-id="197bf-114">SSO_WARN_USER_NOT_ALLOWED_FOR_GROUPS</span><span class="sxs-lookup"><span data-stu-id="197bf-114">SSO_WARN_USER_NOT_ALLOWED_FOR_GROUPS</span></span>|  
|<span data-ttu-id="197bf-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="197bf-115">Message Text</span></span>|<span data-ttu-id="197bf-116">不允许应用程序用户控制组应用程序的映射。%r</span><span class="sxs-lookup"><span data-stu-id="197bf-116">Application Users are not allowed to control mappings for Group applications.%r</span></span><br /><br /> <span data-ttu-id="197bf-117">域名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="197bf-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="197bf-118">用户名: %2 %r</span><span class="sxs-lookup"><span data-stu-id="197bf-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="197bf-119">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="197bf-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="197bf-120">客户端用户： %4</span><span class="sxs-lookup"><span data-stu-id="197bf-120">Client User: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="197bf-121">解释</span><span class="sxs-lookup"><span data-stu-id="197bf-121">Explanation</span></span>  
 <span data-ttu-id="197bf-122">应用程序用户没有足够的权限来创建或控制组应用程序的映射。</span><span class="sxs-lookup"><span data-stu-id="197bf-122">An Application User does not have sufficient privileges to create or control mappings for Group applications.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="197bf-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="197bf-123">User Action</span></span>  
 <span data-ttu-id="197bf-124">此活动必须由应用程序管理员执行。</span><span class="sxs-lookup"><span data-stu-id="197bf-124">This activity must be performed by an Application Administrator.</span></span>