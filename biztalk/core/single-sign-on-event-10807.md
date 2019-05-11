---
title: 单一登录：Event 10807 | Microsoft Docs
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
ms.openlocfilehash: 774769a952436729e3a32c5aeaf9d3d8eb98243c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267524"
---
# <a name="single-sign-on-event-10807"></a><span data-ttu-id="16f29-102">单一登录：事件 10807</span><span class="sxs-lookup"><span data-stu-id="16f29-102">Single Sign-On: Event 10807</span></span>
## <a name="details"></a><span data-ttu-id="16f29-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="16f29-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="16f29-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="16f29-104">Product Name</span></span>   |                 <span data-ttu-id="16f29-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="16f29-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="16f29-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="16f29-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="16f29-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="16f29-107">Event ID</span></span>     |                           <span data-ttu-id="16f29-108">10807</span><span class="sxs-lookup"><span data-stu-id="16f29-108">10807</span></span>                            |
|  <span data-ttu-id="16f29-109">事件源</span><span class="sxs-lookup"><span data-stu-id="16f29-109">Event Source</span></span>   |                           <span data-ttu-id="16f29-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="16f29-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="16f29-111">组件</span><span class="sxs-lookup"><span data-stu-id="16f29-111">Component</span></span>    |                            <span data-ttu-id="16f29-112">不可用</span><span class="sxs-lookup"><span data-stu-id="16f29-112">N/A</span></span>                             |
|  <span data-ttu-id="16f29-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="16f29-113">Symbolic Name</span></span>  |        <span data-ttu-id="16f29-114">ENTSSO_E_TOO_MANY_UNCONFIRMED_NOTIFICATIONS</span><span class="sxs-lookup"><span data-stu-id="16f29-114">ENTSSO_E_TOO_MANY_UNCONFIRMED_NOTIFICATIONS</span></span>         |
|  <span data-ttu-id="16f29-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="16f29-115">Message Text</span></span>   |            <span data-ttu-id="16f29-116">未确认的通知太多。</span><span class="sxs-lookup"><span data-stu-id="16f29-116">Too many unconfirmed notifications.</span></span>             |
  
## <a name="explanation"></a><span data-ttu-id="16f29-117">解释</span><span class="sxs-lookup"><span data-stu-id="16f29-117">Explanation</span></span>  
 <span data-ttu-id="16f29-118">密码更改通知每次发送、 接收一条确认消息。</span><span class="sxs-lookup"><span data-stu-id="16f29-118">Each time a password change notification is sent, a confirmation message is received.</span></span> <span data-ttu-id="16f29-119">在这种情况下，已超过未确认通知的限制。</span><span class="sxs-lookup"><span data-stu-id="16f29-119">In this case, the limit for notifications without confirmation has been exceeded.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="16f29-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="16f29-120">User Action</span></span>  
 <span data-ttu-id="16f29-121">检查密码同步适配器。</span><span class="sxs-lookup"><span data-stu-id="16f29-121">Check the password sync adapter.</span></span>