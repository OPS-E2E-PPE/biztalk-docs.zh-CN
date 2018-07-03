---
title: 单一登录： 事件 10681 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87ce2e50-cf54-4b23-b247-f137ce64ba1d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d2b400db062dc76b32d071032ee75c55ef48046
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011662"
---
# <a name="single-sign-on-event-10681"></a><span data-ttu-id="73dc6-102">单一登录： 事件 10681</span><span class="sxs-lookup"><span data-stu-id="73dc6-102">Single Sign-On: Event 10681</span></span>
## <a name="details"></a><span data-ttu-id="73dc6-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="73dc6-103">Details</span></span>  

|                 |                                                                                                                                                                                                                      |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="73dc6-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="73dc6-104">Product Name</span></span>   |                                                                                              <span data-ttu-id="73dc6-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="73dc6-105">Enterprise Single Sign-On</span></span>                                                                                               |
| <span data-ttu-id="73dc6-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="73dc6-106">Product Version</span></span> |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                              |
|    <span data-ttu-id="73dc6-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="73dc6-107">Event ID</span></span>     |                                                                                                        <span data-ttu-id="73dc6-108">10681</span><span class="sxs-lookup"><span data-stu-id="73dc6-108">10681</span></span>                                                                                                         |
|  <span data-ttu-id="73dc6-109">事件源</span><span class="sxs-lookup"><span data-stu-id="73dc6-109">Event Source</span></span>   |                                                                                                        <span data-ttu-id="73dc6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="73dc6-110">ENTSSO</span></span>                                                                                                        |
|    <span data-ttu-id="73dc6-111">组件</span><span class="sxs-lookup"><span data-stu-id="73dc6-111">Component</span></span>    |                                                                                                         <span data-ttu-id="73dc6-112">N\A</span><span class="sxs-lookup"><span data-stu-id="73dc6-112">N\A</span></span>                                                                                                          |
|  <span data-ttu-id="73dc6-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="73dc6-113">Symbolic Name</span></span>  |                                                                                         <span data-ttu-id="73dc6-114">SSO_WARN_NO_WINDOWS_PASSWORD_CHANGE</span><span class="sxs-lookup"><span data-stu-id="73dc6-114">SSO_WARN_NO_WINDOWS_PASSWORD_CHANGE</span></span>                                                                                          |
|  <span data-ttu-id="73dc6-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="73dc6-115">Message Text</span></span>   | <span data-ttu-id="73dc6-116">外部密码更改。</span><span class="sxs-lookup"><span data-stu-id="73dc6-116">External password change.</span></span> <span data-ttu-id="73dc6-117">Windows 密码未更改，因为一个或多个外部帐户更改失败。%r</span><span class="sxs-lookup"><span data-stu-id="73dc6-117">The Windows password was not changed because one or more of the external account changes failed.%r</span></span><br /><br /> <span data-ttu-id="73dc6-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="73dc6-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="73dc6-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="73dc6-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="73dc6-120">Windows 帐户： %3</span><span class="sxs-lookup"><span data-stu-id="73dc6-120">Windows Account: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="73dc6-121">解释</span><span class="sxs-lookup"><span data-stu-id="73dc6-121">Explanation</span></span>  
 <span data-ttu-id="73dc6-122">此警告事件表明，因为一个或多个外部帐户更改失败导致 Windows 密码未更改。</span><span class="sxs-lookup"><span data-stu-id="73dc6-122">This Warning event indicates that the Windows password was not changed because one or more of the external account changes failed.</span></span>  

## <a name="user-action"></a><span data-ttu-id="73dc6-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="73dc6-123">User Action</span></span>  
 <span data-ttu-id="73dc6-124">若要解决此警告问题，请执行以下一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="73dc6-124">To resolve this warning, do one or more of the following:</span></span>  

-   <span data-ttu-id="73dc6-125">检查系统和应用程序事件日志，了解相关事件。</span><span class="sxs-lookup"><span data-stu-id="73dc6-125">Check the System and Application Event logs for associated events.</span></span>  

-   <span data-ttu-id="73dc6-126">使用 SSO 管理工具验证适配器配置。</span><span class="sxs-lookup"><span data-stu-id="73dc6-126">Verify adapter configuration using the SSO administration tools.</span></span>  

-   <span data-ttu-id="73dc6-127">验证外部系统。</span><span class="sxs-lookup"><span data-stu-id="73dc6-127">Verify external systems.</span></span>  

## <a name="more-info"></a><span data-ttu-id="73dc6-128">详细信息</span><span class="sxs-lookup"><span data-stu-id="73dc6-128">More info</span></span>

- [<span data-ttu-id="73dc6-129">密码同步</span><span class="sxs-lookup"><span data-stu-id="73dc6-129">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="73dc6-130">**密码同步适配器属性： 选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="73dc6-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
