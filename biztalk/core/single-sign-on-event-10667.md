---
title: 单一登录：Event 10667 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 74bbe7e6-af21-434c-9a62-3c3b13ca3307
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e5115d7d521a0e19d1b48f5c1bf1f9f1f5937e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397549"
---
# <a name="single-sign-on-event-10667"></a><span data-ttu-id="d2f04-102">单一登录：事件 10667</span><span class="sxs-lookup"><span data-stu-id="d2f04-102">Single Sign-On: Event 10667</span></span>
## <a name="details"></a><span data-ttu-id="d2f04-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d2f04-103">Details</span></span>  

|                 |                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d2f04-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d2f04-104">Product Name</span></span>   |                                                        <span data-ttu-id="d2f04-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="d2f04-105">Enterprise Single Sign-On</span></span>                                                        |
| <span data-ttu-id="d2f04-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="d2f04-106">Product Version</span></span> |                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                        |
|    <span data-ttu-id="d2f04-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d2f04-107">Event ID</span></span>     |                                                                  <span data-ttu-id="d2f04-108">10667</span><span class="sxs-lookup"><span data-stu-id="d2f04-108">10667</span></span>                                                                  |
|  <span data-ttu-id="d2f04-109">事件源</span><span class="sxs-lookup"><span data-stu-id="d2f04-109">Event Source</span></span>   |                                                                 <span data-ttu-id="d2f04-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d2f04-110">ENTSSO</span></span>                                                                  |
|    <span data-ttu-id="d2f04-111">组件</span><span class="sxs-lookup"><span data-stu-id="d2f04-111">Component</span></span>    |                                                                   <span data-ttu-id="d2f04-112">N\A</span><span class="sxs-lookup"><span data-stu-id="d2f04-112">N\A</span></span>                                                                   |
|  <span data-ttu-id="d2f04-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="d2f04-113">Symbolic Name</span></span>  |                                          <span data-ttu-id="d2f04-114">SSO_INFO_SUPPRESSED_DUPLICATE_WINDOWS_PASSWORD_CHANGE</span><span class="sxs-lookup"><span data-stu-id="d2f04-114">SSO_INFO_SUPPRESSED_DUPLICATE_WINDOWS_PASSWORD_CHANGE</span></span>                                          |
|  <span data-ttu-id="d2f04-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="d2f04-115">Message Text</span></span>   | <span data-ttu-id="d2f04-116">禁止显示重复的 Windows 密码 change.%r</span><span class="sxs-lookup"><span data-stu-id="d2f04-116">Suppressed duplicate Windows password change.%r</span></span><br /><br /> <span data-ttu-id="d2f04-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d2f04-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="d2f04-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="d2f04-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="d2f04-119">Windows 帐户： %3</span><span class="sxs-lookup"><span data-stu-id="d2f04-119">Windows Account: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="d2f04-120">解释</span><span class="sxs-lookup"><span data-stu-id="d2f04-120">Explanation</span></span>  
 <span data-ttu-id="d2f04-121">此信息事件表明 SSO 已取消重复的 Windows 密码更改。</span><span class="sxs-lookup"><span data-stu-id="d2f04-121">This Information event indicates that SSO has suppressed a duplicate Windows password change.</span></span>  

## <a name="user-action"></a><span data-ttu-id="d2f04-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="d2f04-122">User Action</span></span>  

-   <span data-ttu-id="d2f04-123">不不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="d2f04-123">No user action is necessary.</span></span>  

## <a name="more-info"></a><span data-ttu-id="d2f04-124">详细信息</span><span class="sxs-lookup"><span data-stu-id="d2f04-124">More info</span></span>

- [<span data-ttu-id="d2f04-125">密码同步</span><span class="sxs-lookup"><span data-stu-id="d2f04-125">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="d2f04-126">**密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="d2f04-126">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
