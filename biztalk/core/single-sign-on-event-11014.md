---
title: 单一登录：事件 11014 |Microsoft Docs
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
ms.openlocfilehash: aebd0225967e3165f19449b73488d8f938b349ef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267272"
---
# <a name="single-sign-on-event-11014"></a><span data-ttu-id="5bc6b-102">单一登录：事件 11014</span><span class="sxs-lookup"><span data-stu-id="5bc6b-102">Single Sign-On: Event 11014</span></span>
## <a name="details"></a><span data-ttu-id="5bc6b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5bc6b-103">Details</span></span>  
  
|                 |                                                                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="5bc6b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5bc6b-104">Product Name</span></span>   |                                                                <span data-ttu-id="5bc6b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="5bc6b-105">Enterprise Single Sign-On</span></span>                                                                 |
| <span data-ttu-id="5bc6b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="5bc6b-106">Product Version</span></span> |                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                |
|    <span data-ttu-id="5bc6b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5bc6b-107">Event ID</span></span>     |                                                                          <span data-ttu-id="5bc6b-108">11014</span><span class="sxs-lookup"><span data-stu-id="5bc6b-108">11014</span></span>                                                                           |
|  <span data-ttu-id="5bc6b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="5bc6b-109">Event Source</span></span>   |                                                                          <span data-ttu-id="5bc6b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5bc6b-110">ENTSSO</span></span>                                                                          |
|    <span data-ttu-id="5bc6b-111">组件</span><span class="sxs-lookup"><span data-stu-id="5bc6b-111">Component</span></span>    |                                                                           <span data-ttu-id="5bc6b-112">不可用</span><span class="sxs-lookup"><span data-stu-id="5bc6b-112">N/A</span></span>                                                                            |
|  <span data-ttu-id="5bc6b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="5bc6b-113">Symbolic Name</span></span>  |                                                                  <span data-ttu-id="5bc6b-114">SSO_ERROR_ACCESS_CHECK</span><span class="sxs-lookup"><span data-stu-id="5bc6b-114">SSO_ERROR_ACCESS_CHECK</span></span>                                                                  |
|  <span data-ttu-id="5bc6b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="5bc6b-115">Message Text</span></span>   | <span data-ttu-id="5bc6b-116">访问检查 failed.%r</span><span class="sxs-lookup"><span data-stu-id="5bc6b-116">Access check failed.%r</span></span><br /><br /> <span data-ttu-id="5bc6b-117">客户端用户： %1\\%2 %r</span><span class="sxs-lookup"><span data-stu-id="5bc6b-117">Client User: %1\\%2%r</span></span><br /><br /> <span data-ttu-id="5bc6b-118">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="5bc6b-118">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="5bc6b-119">其他数据: %4 %r</span><span class="sxs-lookup"><span data-stu-id="5bc6b-119">Additional Data: %4%r</span></span><br /><br /> <span data-ttu-id="5bc6b-120">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="5bc6b-120">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="5bc6b-121">解释</span><span class="sxs-lookup"><span data-stu-id="5bc6b-121">Explanation</span></span>  
 <span data-ttu-id="5bc6b-122">访问检查失败的客户端和应用程序列出。</span><span class="sxs-lookup"><span data-stu-id="5bc6b-122">The access check failed for the client and application listed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5bc6b-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="5bc6b-123">User Action</span></span>  
 <span data-ttu-id="5bc6b-124">其他信息应可以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="5bc6b-124">The additional information should enable you to fix the problem.</span></span> <span data-ttu-id="5bc6b-125">若要避免此错误在将来，您可以降低审核级别。</span><span class="sxs-lookup"><span data-stu-id="5bc6b-125">To avoid this error in the future, you can also lower the audit level.</span></span>