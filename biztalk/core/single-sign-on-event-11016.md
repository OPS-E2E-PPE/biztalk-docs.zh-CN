---
title: 单一登录：Event 11016 | Microsoft Docs
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
ms.openlocfilehash: 01bf4d34a68680b391e49b465e44138fca81b210
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267072"
---
# <a name="single-sign-on-event-11016"></a><span data-ttu-id="992f5-102">单一登录：事件 11016</span><span class="sxs-lookup"><span data-stu-id="992f5-102">Single Sign-On: Event 11016</span></span>
## <a name="details"></a><span data-ttu-id="992f5-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="992f5-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="992f5-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="992f5-104">Product Name</span></span>   |                                                                                                                                                                   <span data-ttu-id="992f5-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="992f5-105">Enterprise Single Sign-On</span></span>                                                                                                                                                                    |
| <span data-ttu-id="992f5-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="992f5-106">Product Version</span></span> |                                                                                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                   |
|    <span data-ttu-id="992f5-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="992f5-107">Event ID</span></span>     |                                                                                                                                                                             <span data-ttu-id="992f5-108">11016</span><span class="sxs-lookup"><span data-stu-id="992f5-108">11016</span></span>                                                                                                                                                                              |
|  <span data-ttu-id="992f5-109">事件源</span><span class="sxs-lookup"><span data-stu-id="992f5-109">Event Source</span></span>   |                                                                                                                                                                             <span data-ttu-id="992f5-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="992f5-110">ENTSSO</span></span>                                                                                                                                                                             |
|    <span data-ttu-id="992f5-111">组件</span><span class="sxs-lookup"><span data-stu-id="992f5-111">Component</span></span>    |                                                                                                                                                                              <span data-ttu-id="992f5-112">不可用</span><span class="sxs-lookup"><span data-stu-id="992f5-112">N/A</span></span>                                                                                                                                                                               |
|  <span data-ttu-id="992f5-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="992f5-113">Symbolic Name</span></span>  |                                                                                                                                                                <span data-ttu-id="992f5-114">RPC 扩展错误信息 %r</span><span class="sxs-lookup"><span data-stu-id="992f5-114">RPC EXTENDED ERROR INFORMATION%r</span></span>                                                                                                                                                                |
|  <span data-ttu-id="992f5-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="992f5-115">Message Text</span></span>   | <span data-ttu-id="992f5-116">%1%r</span><span class="sxs-lookup"><span data-stu-id="992f5-116">%1%r</span></span><br /><br /> <span data-ttu-id="992f5-117">错误代码： %2</span><span class="sxs-lookup"><span data-stu-id="992f5-117">Error Code: %2</span></span><br /><br /> <span data-ttu-id="992f5-118">AuthzInitializeContextFromSid 函数失败，出现 ERROR_ACCESS_DENIED。</span><span class="sxs-lookup"><span data-stu-id="992f5-118">The AuthzInitializeContextFromSid function failed with ERROR_ACCESS_DENIED.</span></span> <span data-ttu-id="992f5-119">这意味着 SSO 服务器下运行的服务帐户没有足够的权限来检查 Active Directory 中的组成员身份。</span><span class="sxs-lookup"><span data-stu-id="992f5-119">This means that the service account that the SSO server is running under does not have sufficient permissions to check group membership in Active Directory.</span></span> <span data-ttu-id="992f5-120">请检查您的文档详细介绍了如何修复此 problem.%r</span><span class="sxs-lookup"><span data-stu-id="992f5-120">Please check your documentation for details on how to fix this problem.%r</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="992f5-121">解释</span><span class="sxs-lookup"><span data-stu-id="992f5-121">Explanation</span></span>  
 <span data-ttu-id="992f5-122">SSO 服务器下运行的服务帐户没有足够的权限来检查 Active Directory 中的组成员身份。</span><span class="sxs-lookup"><span data-stu-id="992f5-122">The service account that the SSO server is running under does not have sufficient permissions to check group membership in Active Directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="992f5-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="992f5-123">User Action</span></span>  
 <span data-ttu-id="992f5-124">请参阅[SSO 服务器](../core/sso-server.md)SSO 文档中。</span><span class="sxs-lookup"><span data-stu-id="992f5-124">See [SSO Server](../core/sso-server.md) in the SSO documentation.</span></span>