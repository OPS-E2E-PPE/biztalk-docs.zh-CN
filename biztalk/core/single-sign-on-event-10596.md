---
title: 单一登录：Event 10596 | Microsoft Docs
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
ms.openlocfilehash: f093968363a0c67d48e8e50e4bd0d44c45d9491a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397839"
---
# <a name="single-sign-on-event-10596"></a><span data-ttu-id="5e279-102">单一登录：事件 10596</span><span class="sxs-lookup"><span data-stu-id="5e279-102">Single Sign-On: Event 10596</span></span>
## <a name="details"></a><span data-ttu-id="5e279-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5e279-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="5e279-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5e279-104">Product Name</span></span>   |                                                                                                         <span data-ttu-id="5e279-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="5e279-105">Enterprise Single Sign-On</span></span>                                                                                                          |
| <span data-ttu-id="5e279-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="5e279-106">Product Version</span></span> |                                                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                         |
|    <span data-ttu-id="5e279-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5e279-107">Event ID</span></span>     |                                                                                                                   <span data-ttu-id="5e279-108">10596</span><span class="sxs-lookup"><span data-stu-id="5e279-108">10596</span></span>                                                                                                                    |
|  <span data-ttu-id="5e279-109">事件源</span><span class="sxs-lookup"><span data-stu-id="5e279-109">Event Source</span></span>   |                                                                                                                   <span data-ttu-id="5e279-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5e279-110">ENTSSO</span></span>                                                                                                                   |
|    <span data-ttu-id="5e279-111">组件</span><span class="sxs-lookup"><span data-stu-id="5e279-111">Component</span></span>    |                                                                                                                    <span data-ttu-id="5e279-112">不可用</span><span class="sxs-lookup"><span data-stu-id="5e279-112">N/A</span></span>                                                                                                                     |
|  <span data-ttu-id="5e279-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="5e279-113">Symbolic Name</span></span>  |                                                                                                     <span data-ttu-id="5e279-114">SSO_WARN_TICKET_USER_NOT_IN_GROUP</span><span class="sxs-lookup"><span data-stu-id="5e279-114">SSO_WARN_TICKET_USER_NOT_IN_GROUP</span></span>                                                                                                      |
|  <span data-ttu-id="5e279-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="5e279-115">Message Text</span></span>   | <span data-ttu-id="5e279-116">无法兑换票证，因为要为其颁发票证的用户不是应用程序用户 account.%r 的成员</span><span class="sxs-lookup"><span data-stu-id="5e279-116">The ticket cannot be redeemed because the user for whom the ticket was issued is not a member of the Application Users account.%r</span></span><br /><br /> <span data-ttu-id="5e279-117">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="5e279-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="5e279-118">有关颁发票证: %2 %r</span><span class="sxs-lookup"><span data-stu-id="5e279-118">Ticket Issued For: %2%r</span></span><br /><br /> <span data-ttu-id="5e279-119">应用程序用户： %3</span><span class="sxs-lookup"><span data-stu-id="5e279-119">Application Users: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="5e279-120">解释</span><span class="sxs-lookup"><span data-stu-id="5e279-120">Explanation</span></span>  
 <span data-ttu-id="5e279-121">无法兑换票证，因为要为其颁发票证的用户不是应用程序用户帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="5e279-121">The ticket cannot be redeemed because the user for whom the ticket was issued is not a member of the Application Users account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5e279-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="5e279-122">User Action</span></span>  
 <span data-ttu-id="5e279-123">是 Application Users 帐户的成员的用户将票证重新颁发。</span><span class="sxs-lookup"><span data-stu-id="5e279-123">Reissue the ticket to a user who is a member of the Application Users account.</span></span>