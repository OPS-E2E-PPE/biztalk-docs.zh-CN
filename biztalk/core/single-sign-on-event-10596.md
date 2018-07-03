---
title: 单一登录： 事件 10596 |Microsoft Docs
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
ms.openlocfilehash: 3a1e565ca3b96663e0ece5a2cf68c02d3258ac5d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008790"
---
# <a name="single-sign-on-event-10596"></a><span data-ttu-id="8dd56-102">单一登录： 事件 10596</span><span class="sxs-lookup"><span data-stu-id="8dd56-102">Single Sign-On: Event 10596</span></span>
## <a name="details"></a><span data-ttu-id="8dd56-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8dd56-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8dd56-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8dd56-104">Product Name</span></span>   |                                                                                                         <span data-ttu-id="8dd56-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="8dd56-105">Enterprise Single Sign-On</span></span>                                                                                                          |
| <span data-ttu-id="8dd56-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="8dd56-106">Product Version</span></span> |                                                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                         |
|    <span data-ttu-id="8dd56-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8dd56-107">Event ID</span></span>     |                                                                                                                   <span data-ttu-id="8dd56-108">10596</span><span class="sxs-lookup"><span data-stu-id="8dd56-108">10596</span></span>                                                                                                                    |
|  <span data-ttu-id="8dd56-109">事件源</span><span class="sxs-lookup"><span data-stu-id="8dd56-109">Event Source</span></span>   |                                                                                                                   <span data-ttu-id="8dd56-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8dd56-110">ENTSSO</span></span>                                                                                                                   |
|    <span data-ttu-id="8dd56-111">组件</span><span class="sxs-lookup"><span data-stu-id="8dd56-111">Component</span></span>    |                                                                                                                    <span data-ttu-id="8dd56-112">N/A</span><span class="sxs-lookup"><span data-stu-id="8dd56-112">N/A</span></span>                                                                                                                     |
|  <span data-ttu-id="8dd56-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="8dd56-113">Symbolic Name</span></span>  |                                                                                                     <span data-ttu-id="8dd56-114">SSO_WARN_TICKET_USER_NOT_IN_GROUP</span><span class="sxs-lookup"><span data-stu-id="8dd56-114">SSO_WARN_TICKET_USER_NOT_IN_GROUP</span></span>                                                                                                      |
|  <span data-ttu-id="8dd56-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="8dd56-115">Message Text</span></span>   | <span data-ttu-id="8dd56-116">无法兑换票证，因为要使用所颁发票证的用户不是应用程序用户帐户的成员。%r</span><span class="sxs-lookup"><span data-stu-id="8dd56-116">The ticket cannot be redeemed because the user for whom the ticket was issued is not a member of the Application Users account.%r</span></span><br /><br /> <span data-ttu-id="8dd56-117">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="8dd56-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="8dd56-118">有关颁发票证: %2 %r</span><span class="sxs-lookup"><span data-stu-id="8dd56-118">Ticket Issued For: %2%r</span></span><br /><br /> <span data-ttu-id="8dd56-119">应用程序用户： %3</span><span class="sxs-lookup"><span data-stu-id="8dd56-119">Application Users: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="8dd56-120">解释</span><span class="sxs-lookup"><span data-stu-id="8dd56-120">Explanation</span></span>  
 <span data-ttu-id="8dd56-121">无法兑换票证，因为要使用所颁发票证的用户不是应用程序用户帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="8dd56-121">The ticket cannot be redeemed because the user for whom the ticket was issued is not a member of the Application Users account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8dd56-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="8dd56-122">User Action</span></span>  
 <span data-ttu-id="8dd56-123">将票证重新颁发给属于应用程序用户帐户成员的用户。</span><span class="sxs-lookup"><span data-stu-id="8dd56-123">Reissue the ticket to a user who is a member of the Application Users account.</span></span>