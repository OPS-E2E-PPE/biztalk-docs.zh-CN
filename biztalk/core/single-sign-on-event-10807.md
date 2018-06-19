---
title: 单一登录： 事件 10807 |Microsoft 文档
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
ms.openlocfilehash: 4e269b22bc8ea2fec013123d515ac04bd3f60d46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277693"
---
# <a name="single-sign-on-event-10807"></a><span data-ttu-id="881db-102">单一登录： 事件 10807</span><span class="sxs-lookup"><span data-stu-id="881db-102">Single Sign-On: Event 10807</span></span>
## <a name="details"></a><span data-ttu-id="881db-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="881db-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="881db-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="881db-104">Product Name</span></span>|<span data-ttu-id="881db-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="881db-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="881db-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="881db-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="881db-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="881db-107">Event ID</span></span>|<span data-ttu-id="881db-108">10807</span><span class="sxs-lookup"><span data-stu-id="881db-108">10807</span></span>|  
|<span data-ttu-id="881db-109">事件源</span><span class="sxs-lookup"><span data-stu-id="881db-109">Event Source</span></span>|<span data-ttu-id="881db-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="881db-110">ENTSSO</span></span>|  
|<span data-ttu-id="881db-111">组件</span><span class="sxs-lookup"><span data-stu-id="881db-111">Component</span></span>|<span data-ttu-id="881db-112">N/A</span><span class="sxs-lookup"><span data-stu-id="881db-112">N/A</span></span>|  
|<span data-ttu-id="881db-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="881db-113">Symbolic Name</span></span>|<span data-ttu-id="881db-114">ENTSSO_E_TOO_MANY_UNCONFIRMED_NOTIFICATIONS</span><span class="sxs-lookup"><span data-stu-id="881db-114">ENTSSO_E_TOO_MANY_UNCONFIRMED_NOTIFICATIONS</span></span>|  
|<span data-ttu-id="881db-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="881db-115">Message Text</span></span>|<span data-ttu-id="881db-116">未确认的通知太多。</span><span class="sxs-lookup"><span data-stu-id="881db-116">Too many unconfirmed notifications.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="881db-117">解释</span><span class="sxs-lookup"><span data-stu-id="881db-117">Explanation</span></span>  
 <span data-ttu-id="881db-118">每次发送密码更改通知时都会收到一条确认消息。</span><span class="sxs-lookup"><span data-stu-id="881db-118">Each time a password change notification is sent, a confirmation message is received.</span></span> <span data-ttu-id="881db-119">这样就超出了未确认通知的限制。</span><span class="sxs-lookup"><span data-stu-id="881db-119">In this case, the limit for notifications without confirmation has been exceeded.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="881db-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="881db-120">User Action</span></span>  
 <span data-ttu-id="881db-121">检查密码同步适配器。</span><span class="sxs-lookup"><span data-stu-id="881db-121">Check the password sync adapter.</span></span>