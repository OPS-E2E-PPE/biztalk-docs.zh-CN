---
title: 单一登录： 事件 10596 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d70aabcf-aa53-40bf-8937-44f191af1aec
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 051fdf627edc3f560a8d02026207dc2fe5bb3533
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270141"
---
# <a name="single-sign-on-event-10596"></a><span data-ttu-id="34511-102">单一登录： 事件 10596</span><span class="sxs-lookup"><span data-stu-id="34511-102">Single Sign-On: Event 10596</span></span>
## <a name="details"></a><span data-ttu-id="34511-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="34511-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="34511-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="34511-104">Product Name</span></span>|<span data-ttu-id="34511-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="34511-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="34511-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="34511-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="34511-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="34511-107">Event ID</span></span>|<span data-ttu-id="34511-108">10596</span><span class="sxs-lookup"><span data-stu-id="34511-108">10596</span></span>|  
|<span data-ttu-id="34511-109">事件源</span><span class="sxs-lookup"><span data-stu-id="34511-109">Event Source</span></span>|<span data-ttu-id="34511-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="34511-110">ENTSSO</span></span>|  
|<span data-ttu-id="34511-111">组件</span><span class="sxs-lookup"><span data-stu-id="34511-111">Component</span></span>|<span data-ttu-id="34511-112">N/A</span><span class="sxs-lookup"><span data-stu-id="34511-112">N/A</span></span>|  
|<span data-ttu-id="34511-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="34511-113">Symbolic Name</span></span>|<span data-ttu-id="34511-114">SSO_WARN_TICKET_USER_NOT_IN_GROUP</span><span class="sxs-lookup"><span data-stu-id="34511-114">SSO_WARN_TICKET_USER_NOT_IN_GROUP</span></span>|  
|<span data-ttu-id="34511-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="34511-115">Message Text</span></span>|<span data-ttu-id="34511-116">无法兑换票证，因为要使用所颁发票证的用户不是应用程序用户帐户的成员。%r</span><span class="sxs-lookup"><span data-stu-id="34511-116">The ticket cannot be redeemed because the user for whom the ticket was issued is not a member of the Application Users account.%r</span></span><br /><br /> <span data-ttu-id="34511-117">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="34511-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="34511-118">票证的发布日期: %2 %r</span><span class="sxs-lookup"><span data-stu-id="34511-118">Ticket Issued For: %2%r</span></span><br /><br /> <span data-ttu-id="34511-119">Application Users: %3</span><span class="sxs-lookup"><span data-stu-id="34511-119">Application Users: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="34511-120">解释</span><span class="sxs-lookup"><span data-stu-id="34511-120">Explanation</span></span>  
 <span data-ttu-id="34511-121">无法兑换票证，因为要使用所颁发票证的用户不是应用程序用户帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="34511-121">The ticket cannot be redeemed because the user for whom the ticket was issued is not a member of the Application Users account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="34511-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="34511-122">User Action</span></span>  
 <span data-ttu-id="34511-123">将票证重新颁发给属于应用程序用户帐户成员的用户。</span><span class="sxs-lookup"><span data-stu-id="34511-123">Reissue the ticket to a user who is a member of the Application Users account.</span></span>