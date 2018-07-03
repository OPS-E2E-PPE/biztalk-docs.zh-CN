---
title: 单一登录： 事件 10709 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98e86890-88dd-49f0-bb2c-1234507e8be5
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b114b8afb55c41171ef537a9dfc56d341943a226
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014246"
---
# <a name="single-sign-on-event-10709"></a><span data-ttu-id="1f7dc-102">单一登录： 事件 10709</span><span class="sxs-lookup"><span data-stu-id="1f7dc-102">Single Sign-On: Event 10709</span></span>
## <a name="details"></a><span data-ttu-id="1f7dc-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1f7dc-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1f7dc-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1f7dc-104">Product Name</span></span>   |                                                                                                                  <span data-ttu-id="1f7dc-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="1f7dc-105">Enterprise Single Sign-On</span></span>                                                                                                                   |
| <span data-ttu-id="1f7dc-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="1f7dc-106">Product Version</span></span> |                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                  |
|    <span data-ttu-id="1f7dc-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1f7dc-107">Event ID</span></span>     |                                                                                                                            <span data-ttu-id="1f7dc-108">10709</span><span class="sxs-lookup"><span data-stu-id="1f7dc-108">10709</span></span>                                                                                                                             |
|  <span data-ttu-id="1f7dc-109">事件源</span><span class="sxs-lookup"><span data-stu-id="1f7dc-109">Event Source</span></span>   |                                                                                                                            <span data-ttu-id="1f7dc-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1f7dc-110">ENTSSO</span></span>                                                                                                                            |
|    <span data-ttu-id="1f7dc-111">组件</span><span class="sxs-lookup"><span data-stu-id="1f7dc-111">Component</span></span>    |                                                                                                                             <span data-ttu-id="1f7dc-112">N\A</span><span class="sxs-lookup"><span data-stu-id="1f7dc-112">N\A</span></span>                                                                                                                              |
|  <span data-ttu-id="1f7dc-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="1f7dc-113">Symbolic Name</span></span>  |                                                                                                                <span data-ttu-id="1f7dc-114">SSO_WARN_PS_PCNS_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="1f7dc-114">SSO_WARN_PS_PCNS_ACCESS_DENIED</span></span>                                                                                                                |
|  <span data-ttu-id="1f7dc-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="1f7dc-115">Message Text</span></span>   | <span data-ttu-id="1f7dc-116">仅接受来自访问域中域控制器上 PCNS 的 Windows 密码更改。%r</span><span class="sxs-lookup"><span data-stu-id="1f7dc-116">Windows password changes from PCNS will only be accepted from Domain Controllers in the access domain.%r</span></span><br /><br /> <span data-ttu-id="1f7dc-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="1f7dc-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="1f7dc-118">客户端用户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="1f7dc-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="1f7dc-119">访问域: %3 %r</span><span class="sxs-lookup"><span data-stu-id="1f7dc-119">Access Domain: %3%r</span></span><br /><br /> <span data-ttu-id="1f7dc-120">访问 Sid: %4 %r</span><span class="sxs-lookup"><span data-stu-id="1f7dc-120">Access Sid: %4%r</span></span><br /><br /> <span data-ttu-id="1f7dc-121">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="1f7dc-121">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="1f7dc-122">解释</span><span class="sxs-lookup"><span data-stu-id="1f7dc-122">Explanation</span></span>  
 <span data-ttu-id="1f7dc-123">此警告事件表明，收到来自 ENTSSO 服务器域外某个服务器上密码更改通知服务 (PCNS) 的一个 Windows 密码更改。</span><span class="sxs-lookup"><span data-stu-id="1f7dc-123">This Warning event indicates that a Windows password change was received from Password Change Notification Services (PCNS) on a server outside the ENTSSO server's domain.</span></span> <span data-ttu-id="1f7dc-124">仅接受来自 ENTSSO 服务器所在域中的域控制器的 Windows 密码更改。</span><span class="sxs-lookup"><span data-stu-id="1f7dc-124">Windows password changes will only be accepted from domain controllers in the same domain as the ENTSSO server.</span></span>  

## <a name="user-action"></a><span data-ttu-id="1f7dc-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="1f7dc-125">User Action</span></span>  
 <span data-ttu-id="1f7dc-126">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1f7dc-126">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="1f7dc-127">将同一域中的 ENTSSO 服务器配置为 PCNS。</span><span class="sxs-lookup"><span data-stu-id="1f7dc-127">Configure an ENTSSO server in the same domain as PCNS.</span></span>  

  <span data-ttu-id="1f7dc-128">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="1f7dc-128">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="1f7dc-129">密码同步</span><span class="sxs-lookup"><span data-stu-id="1f7dc-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
