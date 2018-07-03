---
title: 单一登录： 事件 10807 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 882c01c6-70db-4986-9f4b-f08335424250
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9e23aefbb950160f29b6145e64bfaa1784dc3f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985406"
---
# <a name="single-sign-on-event-10807"></a><span data-ttu-id="8b876-102">单一登录： 事件 10807</span><span class="sxs-lookup"><span data-stu-id="8b876-102">Single Sign-On: Event 10807</span></span>
## <a name="details"></a><span data-ttu-id="8b876-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8b876-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="8b876-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8b876-104">Product Name</span></span>   |                 <span data-ttu-id="8b876-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="8b876-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="8b876-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="8b876-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="8b876-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8b876-107">Event ID</span></span>     |                           <span data-ttu-id="8b876-108">10807</span><span class="sxs-lookup"><span data-stu-id="8b876-108">10807</span></span>                            |
|  <span data-ttu-id="8b876-109">事件源</span><span class="sxs-lookup"><span data-stu-id="8b876-109">Event Source</span></span>   |                           <span data-ttu-id="8b876-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8b876-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="8b876-111">组件</span><span class="sxs-lookup"><span data-stu-id="8b876-111">Component</span></span>    |                            <span data-ttu-id="8b876-112">N/A</span><span class="sxs-lookup"><span data-stu-id="8b876-112">N/A</span></span>                             |
|  <span data-ttu-id="8b876-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="8b876-113">Symbolic Name</span></span>  |        <span data-ttu-id="8b876-114">ENTSSO_E_TOO_MANY_UNCONFIRMED_NOTIFICATIONS</span><span class="sxs-lookup"><span data-stu-id="8b876-114">ENTSSO_E_TOO_MANY_UNCONFIRMED_NOTIFICATIONS</span></span>         |
|  <span data-ttu-id="8b876-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="8b876-115">Message Text</span></span>   |            <span data-ttu-id="8b876-116">未确认的通知太多。</span><span class="sxs-lookup"><span data-stu-id="8b876-116">Too many unconfirmed notifications.</span></span>             |
  
## <a name="explanation"></a><span data-ttu-id="8b876-117">解释</span><span class="sxs-lookup"><span data-stu-id="8b876-117">Explanation</span></span>  
 <span data-ttu-id="8b876-118">每次发送密码更改通知时都会收到一条确认消息。</span><span class="sxs-lookup"><span data-stu-id="8b876-118">Each time a password change notification is sent, a confirmation message is received.</span></span> <span data-ttu-id="8b876-119">这样就超出了未确认通知的限制。</span><span class="sxs-lookup"><span data-stu-id="8b876-119">In this case, the limit for notifications without confirmation has been exceeded.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8b876-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="8b876-120">User Action</span></span>  
 <span data-ttu-id="8b876-121">检查密码同步适配器。</span><span class="sxs-lookup"><span data-stu-id="8b876-121">Check the password sync adapter.</span></span>