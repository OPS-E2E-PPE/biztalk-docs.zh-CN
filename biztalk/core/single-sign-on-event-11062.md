---
title: 单一登录： 事件 11062 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55c7c2ea-c671-4853-ac64-8cb80bba98b0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50df4834f92eff7cc679c051f529f4dbaefc4335
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970134"
---
# <a name="single-sign-on-event-11062"></a><span data-ttu-id="1b300-102">单一登录： 事件 11062</span><span class="sxs-lookup"><span data-stu-id="1b300-102">Single Sign-On: Event 11062</span></span>
## <a name="details"></a><span data-ttu-id="1b300-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1b300-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1b300-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1b300-104">Product Name</span></span>   |                                                                                       <span data-ttu-id="1b300-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="1b300-105">Enterprise Single Sign-On</span></span>                                                                                        |
| <span data-ttu-id="1b300-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="1b300-106">Product Version</span></span> |                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                       |
|    <span data-ttu-id="1b300-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1b300-107">Event ID</span></span>     |                                                                                                 <span data-ttu-id="1b300-108">11062</span><span class="sxs-lookup"><span data-stu-id="1b300-108">11062</span></span>                                                                                                  |
|  <span data-ttu-id="1b300-109">事件源</span><span class="sxs-lookup"><span data-stu-id="1b300-109">Event Source</span></span>   |                                                                                                 <span data-ttu-id="1b300-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1b300-110">ENTSSO</span></span>                                                                                                 |
|    <span data-ttu-id="1b300-111">组件</span><span class="sxs-lookup"><span data-stu-id="1b300-111">Component</span></span>    |                                                                                                  <span data-ttu-id="1b300-112">N/A</span><span class="sxs-lookup"><span data-stu-id="1b300-112">N/A</span></span>                                                                                                   |
|  <span data-ttu-id="1b300-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="1b300-113">Symbolic Name</span></span>  |                                                                                    <span data-ttu-id="1b300-114">SSO_WARN_PASSWORD_FILTER_FAILED</span><span class="sxs-lookup"><span data-stu-id="1b300-114">SSO_WARN_PASSWORD_FILTER_FAILED</span></span>                                                                                     |
|  <span data-ttu-id="1b300-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="1b300-115">Message Text</span></span>   | <span data-ttu-id="1b300-116">密码筛选失败。</span><span class="sxs-lookup"><span data-stu-id="1b300-116">Password filtering failed.</span></span> <span data-ttu-id="1b300-117">将不使用任何密码筛选器。%r</span><span class="sxs-lookup"><span data-stu-id="1b300-117">No password filter will be used.%r</span></span><br /><br /> <span data-ttu-id="1b300-118">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="1b300-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="1b300-119">密码筛选器字符串: %2 %r</span><span class="sxs-lookup"><span data-stu-id="1b300-119">Password Filter String: %2%r</span></span><br /><br /> <span data-ttu-id="1b300-120">其他数据: %3 %r</span><span class="sxs-lookup"><span data-stu-id="1b300-120">Additional Data: %3%r</span></span><br /><br /> <span data-ttu-id="1b300-121">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="1b300-121">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="1b300-122">解释</span><span class="sxs-lookup"><span data-stu-id="1b300-122">Explanation</span></span>  
 <span data-ttu-id="1b300-123">创建密码筛选器时出错，并不创建的筛选器。</span><span class="sxs-lookup"><span data-stu-id="1b300-123">An error occurred while creating a password filter, and the filter was not created.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1b300-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="1b300-124">User Action</span></span>  
 <span data-ttu-id="1b300-125">若要创建密码筛选器使用创建密码筛选器向导，请参阅[如何使用密码筛选器](../core/how-to-use-password-filters.md)。</span><span class="sxs-lookup"><span data-stu-id="1b300-125">To create the Password Filter using the Create Password Filter Wizard, see [How to Use Password Filters](../core/how-to-use-password-filters.md).</span></span>