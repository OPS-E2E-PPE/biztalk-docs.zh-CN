---
title: 单一登录：Event 10709 | Microsoft Docs
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
ms.openlocfilehash: f4f69e2226ab304e9d6b23ead1c9e2b84ffa9fb4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397247"
---
# <a name="single-sign-on-event-10709"></a><span data-ttu-id="79679-102">单一登录：事件 10709</span><span class="sxs-lookup"><span data-stu-id="79679-102">Single Sign-On: Event 10709</span></span>
## <a name="details"></a><span data-ttu-id="79679-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="79679-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="79679-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="79679-104">Product Name</span></span>   |                                                                                                                  <span data-ttu-id="79679-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="79679-105">Enterprise Single Sign-On</span></span>                                                                                                                   |
| <span data-ttu-id="79679-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="79679-106">Product Version</span></span> |                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                  |
|    <span data-ttu-id="79679-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="79679-107">Event ID</span></span>     |                                                                                                                            <span data-ttu-id="79679-108">10709</span><span class="sxs-lookup"><span data-stu-id="79679-108">10709</span></span>                                                                                                                             |
|  <span data-ttu-id="79679-109">事件源</span><span class="sxs-lookup"><span data-stu-id="79679-109">Event Source</span></span>   |                                                                                                                            <span data-ttu-id="79679-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="79679-110">ENTSSO</span></span>                                                                                                                            |
|    <span data-ttu-id="79679-111">组件</span><span class="sxs-lookup"><span data-stu-id="79679-111">Component</span></span>    |                                                                                                                             <span data-ttu-id="79679-112">N\A</span><span class="sxs-lookup"><span data-stu-id="79679-112">N\A</span></span>                                                                                                                              |
|  <span data-ttu-id="79679-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="79679-113">Symbolic Name</span></span>  |                                                                                                                <span data-ttu-id="79679-114">SSO_WARN_PS_PCNS_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="79679-114">SSO_WARN_PS_PCNS_ACCESS_DENIED</span></span>                                                                                                                |
|  <span data-ttu-id="79679-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="79679-115">Message Text</span></span>   | <span data-ttu-id="79679-116">从 PCNS 的 Windows 密码更改将仅接受来自域控制器中访问 domain.%r</span><span class="sxs-lookup"><span data-stu-id="79679-116">Windows password changes from PCNS will only be accepted from Domain Controllers in the access domain.%r</span></span><br /><br /> <span data-ttu-id="79679-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="79679-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="79679-118">客户端用户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="79679-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="79679-119">访问域: %3 %r</span><span class="sxs-lookup"><span data-stu-id="79679-119">Access Domain: %3%r</span></span><br /><br /> <span data-ttu-id="79679-120">访问 Sid: %4 %r</span><span class="sxs-lookup"><span data-stu-id="79679-120">Access Sid: %4%r</span></span><br /><br /> <span data-ttu-id="79679-121">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="79679-121">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="79679-122">解释</span><span class="sxs-lookup"><span data-stu-id="79679-122">Explanation</span></span>  
 <span data-ttu-id="79679-123">此警告事件表明 Windows 密码更改已在 ENTSSO 服务器域之外的服务器上收到来自密码更改通知服务 (PCNS)。</span><span class="sxs-lookup"><span data-stu-id="79679-123">This Warning event indicates that a Windows password change was received from Password Change Notification Services (PCNS) on a server outside the ENTSSO server's domain.</span></span> <span data-ttu-id="79679-124">Windows 密码更改将仅接受来自 ENTSSO 服务器所在域中的域控制器。</span><span class="sxs-lookup"><span data-stu-id="79679-124">Windows password changes will only be accepted from domain controllers in the same domain as the ENTSSO server.</span></span>  

## <a name="user-action"></a><span data-ttu-id="79679-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="79679-125">User Action</span></span>  
 <span data-ttu-id="79679-126">若要解决此警告，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="79679-126">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="79679-127">ENTSSO 服务器配置为 PCNS 位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="79679-127">Configure an ENTSSO server in the same domain as PCNS.</span></span>  

  <span data-ttu-id="79679-128">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="79679-128">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="79679-129">密码同步</span><span class="sxs-lookup"><span data-stu-id="79679-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
