---
title: 单一登录：Event 11060 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4851fba-0d3a-4a29-b720-a1d175d20555
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ded0ef8904e0a9def8d02ffe477ef7a3d846c14d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258686"
---
# <a name="single-sign-on-event-11060"></a><span data-ttu-id="2f44e-102">单一登录：事件 11060</span><span class="sxs-lookup"><span data-stu-id="2f44e-102">Single Sign-On: Event 11060</span></span>
## <a name="details"></a><span data-ttu-id="2f44e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="2f44e-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="2f44e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="2f44e-104">Product Name</span></span>   |                                                                                               <span data-ttu-id="2f44e-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="2f44e-105">Enterprise Single Sign-On</span></span>                                                                                               |
| <span data-ttu-id="2f44e-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="2f44e-106">Product Version</span></span> |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    <span data-ttu-id="2f44e-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2f44e-107">Event ID</span></span>     |                                                                                                         <span data-ttu-id="2f44e-108">11060</span><span class="sxs-lookup"><span data-stu-id="2f44e-108">11060</span></span>                                                                                                         |
|  <span data-ttu-id="2f44e-109">事件源</span><span class="sxs-lookup"><span data-stu-id="2f44e-109">Event Source</span></span>   |                                                                                                        <span data-ttu-id="2f44e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="2f44e-110">ENTSSO</span></span>                                                                                                         |
|    <span data-ttu-id="2f44e-111">组件</span><span class="sxs-lookup"><span data-stu-id="2f44e-111">Component</span></span>    |                                                                                                          <span data-ttu-id="2f44e-112">不可用</span><span class="sxs-lookup"><span data-stu-id="2f44e-112">N/A</span></span>                                                                                                          |
|  <span data-ttu-id="2f44e-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="2f44e-113">Symbolic Name</span></span>  |                                                                                            <span data-ttu-id="2f44e-114">SSO_WARN_PS_MIIS_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="2f44e-114">SSO_WARN_PS_MIIS_ACCESS_DENIED</span></span>                                                                                             |
|  <span data-ttu-id="2f44e-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="2f44e-115">Message Text</span></span>   | <span data-ttu-id="2f44e-116">从 MIIS 进行 Windows 密码更改将仅接受来自 account.%r</span><span class="sxs-lookup"><span data-stu-id="2f44e-116">Windows password changes from MIIS will only be accepted from the SSO service account.%r</span></span><br /><br /> <span data-ttu-id="2f44e-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="2f44e-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="2f44e-118">客户端用户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="2f44e-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="2f44e-119">SSO 服务帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="2f44e-119">SSO Service Account: %3%r</span></span><br /><br /> <span data-ttu-id="2f44e-120">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="2f44e-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="2f44e-121">解释</span><span class="sxs-lookup"><span data-stu-id="2f44e-121">Explanation</span></span>  
 <span data-ttu-id="2f44e-122">ENTSSO 服务器从 Microsoft Identity Integration Server (MIIS) 收到密码更改。</span><span class="sxs-lookup"><span data-stu-id="2f44e-122">A password change has been received by the ENTSSO server from Microsoft Identity Integration Server (MIIS).</span></span> <span data-ttu-id="2f44e-123">但是，ENTSSO 服务器将只接受从 MIIS 进行密码更改，如果客户端用户 （调用方） 是与 SSO 服务帐户相同的帐户。</span><span class="sxs-lookup"><span data-stu-id="2f44e-123">However, the ENTSSO server will only accept password changes from MIIS if the Client User (the caller) is the same account as the SSO service account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2f44e-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="2f44e-124">User Action</span></span>  
 <span data-ttu-id="2f44e-125">检查 MIIS 中密码同步调用方的配置。</span><span class="sxs-lookup"><span data-stu-id="2f44e-125">Check the configuration of the caller for password sync in MIIS.</span></span> <span data-ttu-id="2f44e-126">有关详细信息，请参阅[如何实现 MIIS 密码同步配置 ENTSSO](../core/how-to-configure-entsso-for-miis-password-sync.md)。</span><span class="sxs-lookup"><span data-stu-id="2f44e-126">For more information, see [How to Configure ENTSSO for MIIS Password Sync](../core/how-to-configure-entsso-for-miis-password-sync.md).</span></span>