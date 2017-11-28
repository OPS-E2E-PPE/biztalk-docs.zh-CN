---
title: "单一登录： 事件 11009 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5f06f8c-1614-4538-83e6-689657135776
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99308e7a9e709cff5c0e1e15963eeb4769c00f05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11009"></a><span data-ttu-id="8ffd1-102">单一登录： 事件 11009</span><span class="sxs-lookup"><span data-stu-id="8ffd1-102">Single Sign-On: Event 11009</span></span>
## <a name="details"></a><span data-ttu-id="8ffd1-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8ffd1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8ffd1-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8ffd1-104">Product Name</span></span>|<span data-ttu-id="8ffd1-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="8ffd1-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="8ffd1-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="8ffd1-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="8ffd1-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8ffd1-107">Event ID</span></span>|<span data-ttu-id="8ffd1-108">11009</span><span class="sxs-lookup"><span data-stu-id="8ffd1-108">11009</span></span>|  
|<span data-ttu-id="8ffd1-109">事件源</span><span class="sxs-lookup"><span data-stu-id="8ffd1-109">Event Source</span></span>|<span data-ttu-id="8ffd1-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8ffd1-110">ENTSSO</span></span>|  
|<span data-ttu-id="8ffd1-111">组件</span><span class="sxs-lookup"><span data-stu-id="8ffd1-111">Component</span></span>|<span data-ttu-id="8ffd1-112">N/A</span><span class="sxs-lookup"><span data-stu-id="8ffd1-112">N/A</span></span>|  
|<span data-ttu-id="8ffd1-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="8ffd1-113">Symbolic Name</span></span>|<span data-ttu-id="8ffd1-114">SSO_WARN_NOT_SSO_ADMIN</span><span class="sxs-lookup"><span data-stu-id="8ffd1-114">SSO_WARN_NOT_SSO_ADMIN</span></span>|  
|<span data-ttu-id="8ffd1-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="8ffd1-115">Message Text</span></span>|<span data-ttu-id="8ffd1-116">客户端用户不是 SSO 管理员帐户的成员。%r</span><span class="sxs-lookup"><span data-stu-id="8ffd1-116">Client user is not a member of the SSO Administrators account.%r</span></span><br /><br /> <span data-ttu-id="8ffd1-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="8ffd1-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="8ffd1-118">客户端用户： %2\\%3 %r</span><span class="sxs-lookup"><span data-stu-id="8ffd1-118">Client User: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="8ffd1-119">SSO Administrators: %4</span><span class="sxs-lookup"><span data-stu-id="8ffd1-119">SSO Administrators: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8ffd1-120">解释</span><span class="sxs-lookup"><span data-stu-id="8ffd1-120">Explanation</span></span>  
 <span data-ttu-id="8ffd1-121">客户端用户不是 SSO 管理员帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="8ffd1-121">The client user is not a member of the SSO Administrators account.</span></span> <span data-ttu-id="8ffd1-122">只有当审核级别设置为高时，才会出现此警告。</span><span class="sxs-lookup"><span data-stu-id="8ffd1-122">This warning only appears when the audit levels are set to high.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8ffd1-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="8ffd1-123">User Action</span></span>  
 <span data-ttu-id="8ffd1-124">若要修复此情形，您必须使客户端用户成为 SSO 管理员帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="8ffd1-124">To remedy the situation, you must make the client user a member of the SSO Administrators account.</span></span> <span data-ttu-id="8ffd1-125">若要阻止以后出现此警告，您可以降低审核级别。</span><span class="sxs-lookup"><span data-stu-id="8ffd1-125">To stop this warning from appearing in the future, you can lower the audit levels.</span></span>