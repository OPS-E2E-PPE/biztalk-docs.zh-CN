---
title: 单一登录： 事件 10715 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f63c98d2-988e-466f-be40-171b13a34732
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9bc461aa812c2c61844c11d54743335ac89321a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994854"
---
# <a name="single-sign-on-event-10715"></a><span data-ttu-id="78301-102">单一登录： 事件 10715</span><span class="sxs-lookup"><span data-stu-id="78301-102">Single Sign-On: Event 10715</span></span>
## <a name="details"></a><span data-ttu-id="78301-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="78301-103">Details</span></span>  

|                 |                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="78301-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="78301-104">Product Name</span></span>   |                                                                                            <span data-ttu-id="78301-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="78301-105">Enterprise Single Sign-On</span></span>                                                                                             |
| <span data-ttu-id="78301-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="78301-106">Product Version</span></span> |                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                            |
|    <span data-ttu-id="78301-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="78301-107">Event ID</span></span>     |                                                                                                      <span data-ttu-id="78301-108">10715</span><span class="sxs-lookup"><span data-stu-id="78301-108">10715</span></span>                                                                                                       |
|  <span data-ttu-id="78301-109">事件源</span><span class="sxs-lookup"><span data-stu-id="78301-109">Event Source</span></span>   |                                                                                                      <span data-ttu-id="78301-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="78301-110">ENTSSO</span></span>                                                                                                      |
|    <span data-ttu-id="78301-111">组件</span><span class="sxs-lookup"><span data-stu-id="78301-111">Component</span></span>    |                                                                                                       <span data-ttu-id="78301-112">N\A</span><span class="sxs-lookup"><span data-stu-id="78301-112">N\A</span></span>                                                                                                        |
|  <span data-ttu-id="78301-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="78301-113">Symbolic Name</span></span>  |                                                                                            <span data-ttu-id="78301-114">SSO_WARN_NO_CREATE_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="78301-114">SSO_WARN_NO_CREATE_ADAPTER</span></span>                                                                                            |
|  <span data-ttu-id="78301-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="78301-115">Message Text</span></span>   | <span data-ttu-id="78301-116">客户端用户必须是 SSO 管理员帐户的成员才能创建适配器。%r</span><span class="sxs-lookup"><span data-stu-id="78301-116">The client user must be a member of the SSO Administrators account to create adapters.%r</span></span><br /><br /> <span data-ttu-id="78301-117">客户端用户: %1 %r</span><span class="sxs-lookup"><span data-stu-id="78301-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="78301-118">SSO Administrators: %2 %r</span><span class="sxs-lookup"><span data-stu-id="78301-118">SSO Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="78301-119">适配器: %3 %r</span><span class="sxs-lookup"><span data-stu-id="78301-119">Adapter: %3%r</span></span><br /><br /> <span data-ttu-id="78301-120">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="78301-120">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="78301-121">解释</span><span class="sxs-lookup"><span data-stu-id="78301-121">Explanation</span></span>  
 <span data-ttu-id="78301-122">此警告事件表示客户端用户必须是 SSO 管理员帐户的成员才能创建适配器。</span><span class="sxs-lookup"><span data-stu-id="78301-122">This Warning event indicates that the client user must be a member of the SSO Administrators account to create adapters.</span></span>  

## <a name="user-action"></a><span data-ttu-id="78301-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="78301-123">User Action</span></span>  
 <span data-ttu-id="78301-124">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="78301-124">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="78301-125">登录所用帐户所属的 SSO 管理员组。</span><span class="sxs-lookup"><span data-stu-id="78301-125">Logon with an account that belongs to the SSO Administrators group.</span></span>  

  <span data-ttu-id="78301-126">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="78301-126">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="78301-127">SSO 用户组</span><span class="sxs-lookup"><span data-stu-id="78301-127">SSO User Groups</span></span>](../core/sso-user-groups.md)
