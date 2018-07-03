---
title: 单一登录： 事件 11014 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71e4c9bd-8bda-46ca-9e76-f7b4fa033167
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e86642a7f62b53d45f20e140131d6a12d0771ec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001112"
---
# <a name="single-sign-on-event-11014"></a><span data-ttu-id="8065d-102">单一登录： 事件 11014</span><span class="sxs-lookup"><span data-stu-id="8065d-102">Single Sign-On: Event 11014</span></span>
## <a name="details"></a><span data-ttu-id="8065d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8065d-103">Details</span></span>  
  
|                 |                                                                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8065d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8065d-104">Product Name</span></span>   |                                                                <span data-ttu-id="8065d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="8065d-105">Enterprise Single Sign-On</span></span>                                                                 |
| <span data-ttu-id="8065d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="8065d-106">Product Version</span></span> |                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                |
|    <span data-ttu-id="8065d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8065d-107">Event ID</span></span>     |                                                                          <span data-ttu-id="8065d-108">11014</span><span class="sxs-lookup"><span data-stu-id="8065d-108">11014</span></span>                                                                           |
|  <span data-ttu-id="8065d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="8065d-109">Event Source</span></span>   |                                                                          <span data-ttu-id="8065d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8065d-110">ENTSSO</span></span>                                                                          |
|    <span data-ttu-id="8065d-111">组件</span><span class="sxs-lookup"><span data-stu-id="8065d-111">Component</span></span>    |                                                                           <span data-ttu-id="8065d-112">N/A</span><span class="sxs-lookup"><span data-stu-id="8065d-112">N/A</span></span>                                                                            |
|  <span data-ttu-id="8065d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="8065d-113">Symbolic Name</span></span>  |                                                                  <span data-ttu-id="8065d-114">SSO_ERROR_ACCESS_CHECK</span><span class="sxs-lookup"><span data-stu-id="8065d-114">SSO_ERROR_ACCESS_CHECK</span></span>                                                                  |
|  <span data-ttu-id="8065d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="8065d-115">Message Text</span></span>   | <span data-ttu-id="8065d-116">访问检查失败。%r</span><span class="sxs-lookup"><span data-stu-id="8065d-116">Access check failed.%r</span></span><br /><br /> <span data-ttu-id="8065d-117">客户端用户： %1\\%2 %r</span><span class="sxs-lookup"><span data-stu-id="8065d-117">Client User: %1\\%2%r</span></span><br /><br /> <span data-ttu-id="8065d-118">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="8065d-118">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="8065d-119">其他数据: %4 %r</span><span class="sxs-lookup"><span data-stu-id="8065d-119">Additional Data: %4%r</span></span><br /><br /> <span data-ttu-id="8065d-120">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="8065d-120">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="8065d-121">解释</span><span class="sxs-lookup"><span data-stu-id="8065d-121">Explanation</span></span>  
 <span data-ttu-id="8065d-122">所列客户端和应用程序的访问检查失败。</span><span class="sxs-lookup"><span data-stu-id="8065d-122">The access check failed for the client and application listed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8065d-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="8065d-123">User Action</span></span>  
 <span data-ttu-id="8065d-124">其他信息应该可以帮助您解决该问题。</span><span class="sxs-lookup"><span data-stu-id="8065d-124">The additional information should enable you to fix the problem.</span></span> <span data-ttu-id="8065d-125">为了避免将来再出现此错误，您还可以降低审核级别。</span><span class="sxs-lookup"><span data-stu-id="8065d-125">To avoid this error in the future, you can also lower the audit level.</span></span>