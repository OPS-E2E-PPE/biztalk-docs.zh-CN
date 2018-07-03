---
title: 单一登录： 事件 11009 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5f06f8c-1614-4538-83e6-689657135776
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96dc58b9f4a0e3fbed894323e2d281b1e9884961
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972118"
---
# <a name="single-sign-on-event-11009"></a><span data-ttu-id="bdbaa-102">单一登录： 事件 11009</span><span class="sxs-lookup"><span data-stu-id="bdbaa-102">Single Sign-On: Event 11009</span></span>
## <a name="details"></a><span data-ttu-id="bdbaa-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="bdbaa-103">Details</span></span>  
  
|                 |                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="bdbaa-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="bdbaa-104">Product Name</span></span>   |                                                                      <span data-ttu-id="bdbaa-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="bdbaa-105">Enterprise Single Sign-On</span></span>                                                                      |
| <span data-ttu-id="bdbaa-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="bdbaa-106">Product Version</span></span> |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                      |
|    <span data-ttu-id="bdbaa-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="bdbaa-107">Event ID</span></span>     |                                                                                <span data-ttu-id="bdbaa-108">11009</span><span class="sxs-lookup"><span data-stu-id="bdbaa-108">11009</span></span>                                                                                |
|  <span data-ttu-id="bdbaa-109">事件源</span><span class="sxs-lookup"><span data-stu-id="bdbaa-109">Event Source</span></span>   |                                                                               <span data-ttu-id="bdbaa-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bdbaa-110">ENTSSO</span></span>                                                                                |
|    <span data-ttu-id="bdbaa-111">组件</span><span class="sxs-lookup"><span data-stu-id="bdbaa-111">Component</span></span>    |                                                                                 <span data-ttu-id="bdbaa-112">N/A</span><span class="sxs-lookup"><span data-stu-id="bdbaa-112">N/A</span></span>                                                                                 |
|  <span data-ttu-id="bdbaa-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="bdbaa-113">Symbolic Name</span></span>  |                                                                       <span data-ttu-id="bdbaa-114">SSO_WARN_NOT_SSO_ADMIN</span><span class="sxs-lookup"><span data-stu-id="bdbaa-114">SSO_WARN_NOT_SSO_ADMIN</span></span>                                                                        |
|  <span data-ttu-id="bdbaa-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="bdbaa-115">Message Text</span></span>   | <span data-ttu-id="bdbaa-116">客户端用户不是 SSO 管理员帐户的成员。%r</span><span class="sxs-lookup"><span data-stu-id="bdbaa-116">Client user is not a member of the SSO Administrators account.%r</span></span><br /><br /> <span data-ttu-id="bdbaa-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="bdbaa-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="bdbaa-118">客户端用户： %2\\%3 %r</span><span class="sxs-lookup"><span data-stu-id="bdbaa-118">Client User: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="bdbaa-119">SSO 管理员： %4</span><span class="sxs-lookup"><span data-stu-id="bdbaa-119">SSO Administrators: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="bdbaa-120">解释</span><span class="sxs-lookup"><span data-stu-id="bdbaa-120">Explanation</span></span>  
 <span data-ttu-id="bdbaa-121">客户端用户不是 SSO 管理员帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="bdbaa-121">The client user is not a member of the SSO Administrators account.</span></span> <span data-ttu-id="bdbaa-122">只有当审核级别设置为高时，才会出现此警告。</span><span class="sxs-lookup"><span data-stu-id="bdbaa-122">This warning only appears when the audit levels are set to high.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bdbaa-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="bdbaa-123">User Action</span></span>  
 <span data-ttu-id="bdbaa-124">若要修复此情形，您必须使客户端用户成为 SSO 管理员帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="bdbaa-124">To remedy the situation, you must make the client user a member of the SSO Administrators account.</span></span> <span data-ttu-id="bdbaa-125">若要阻止以后出现此警告，您可以降低审核级别。</span><span class="sxs-lookup"><span data-stu-id="bdbaa-125">To stop this warning from appearing in the future, you can lower the audit levels.</span></span>