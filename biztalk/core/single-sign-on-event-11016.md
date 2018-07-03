---
title: 单一登录： 事件 11016 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3963b706-168d-438d-a068-637f8a6b7b0c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96f39cba26da1b3e03c7259643c3dcf2704bbdf3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974510"
---
# <a name="single-sign-on-event-11016"></a><span data-ttu-id="e0594-102">单一登录： 事件 11016</span><span class="sxs-lookup"><span data-stu-id="e0594-102">Single Sign-On: Event 11016</span></span>
## <a name="details"></a><span data-ttu-id="e0594-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e0594-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e0594-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e0594-104">Product Name</span></span>   |                                                                                                                                                                   <span data-ttu-id="e0594-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="e0594-105">Enterprise Single Sign-On</span></span>                                                                                                                                                                    |
| <span data-ttu-id="e0594-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="e0594-106">Product Version</span></span> |                                                                                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                   |
|    <span data-ttu-id="e0594-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e0594-107">Event ID</span></span>     |                                                                                                                                                                             <span data-ttu-id="e0594-108">11016</span><span class="sxs-lookup"><span data-stu-id="e0594-108">11016</span></span>                                                                                                                                                                              |
|  <span data-ttu-id="e0594-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e0594-109">Event Source</span></span>   |                                                                                                                                                                             <span data-ttu-id="e0594-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e0594-110">ENTSSO</span></span>                                                                                                                                                                             |
|    <span data-ttu-id="e0594-111">组件</span><span class="sxs-lookup"><span data-stu-id="e0594-111">Component</span></span>    |                                                                                                                                                                              <span data-ttu-id="e0594-112">N/A</span><span class="sxs-lookup"><span data-stu-id="e0594-112">N/A</span></span>                                                                                                                                                                               |
|  <span data-ttu-id="e0594-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e0594-113">Symbolic Name</span></span>  |                                                                                                                                                                <span data-ttu-id="e0594-114">RPC EXTENDED ERROR INFORMATION%r</span><span class="sxs-lookup"><span data-stu-id="e0594-114">RPC EXTENDED ERROR INFORMATION%r</span></span>                                                                                                                                                                |
|  <span data-ttu-id="e0594-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e0594-115">Message Text</span></span>   | <span data-ttu-id="e0594-116">%1%r</span><span class="sxs-lookup"><span data-stu-id="e0594-116">%1%r</span></span><br /><br /> <span data-ttu-id="e0594-117">错误代码： %2</span><span class="sxs-lookup"><span data-stu-id="e0594-117">Error Code: %2</span></span><br /><br /> <span data-ttu-id="e0594-118">AuthzInitializeContextFromSid 函数失败，错误消息为 ERROR_ACCESS_DENIED。</span><span class="sxs-lookup"><span data-stu-id="e0594-118">The AuthzInitializeContextFromSid function failed with ERROR_ACCESS_DENIED.</span></span> <span data-ttu-id="e0594-119">这表示运行 SSO 服务器的服务帐户没有足够的权限在 Active Directory 中检查组成员身份。</span><span class="sxs-lookup"><span data-stu-id="e0594-119">This means that the service account that the SSO server is running under does not have sufficient permissions to check group membership in Active Directory.</span></span> <span data-ttu-id="e0594-120">请查看您的文档，了解有关如何解决此问题的详细信息。%r</span><span class="sxs-lookup"><span data-stu-id="e0594-120">Please check your documentation for details on how to fix this problem.%r</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e0594-121">解释</span><span class="sxs-lookup"><span data-stu-id="e0594-121">Explanation</span></span>  
 <span data-ttu-id="e0594-122">运行 SSO 服务器的服务帐户没有足够的权限在 Active Directory 中检查组成员身份。</span><span class="sxs-lookup"><span data-stu-id="e0594-122">The service account that the SSO server is running under does not have sufficient permissions to check group membership in Active Directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e0594-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="e0594-123">User Action</span></span>  
 <span data-ttu-id="e0594-124">请参阅[SSO 服务器](../core/sso-server.md)SSO 文档中。</span><span class="sxs-lookup"><span data-stu-id="e0594-124">See [SSO Server](../core/sso-server.md) in the SSO documentation.</span></span>