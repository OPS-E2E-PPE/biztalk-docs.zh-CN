---
title: 单一登录： 事件 10817 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1668b81-e7f4-46d2-aebe-47007f70372b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e42873f0b56c43a7c997a2476ba2b15148d4639
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979190"
---
# <a name="single-sign-on-event-10817"></a><span data-ttu-id="a727d-102">单一登录： 事件 10817</span><span class="sxs-lookup"><span data-stu-id="a727d-102">Single Sign-On: Event 10817</span></span>
## <a name="details"></a><span data-ttu-id="a727d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a727d-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="a727d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a727d-104">Product Name</span></span>   |                 <span data-ttu-id="a727d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="a727d-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="a727d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="a727d-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="a727d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a727d-107">Event ID</span></span>     |                           <span data-ttu-id="a727d-108">10817</span><span class="sxs-lookup"><span data-stu-id="a727d-108">10817</span></span>                            |
|  <span data-ttu-id="a727d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="a727d-109">Event Source</span></span>   |                           <span data-ttu-id="a727d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a727d-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="a727d-111">组件</span><span class="sxs-lookup"><span data-stu-id="a727d-111">Component</span></span>    |                            <span data-ttu-id="a727d-112">N/A</span><span class="sxs-lookup"><span data-stu-id="a727d-112">N/A</span></span>                             |
|  <span data-ttu-id="a727d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="a727d-113">Symbolic Name</span></span>  |              <span data-ttu-id="a727d-114">ENTSSO_E_NOTIFICATION_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="a727d-114">ENTSSO_E_NOTIFICATION_NOT_FOUND</span></span>               |
|  <span data-ttu-id="a727d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="a727d-115">Message Text</span></span>   |         <span data-ttu-id="a727d-116">找不到指定的通知。</span><span class="sxs-lookup"><span data-stu-id="a727d-116">The specified notification was not found.</span></span>          |
  
## <a name="explanation"></a><span data-ttu-id="a727d-117">解释</span><span class="sxs-lookup"><span data-stu-id="a727d-117">Explanation</span></span>  
 <span data-ttu-id="a727d-118">无法找到密码更改所指定的通知 GUID。</span><span class="sxs-lookup"><span data-stu-id="a727d-118">The password change specified a notification GUID which cannot be found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a727d-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="a727d-119">User Action</span></span>  
 <span data-ttu-id="a727d-120">查看此密码同步适配器的配置来确定与通知相应的 GUID。</span><span class="sxs-lookup"><span data-stu-id="a727d-120">See the configuration for this password sync adapter to determine the proper GUID of the notification.</span></span>