---
title: "单一登录： 事件 10550 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73d63bc5-1e60-426c-a0d6-55c51dbb8d76
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9772885746f2c0519cba84db9ad1bee612607117
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10550"></a><span data-ttu-id="d06f8-102">单一登录： 事件 10550</span><span class="sxs-lookup"><span data-stu-id="d06f8-102">Single Sign-On: Event 10550</span></span>
## <a name="details"></a><span data-ttu-id="d06f8-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d06f8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d06f8-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d06f8-104">Product Name</span></span>|<span data-ttu-id="d06f8-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="d06f8-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="d06f8-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="d06f8-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="d06f8-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d06f8-107">Event ID</span></span>|<span data-ttu-id="d06f8-108">10550</span><span class="sxs-lookup"><span data-stu-id="d06f8-108">10550</span></span>|  
|<span data-ttu-id="d06f8-109">事件源</span><span class="sxs-lookup"><span data-stu-id="d06f8-109">Event Source</span></span>|<span data-ttu-id="d06f8-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d06f8-110">ENTSSO</span></span>|  
|<span data-ttu-id="d06f8-111">组件</span><span class="sxs-lookup"><span data-stu-id="d06f8-111">Component</span></span>|<span data-ttu-id="d06f8-112">N/A</span><span class="sxs-lookup"><span data-stu-id="d06f8-112">N/A</span></span>|  
|<span data-ttu-id="d06f8-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="d06f8-113">Symbolic Name</span></span>|<span data-ttu-id="d06f8-114">SSO_ERROR_SERVICE_NOT_SSO_ADMIN</span><span class="sxs-lookup"><span data-stu-id="d06f8-114">SSO_ERROR_SERVICE_NOT_SSO_ADMIN</span></span>|  
|<span data-ttu-id="d06f8-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="d06f8-115">Message Text</span></span>|<span data-ttu-id="d06f8-116">SSO 服务无法启动，因为运行该服务的服务帐户不是 SSO 管理员帐户的成员。%r</span><span class="sxs-lookup"><span data-stu-id="d06f8-116">The SSO service could not start because the service account it is running under is not a member of the SSO Administrators account.%r</span></span><br /><br /> <span data-ttu-id="d06f8-117">SSO Administrators: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d06f8-117">SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="d06f8-118">SSO 服务帐户： %2</span><span class="sxs-lookup"><span data-stu-id="d06f8-118">SSO Service Account: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d06f8-119">解释</span><span class="sxs-lookup"><span data-stu-id="d06f8-119">Explanation</span></span>  
 <span data-ttu-id="d06f8-120">SSO 服务必须是 SSO Administrators 帐户的成员的服务帐户下运行。</span><span class="sxs-lookup"><span data-stu-id="d06f8-120">The SSO service must be running under a service account that is a member of the SSO Administrators account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d06f8-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="d06f8-121">User Action</span></span>  
 <span data-ttu-id="d06f8-122">有关详细信息，请参阅[如何指定 SSO Administrators 和 Affiliate Administrators 帐户](../core/how-to-specify-sso-administrators-and-affiliate-administrators-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="d06f8-122">For more information, see [How to Specify SSO Administrators and Affiliate Administrators Accounts](../core/how-to-specify-sso-administrators-and-affiliate-administrators-accounts.md).</span></span>