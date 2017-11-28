---
title: "单一登录： 事件 10817 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1668b81-e7f4-46d2-aebe-47007f70372b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c94f677ccd14dd821886210f9e4c55efd754a404
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10817"></a><span data-ttu-id="709fe-102">单一登录： 事件 10817</span><span class="sxs-lookup"><span data-stu-id="709fe-102">Single Sign-On: Event 10817</span></span>
## <a name="details"></a><span data-ttu-id="709fe-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="709fe-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="709fe-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="709fe-104">Product Name</span></span>|<span data-ttu-id="709fe-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="709fe-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="709fe-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="709fe-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="709fe-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="709fe-107">Event ID</span></span>|<span data-ttu-id="709fe-108">10817</span><span class="sxs-lookup"><span data-stu-id="709fe-108">10817</span></span>|  
|<span data-ttu-id="709fe-109">事件源</span><span class="sxs-lookup"><span data-stu-id="709fe-109">Event Source</span></span>|<span data-ttu-id="709fe-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="709fe-110">ENTSSO</span></span>|  
|<span data-ttu-id="709fe-111">组件</span><span class="sxs-lookup"><span data-stu-id="709fe-111">Component</span></span>|<span data-ttu-id="709fe-112">N/A</span><span class="sxs-lookup"><span data-stu-id="709fe-112">N/A</span></span>|  
|<span data-ttu-id="709fe-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="709fe-113">Symbolic Name</span></span>|<span data-ttu-id="709fe-114">ENTSSO_E_NOTIFICATION_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="709fe-114">ENTSSO_E_NOTIFICATION_NOT_FOUND</span></span>|  
|<span data-ttu-id="709fe-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="709fe-115">Message Text</span></span>|<span data-ttu-id="709fe-116">找不到指定的通知。</span><span class="sxs-lookup"><span data-stu-id="709fe-116">The specified notification was not found.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="709fe-117">解释</span><span class="sxs-lookup"><span data-stu-id="709fe-117">Explanation</span></span>  
 <span data-ttu-id="709fe-118">无法找到密码更改所指定的通知 GUID。</span><span class="sxs-lookup"><span data-stu-id="709fe-118">The password change specified a notification GUID which cannot be found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="709fe-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="709fe-119">User Action</span></span>  
 <span data-ttu-id="709fe-120">查看此密码同步适配器的配置来确定与通知相应的 GUID。</span><span class="sxs-lookup"><span data-stu-id="709fe-120">See the configuration for this password sync adapter to determine the proper GUID of the notification.</span></span>