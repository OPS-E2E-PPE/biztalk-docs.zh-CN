---
title: "单一登录： 事件 11016 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3963b706-168d-438d-a068-637f8a6b7b0c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f84bfef5dcef8e28bb3616ce30f1addc77f240c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11016"></a><span data-ttu-id="d892f-102">单一登录： 事件 11016</span><span class="sxs-lookup"><span data-stu-id="d892f-102">Single Sign-On: Event 11016</span></span>
## <a name="details"></a><span data-ttu-id="d892f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d892f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d892f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d892f-104">Product Name</span></span>|<span data-ttu-id="d892f-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="d892f-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="d892f-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="d892f-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="d892f-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d892f-107">Event ID</span></span>|<span data-ttu-id="d892f-108">11016</span><span class="sxs-lookup"><span data-stu-id="d892f-108">11016</span></span>|  
|<span data-ttu-id="d892f-109">事件源</span><span class="sxs-lookup"><span data-stu-id="d892f-109">Event Source</span></span>|<span data-ttu-id="d892f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d892f-110">ENTSSO</span></span>|  
|<span data-ttu-id="d892f-111">组件</span><span class="sxs-lookup"><span data-stu-id="d892f-111">Component</span></span>|<span data-ttu-id="d892f-112">N/A</span><span class="sxs-lookup"><span data-stu-id="d892f-112">N/A</span></span>|  
|<span data-ttu-id="d892f-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="d892f-113">Symbolic Name</span></span>|<span data-ttu-id="d892f-114">RPC EXTENDED ERROR INFORMATION%r</span><span class="sxs-lookup"><span data-stu-id="d892f-114">RPC EXTENDED ERROR INFORMATION%r</span></span>|  
|<span data-ttu-id="d892f-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="d892f-115">Message Text</span></span>|<span data-ttu-id="d892f-116">%1%r</span><span class="sxs-lookup"><span data-stu-id="d892f-116">%1%r</span></span><br /><br /> <span data-ttu-id="d892f-117">错误代码： %2</span><span class="sxs-lookup"><span data-stu-id="d892f-117">Error Code: %2</span></span><br /><br /> <span data-ttu-id="d892f-118">AuthzInitializeContextFromSid 函数失败，错误消息为 ERROR_ACCESS_DENIED。</span><span class="sxs-lookup"><span data-stu-id="d892f-118">The AuthzInitializeContextFromSid function failed with ERROR_ACCESS_DENIED.</span></span> <span data-ttu-id="d892f-119">这表示运行 SSO 服务器的服务帐户没有足够的权限在 Active Directory 中检查组成员身份。</span><span class="sxs-lookup"><span data-stu-id="d892f-119">This means that the service account that the SSO server is running under does not have sufficient permissions to check group membership in Active Directory.</span></span> <span data-ttu-id="d892f-120">请查看您的文档，了解有关如何解决此问题的详细信息。%r</span><span class="sxs-lookup"><span data-stu-id="d892f-120">Please check your documentation for details on how to fix this problem.%r</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d892f-121">解释</span><span class="sxs-lookup"><span data-stu-id="d892f-121">Explanation</span></span>  
 <span data-ttu-id="d892f-122">运行 SSO 服务器的服务帐户没有足够的权限在 Active Directory 中检查组成员身份。</span><span class="sxs-lookup"><span data-stu-id="d892f-122">The service account that the SSO server is running under does not have sufficient permissions to check group membership in Active Directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d892f-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="d892f-123">User Action</span></span>  
 <span data-ttu-id="d892f-124">请参阅[SSO 服务器](../core/sso-server.md)SSO 文档中。</span><span class="sxs-lookup"><span data-stu-id="d892f-124">See [SSO Server](../core/sso-server.md) in the SSO documentation.</span></span>